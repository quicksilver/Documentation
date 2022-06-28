## Overview

This AppleScript is run from Quicksilver's 1st pane to either turn
Bluetooth on or off, depending on its current state. The AppleScript
requires the installation of [Growl](http://growl.info) (for
notifications), and [blueutil](https://github.com/toy/blueutil) for the
Bluetooth management. Download Growl from their website, and blueutil
from [here](http://qs0.qsapp.com/scripts/blueutil.zip)

To install blueutil, unzip the downloaded file and copy it to the folder
`/usr/local/bin`. (Alternatively, if you have homebrew installed on your
system, use `$ brew install blueutil`

Once these two are installed, download the 'Bluetooth.scpt' script, and
save it somewhere in Quicksilver's catalog.

## \[Code\] Enable and Disable Bluetooth

``` applescript
property blueutilPath : "/usr/local/bin/blueutil"


-- Check the current bluetooth status and turn it on if necessary.
if execBlueutil("") is "0" then
    execBlueutil("1")
    tell application "Growl"
        set the allNotificationsList to {"Bluetooth Setting"}
        set the enabledNotificationsList to {"Bluetooth Setting"}
        notify with name "Bluetooth Setting" title "Bluetooth On" description "Bluetooth has been enabled." application name "AppleScript - Bluetooth" icon of file (path to me)
    end tell
else
    -- Set the bluetooth status to what it was before.
    execBlueutil("0")
    tell application "Growl"
        set the allNotificationsList to {"Bluetooth Setting"}
        set the enabledNotificationsList to {"Bluetooth Setting"}
        notify with name "Bluetooth Setting" title "Bluetooth Off" description "Bluetooth has been disabled." application name "AppleScript - Bluetooth" icon of file (path to me)
    end tell
end if


on execBlueutil(command)
    set res to do shell script blueutilPath & " power " & command
    if res contains "Error" then
        display dialog res
        quit
    end if
    return res
end execBlueutil
```

## \[Code\] Enable Bluetooth and Connect to Bluetooth Device

Supplemental script to connect to paired bluetooth device after enabling
bluetooth via blueutil.

``` applescript
-- Enable Bluetooth and Connect to iPhone

property blueutilPath : "/usr/local/bin/blueutil"

-- Turn on bluetooth.
execBlueutil("1")
tell application "Growl"
    set the allNotificationsList to ¬
        {"Bluetooth Setting"}
    set the enabledNotificationsList to ¬
        {"Bluetooth Setting"}
    register as application ¬
        "AppleScript - Bluetooth" all notifications allNotificationsList ¬
        default notifications enabledNotificationsList
    notify with name ¬
        "Bluetooth Setting" title ¬
        "Bluetooth is On & iPhone Connected" description ¬
        "Bluetooth has been enabled with iPhone tethered." application name "AppleScript - Bluetooth" icon of file (path to me)
end tell

on execBlueutil(command)
    set res to do shell script blueutilPath & " power " & command
    if res contains "Error" then
        display dialog res
        quit
    end if
    return res
end execBlueutil

-- Connect Device
tell application "System Preferences"
    activate
    set AppleScript's text item delimiters to "."
    set current pane to pane "com.apple.preference.network"
    set winNetwork to "Network"
    set btooth to "Bluetooth"
    tell application "System Events" to tell process "System Preferences"
        set theRow to row 1 of table 1 of scroll area 1 of window winNetwork whose value of static text 1 contains btooth
        select theRow --clicks the bluetooth row
        --If Bluetooth is already connected, the button will say Disconnect, so we don't want to turn it off:
        try
            click (button 1 of group 1 of window winNetwork whose title is "Connect")
        end try
    end tell
    tell application "System Preferences"
        quit
    end tell
end tell
```

## \[Code\] Only Disable Bluetooth

Stripped version of main script used to only turn off bluetooth

``` applescript
-- Disable Bluetooth

property blueutilPath : "/usr/local/bin/blueutil"

-- Turn off Bluetooth.
execBlueutil("0")
tell application "Growl"
    set the allNotificationsList to ¬
        {"Bluetooth Setting"}
    set the enabledNotificationsList to ¬
        {"Bluetooth Setting"}
    notify with name ¬
        "Bluetooth Setting" title ¬
        "Bluetooth Off" description ¬
        "Bluetooth has been disabled." application name "AppleScript - Bluetooth" icon of file (path to me)
end tell

on execBlueutil(command)
    set res to do shell script blueutilPath & " power " & command
    if res contains "Error" then
        display dialog res
        quit
    end if
    return res
end execBlueutil
```