A 3rd pane AppleScript action that takes text from Pane 1 and displays a
[Growl](http://growl.info/) Notification. If you uncomment the "with
sticky" part, the notification will remain on the screen until dismissed
by the user explicitly.

This script is written for Growl 2.0+. To make it work with earlier
versions, replace (tell application "Growl") to (tell application
"GrowlHelperApp")

``` applescript


using terms from application "Quicksilver"
    on process text theText
        growl(theText)
    end process text
end using terms from

on growl(theText)
    -- For Growl versions < 2.0, change (tell application "Growl") to (tell application "GrowlHelperApp")
    tell application "Growl"
        -- tell application "GrowlHelperApp"
        set the allNotificationsList to {"Quicksilver Growl"}
        set the enabledNotificationsList to allNotificationsList

        register as application ¬
            "Quicksilver Growl" all notifications allNotificationsList ¬
            default notifications enabledNotificationsList ¬
            icon of application "Quicksilver"

        --       Send a Notification... Uncomment the "with sticky" if you don't want the notification to automatically dismiss itself. Great for displaying quick, disposable notes.
        --  You can change the title of the notification by replacing "a quick note:" with your own text.
        notify with name ¬
            "Quicksilver Growl" title ¬
            "a quick note:" description ¬
            theText application name ¬
            "Quicksilver Growl" --with sticky
    end tell
end growl
```