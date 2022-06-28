If you have [Sparrow](http://www.sparrowmailapp.com/) installed, use
this Action to [send emails directly from
Quicksilver](http://www.lovequicksilver.com/post/4101585202/quicksparrow).

The action takes text from Pane 1 in this form: Address:Subject:Content

So, for example: lovequicksilverqs@gmail.com:Good morning:Meeting today
at 10am.

``` applescript
using terms from application "Quicksilver"
    on process text _email -- Text in QS pane 1
        try
            set _delimiter to ":" -- Change this to something else if you like to use colons in the subject. (Definitely don't use @ or . or any well used characters. The delimiter in the content is fine.)
            --set _sender to "johndoe@etpan.org" -- Change this to your preferred address?

            set _atid to AppleScript's text item delimiters

            try
                set AppleScript's text item delimiters to _delimiter

                set _address to text item 1 of _email
                set _subject to text item 2 of _email
                set _content to (text items 3 thru -1 of _email) as text
            on error a number b
                set a to ("Make sure the text in Pane 1 takes the form: Address" & _delimiter & "Subject" & _delimiter & "Content
(with no " & _delimiter & "'s in the address or subject)")
                error a number 1
            end try

            set AppleScript's text item delimiters to _atid

            tell application "Sparrow Lite"
                set _outgoingMessage to make new outgoing message with properties {subject:_subject, content:_content} -- sender:_sender

                tell _outgoingMessage to make new to recipient with properties {address:_address}

                sendmessage _outgoingMessage with to recipient
            end tell

        on error a number b
            set AppleScript's text item delimiters to _atid
            activate
            display dialog a with title "QuickSparrow"
        end try
    end process text
end using terms from
```