# Commands

**Based on original text and images from** [**Howard Melman's User Manual**](http://groups.google.com/group/blacktree-quicksilver/web/Quicksilver.pdf?\_done=%2Fgroup%2Fblacktree-quicksilver%3F)

### Explanation

Executing an Action in Quicksilver is known as a 'Command'. Commands are entered via two or three panes containing respectively an Object, an Action and if a third pane is needed, an Argument. Actions appear in Quicksilver's second pane.

![Command\_diagram.png>](images/Command\_diagram.png)

A preference pane shows all the Actions that can be performed (⌘comma, select Actions). Uncheck Actions to remove them from use. Drag Actions within the list to improve their priority in the results list in the second pane. See [ordering actions](ordering\_actions/).

![Quicksilver\_actions\_preferences.png>](images/Quicksilver\_actions\_preferences.png)

Actions can be added by plugins, or by the user in \~/Library/Application Support/Quicksilver/Actions. Plugins are optional modules that are installed which can also add Objects or other capabilities to Quicksilver. User installed Actions generally require a text or file Object in the first pane.

All Actions work on an Object and Actions are allowed based on the type of Object selected. E.g., the Open URL action is only available for Objects that are URLs. Actions that require an Argument typically end in “...” and Arguments are expected to be of a certain type. E.g., the Email to... Actions expect the Argument to be an email address or contact.

![URL\_first\_action.png>](images/URL\_first\_action.png)

### Usage

Select an Object in the first pane, tab, and start typing to find Actions in the second pane. Once the desired Action has been found, press enter to execute the Command.

As you type in the second pane, your choices are filtered down from all possible choices to only those that match what you’ve typed (which are shown in the results list).

The following example is for a file/folder Object in the first pane. Matches can be by the beginning of the phrase (e.g., type "op" for "Open"); the first letter of each word of the choice (e.g., "ow" for “Open With…”; or even any following letters within the word (e.g., "oe" for "open", but not "eo"). The more you use specific Actions the more quickly they will be matched. After a few times, once you type "op" Quicksilver will guess “Open” and if you do it enough, you should be able to choose "Open" just by typing "o".

Some Actions have a complementary Action that reverse the Object and Argument type. E.g., you can enter the Command “file, Email To...(Compose), address” or the Command “address, Email Item... (Compose), file”. Notice the names of the Actions are slightly different (To vs Item). Many (but not all) Action names hint at the type of Argument they take. Email To.... wants an address to follow. Email Item... wants some kind of item to send (text or a file). These email Actions are so similarly named you might not have noticed they are different.

In other cases Actions are so differently named you might not notice they are related. E.g., a pair of Actions is used for searching web sites (like Google). You can enter a Command as “site, Search For..., query” or “query, Find With..., site”. Complementary Action pairs allow Quicksilver to adapt to how you think of Commands. Then there are Commands like Make New... which have no complement and don’t hint at what their Argument type is. (It's a file from \~/Library/Application Support/Quicksilver/Templates.)

![Complimentary\_actions.png>](images/Complimentary\_actions.png)

### Advanced tips

Immediate execution:

If you hold down the last key you type to select an Action it will execute it. So I can select a file in the first pane, tab to the second and hold down "o" to use the "Open" Action. This method is a little risky if you don’t know what the Action will be, but if you do it’s a little faster and there’s no trigger configuration needed. It’s less risky when you realize you can configure the ranking of Actions in the Actions Preference pane. To make it faster you can type the letter with the ⇧⌘ modifiers from the first pane. So to open a file in the first pane I would type ⇧⌘O to have Quicksilver execute the Command. This only allows you to use one letter to identify the Action and has the same risk that you have to know what Action will be run, but if you do, it can be convenient.

Capitalized keys:

Since the matching algorithm is case-insensitive the shift key is available for some use in Quicksilver. If you check “Capitalize Key modifies Action in Command window“ in Preferences - Extras, then shifted letters are used to select the Action, eliminating the need to tab to the second pane. Once moved to the Action pane, unshifted letters don’t change the first pane, all typing counts for the second pane. If you also hold down the ⌘ key the Action will be performed immediately, no need to type return. E.g., ⇧I selects the Action for "i" (perhaps "Get Info") while ⇧⌘I performs the Action for "i". Use with caution as it’s not always clear which Action is invoked.
