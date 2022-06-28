Get the Dropbox public link URLs for files in your Dropbox Public
folder. For multiple files, the URL will be copied to the clipboard one
at a time (useful if Clipboard History is active).

Put your Dropbox Public folder path in the _publicFolderPath property,
e.g. /Users/username/Dropbox/Public

Replace the 0 in the _dropboxID property with your Dropbox id
(right-click a file in the Public folder, Copy Public Link and get the
number from within the clipboard url).

``` applescript
-- Put your Dropbox Public folder path in the quotes, e.g. /Users/example/Dropbox/Public
property _publicFolderPath : ""

-- Replace the 0 with your Dropbox id (right-click a file in the Public folder, Copy Public Link and get the number from within the clipboard url).
property _dropboxID : 0

on _findAndReplace(_toFind, _toReplace, _theText)
    set _astid to AppleScript's text item delimiters
    try
        set AppleScript's text item delimiters to _toFind
        set textItems to _theText's text items
        set AppleScript's text item delimiters to _toReplace
        tell textItems to set _editedText to beginning & _toReplace & rest
        set AppleScript's text item delimiters to " "
        set _textItems2 to text items of _editedText
        set AppleScript's text item delimiters to "%20"
        set _editedText to _textItems2 as text
        set AppleScript's text item delimiters to _astid
        return _editedText
    on error a number b
        set AppleScript's text item delimiters to _astid
        error a number b
    end try
end _findAndReplace

using terms from application "Quicksilver"
    on open _theseItems
        try
            repeat with _anItem in _theseItems
                tell application "Finder"
                    set _path to POSIX path of (_anItem as text)
                    set _fileName to my _findAndReplace(_publicFolderPath, "", _path)
                    set _url to "http://dl.dropbox.com/u/" & _dropboxID & _fileName

                    set the clipboard to _url
                    -- Need a delay between copying to the clipboard
                    if (count of _theseItems) > 1 then delay 1
                end tell
            end repeat

            -- These 2 lines (1 won't work) clear a multiple selection from Quicksilver's first pane.
            tell application "Quicksilver" to set selection to missing value
            tell application "Quicksilver" to set selection to missing value

            tell application "Quicksilver" to set selection to _url
        on error a number b
            display dialog a
        end try
    end open
end using terms from
```