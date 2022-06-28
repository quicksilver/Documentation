This script can be used to change an already open Open/Save dialog box
to another file/folder. To use it, first open the dialog in your
application, then launch Quicksilver, select a file/folder in the first
pane, then the script in the second pane.

See [AppleScripts](AppleScripts "wikilink") for more information on
using and installing AppleScripts. See this
[thread](https://groups.google.com/forum/?hl=en&fromgroups=#!topic/blacktree-quicksilver/NwYiLiPt3NQ)
for discussion on this script in particular.

``` applescript
using terms from application "Quicksilver"
    on get direct types
        return {"NSFilenamesPboardType"}
    end get direct types

    on open files theFiles
        set filePath to POSIX path of item 1 of theFiles
        tell application "System Events"
            set theApplication to application processes whose frontmost is true
            set target to item 1 of theApplication
            set target to a reference to front window of target
            tell target to keystroke "g" using {command down, shift down} -- Activate goto field
            delay 0.1
            if ((count target's sheets) > 0) then set target to front sheet of target -- Open panels use a sheet
            tell target
                tell sheet 1
                    try
                        set value of text field 1 to filePath
                        delay 0.5
                        click button "Go"
                    on error theError -- Carbon apps don't support setting the field directly, so type out the path.
                        keystroke filePath
                        delay 1
                        keystroke return
                    end try
                end tell
                --
            end tell
        end tell
    end open files
end using terms from
```