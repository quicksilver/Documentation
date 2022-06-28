This Applescript displays the time and date in a Growl pane, with the
icon of a clock. Setting Quicksilver to run this Applescript with a
trigger means you can display the time & date whenever you like without
having it displayed in the Menu Bar.

``` applescript
tell application "System Events"
    set timedate to do shell script "date '+Date: %d/%m/%y%nTime: %H:%M'"
    tell application "GrowlHelperApp"
        set the allNotificationsList to {"Time & Date"}
        set the enabledNotificationsList to {"Time & Date"}
        register as application "Time & Date" all notifications allNotificationsList default notifications enabledNotificationsList
        notify with name "Time & Date" title timedate description "" application name "Time & Date" image from location "/System/Library/CoreServices/CoreTypes.bundle/Contents/Resources/Clock.icns"
    end tell
end tell
```