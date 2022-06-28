Quicksilver can be called from AppleScript. Quicksilver can also call
AppleScripts and you can attach triggers to these scripts as well. This
page provides an overview of the ways you can use AppleScript with
Quicksilver along with some useful AppleScripts that users have created
in the past.

## Calling Quicksilver from AppleScript

You can open an object in Quicksilver by setting its selection property
in AppleScript. Quicksilver will try to automatically determine what
kind of object the text actually represents to show the appropriate
actions. Some examples:

``` applescript
tell application "Quicksilver" to set selection to "text"
tell application "Quicksilver" to set selection to "/"
tell application "Quicksilver" to set selection to "http://google.com"
```

## Pane 1 AppleScripts

These Applescripts are selected in Quicksilver's first pane. Simply
select any .scpt file in the first pane and then the 'Run' action.

You can also use AppleScript editor to save a script as an
'Application'. Like any application they can then be selected in the
first pane and then run using the the 'Open' action.

### Adding Pane 1 AppleScripts to catalog

You can add scripts to your [Catalog](Catalog "wikilink") to quickly
find and Run them. Quicksilver by default adds the scripts it finds in
\~/Library/Scripts and /Library/Scripts. You can add more locations by
adding a 'File & Folder Scanner'.

### Using TextAction AppleScripts in Pane 1

Any Text Action AppleScript (see below) can also be used in the first
pane. When you select a Text Action AppleScript in the first pane
instead of getting the Run action you will get the "Process Text..."
action and be prompted for the text in the third pane. This can be very
useful for making Triggers for TextAction AppleScripts.

You may also want to consider adding a "'\~/Library/Application
Support/Quicksilver/Actions/" File & Folder Scanner Scanner to your
catalog so that Text Action AppleScripts can be quickly selected.

### Example Pane 1 Scripts

These simple scripts take no arguments. Copy them into AppleScript
Editor and then save them as .scpt files.

[Show Date and Time with Growl
(AppleScript)](Show_Date_and_Time_with_Growl_(AppleScript) "wikilink")

[Show Date and Time with Large Type
(AppleScript)](Show_Date_and_Time_with_Large_Type_(AppleScript) "wikilink")

[Open AirDrop (AppleScript)](Open_AirDrop_(AppleScript) "wikilink")

[Toggle Bluetooth
(AppleScript)](Toggle_Bluetooth_(AppleScript) "wikilink")

[Color Picker (AppleScript)](Color_Picker_(AppleScript) "wikilink") -
displays the color picker from any app

## Pane 2 AppleScript Actions

Action Applescripts are actions you can select in Quicksilver's second
pane for certain first pane types (the script determines what types).

To install a scripts, save it in *\~/Library/Application
Support/Quicksilver/Actions/MyActionName.scpt* where MyActionName is the
name the action will have in the second pane, and \~ is your user's home
folder. Then **relaunch Quicksilver**. Create the *Actions* folder if it
doesn't exist.

See the [AppleScript Actions](AppleScript_Actions "wikilink") page for
information on writing your own actions.

### Text Action AppleScripts

[QuickSparrow](QuickSparrow_(AppleScript) "wikilink") : Send emails directly from Quicksilver using Sparrow.
[SuperTweet](SuperTweet_(AppleScript) "wikilink") : Send tweets directly from Quicksilver using [SuperTweet](http://www.supertweet.net/) and [twitter](http://twitter.com).
[Encode/Decode URL](Encode/Decode_URL_(AppleScript) "wikilink") : Convert between encoded and unencoded URLs (%20 \<=\> space, %26 \<=\> & ,etc).
[Display Growl](Display_Growl_(AppleScript) "wikilink") : Displays a Growl Notification for your inputted text
[TaskUnifier AddTask](TaskUnifier_AddTask_(AppleScript) "wikilink") : Adds a task to TaskUnifier

### File Action AppleScripts

[Dropbox public link](Dropbox_public_link_(AppleScript) "wikilink") : Gets the Dropbox public link URLs for files in your Dropbox Public folder.
[Paste file path](Paste_file_path_(AppleScript) "wikilink") : of the file in the first pane.
[Shorten URL](Shorten_URL_(AppleScript) "wikilink") : Makes a short link from a URL in the first pane (and optionally on the clipboard). Multiple versions posted.
[Combine PDFs](Combine_PDFs_(AppleScript) "wikilink") : Combines pages from multiple PDFs into a single document.
[Select File In Dialog](Select_File_In_Dialog "wikilink") : Allows you to use Quicksilver to select a file in an Open/Save dialog box

### Miscellaneous Action AppleScripts

[Mosh (AppleScript)](Mosh_(AppleScript) "wikilink") : Use data from the Remote Hosts plugin to automatically Mosh into a host

### Three-Pane AppleScripts

[Run command in shell with arguments](Run_command_in_shell_with_arguments "wikilink") : Runs a text command entered in the first pane using the file or text arguments entered in the third pane.

<!-- -->

[Convert Units To...](Convert_Units_To "wikilink") : Takes a value with units in the first pane, and converts it to the units entered in the third pane.

### Probably-Obsolete Actions

[Quick Look](Quick_Look_(AppleScript) "wikilink") : for multiple files in the same Finder folder *(obsoleted by native QuickLook support in QS)*
[Quick Quick Look](Quick_Quick_Look_(AppleScript) "wikilink") : for multiple files in different Finder folders, although the mouse is needed to navigate the Quick Look window

### Write your own AppleScript actions

To learn how to write your own AppleScript Actions for Quicksilver, see
[AppleScript Actions](AppleScript_Actions "wikilink").

For convenience, you can start using one of the [AppleScript Action
templates](AppleScript_Action_templates "wikilink").