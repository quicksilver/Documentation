Save it as Quick Look.scpt, and then run it with a file selected in the
first pane. If you use it on multiple files, be aware that Quicklook
will only show you the files in one Finder window at a time. Code:

``` applescript
on open these_items
    tell application "Finder"
        activate
        select these_items
        tell application "System Events" to key code 49
    end tell
end open
```