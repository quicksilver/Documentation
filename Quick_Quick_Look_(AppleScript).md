This script is rather hacky… If you know a better way, contact
QSApp.com.

Use the mouse to navigate in Quick Look, unfortunately the keyboard
doesn't work.

Will Quick Look the contents of 1 folder if selected in pane 1. CAUTION:
it takes \~8 seconds/1000 files, so it's quicker to right arrow into a
very large folder, select all, and then do this action.

Clicking the close button will bring the selection back to pane 1.

Will Quick Look files from different folders!

``` applescript
on open _files
    _quickLookRoutine(_files)

    -- These 2 lines clear any previous multiple selection (Comma Trick) in pane 1.
    tell application "Quicksilver" to set selection to missing value
    tell application "Quicksilver" to set selection to missing value

    tell application "Quicksilver" to set selection to every item of _files
end open


on _quickLookRoutine(_files)
    try
        tell application "System Events" -- Quicker than Finder
            if (count of _files) = 1 and kind of item 1 of _files = "Folder" then
                set _filesOfFolder to (every item of (item 1 of _files))
                set _files to {}
                repeat with _file in _filesOfFolder
                    -- Passes over hidden files (name starts with ".") and icon file.
                    set _name to name of _file
                    if item 1 of _name ≠ "." and _name ≠ ("Icon" & return) then
                        set _filePath to path of _file
                        tell me to set end of _files to alias _filePath
                    end if
                end repeat
            end if
        end tell

        set _posixPaths to ""
        repeat with _file in _files
            tell me to set _posixPaths to _posixPaths & " " & (quoted form of POSIX path of (_file))
        end repeat

        set _script to "qlmanage -p " & _posixPaths
        do shell script _script

        return missing value
    on error a number b
        display dialog a
    end try
end _quickLookRoutine
```