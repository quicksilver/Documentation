This AppleScript is very similar to the [Show Date and Time with Growl
(AppleScript)](Show_Date_and_Time_with_Growl_(AppleScript) "wikilink"),
but uses Quicksilver's built in Large Type function to display the
result

``` applescript
tell application "Quicksilver"
    show large type (current date)'s time string & " — " & (current date)'s date string
end tell
```