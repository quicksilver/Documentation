# Actions

<b>Based on original text and images from the [Quicksilver User's
Guide](Quicksilver_User's_Guide "wikilink")</b>

## Explanation

Executing an Action in Quicksilver is known as a 'Command'. Commands are
entered via two or three panes containing respectively an Object, an
Action and if a third pane is needed, an Argument. Actions appear in
Quicksilver's second pane.

![<File:Command_diagram.png>](Command_diagram.png "File:Command_diagram.png")

A preference pane shows all the Actions that can be performed (⌘comma,
select Actions). Uncheck Actions to remove them from use. Drag Actions
within the list to improve their priority in the results list in the
second pane. See [ordering Actions](ordering_Actions "wikilink").

[<file:Quicksilver_actions_preferences.png>](file:Quicksilver_actions_preferences.png "wikilink")

Actions can be added by plugins, or by the user in
\~/Library/Application Support/Quicksilver/Actions. Plugins are optional
modules that are installed which can also add Objects or other
capabilities to Quicksilver. User installed Actions generally require a
text or file Object in the first pane.

All Actions work on an Object and Actions are allowed based on the type
of Object selected. E.g., the Open URL action is only available for
Objects that are URLs. Actions that require an Argument typically end in
“...” and Arguments are expected to be of a certain type. E.g., the
Email to... Actions expect the Argument to be an email address or
contact.

![<File:URL_first_action.png>](URL_first_action.png "File:URL_first_action.png")

## Usage

Select an Object in the first pane, tab, and start typing to find
Actions in the second pane. Once the desired Action has been found,
press enter to execute the command.

As you type in the second pane, your choices are filtered down from all
possible choices to only those that match what you’ve typed (which are
shown in the results list).

The following example is for a file/folder Object in the first pane.
Matches can be by the beginning of the phrase (e.g., type "op" for
"Open"); the first letter of each word of the choice (e.g., "ow" for
“Open With…”; or even any following letters within the word (e.g., "oe"
for "open", but not "eo"). The more you use specific Actions the more
quickly they will be matched. After a few times, once you type "op"
Quicksilver will guess “Open” and if you do it enough, you should be
able to choose "Open" just by typing "o".

Some Actions have a complementary Action that reverse the Object and
Argument type. E.g., you can enter the command “file, Email
To...(Compose), address” or the command “address, Email Item...
(Compose), file”. Notice the names of the Actions are slightly different
(To vs Item). Many (but not all) Action names hint at the type of
Argument they take. Email To.... wants an address to follow. Email
Item... wants some kind of item to send (text or a file). These email
Actions are so similarly named you might not have noticed they are
different.

In other cases Actions are so differently named you might not notice
they are related. E.g., a pair of Actions is used for searching web
sites (like Google). You can enter a command as “site, Search For...,
query” or “query, Find With..., site”. Complementary Action pairs allow
Quicksilver to adapt to how you think of commands. Then there are
commands like Make New... which have no complement and don’t hint at
what their Argument type is. (It's a file from \~/Library/Application
Support/Quicksilver/Templates.)

![<File:Complimentary_Actions.png>](Complimentary_Actions.png "File:Complimentary_Actions.png")

## Advanced tips

Immediate execution:

If you hold down the last key you type to select an Action it will
execute it. So I can select a file in the first pane, tab to the second
and hold down "o" to use the "Open" Action. This method is a little
risky if you don’t know what the Action will be, but if you do it’s a
little faster and there’s no trigger configuration needed. It’s less
risky when you realize you can configure the ranking of Actions in the
Actions Preference pane. To make it faster you can type the letter with
the ⇧⌘ modifiers from the first pane. So to open a file in the first
pane I would type ⇧⌘O to have Quicksilver execute the command. This only
allows you to use one letter to identify the Action and has the same
risk that you have to know what Action will be run, but if you do, it
can be convenient.

Capitalized keys:

Since the matching algorithm is case-insensitive the shift key is
available for some use in Quicksilver. If you check “Capitalize Key
modifies Action in command window“ in Preferences - Extras, then shifted
letters are used to select the Action, eliminating the need to tab to
the second pane. Once moved to the Action pane, unshifted letters don’t
change the first pane, all typing counts for the second pane. If you
also hold down the ⌘ key the Action will be performed immediately, no
need to type return. E.g., ⇧I selects the Action for "i" (perhaps "Get
Info") while ⇧⌘I performs the Action for "i".

## Alternate Actions

Alternate actions are a quick way of modifying the action without a need
to re-type the action. The the [Alternate
Actions](Alternate_Actions "wikilink") page for more information and a
list of actions and their alternate counterparts.