'''Most of the information here comes from Howard Melman's [Quicksilver
User's Guide](Quicksilver_User's_Guide "wikilink") and Quick Reference.

Here are some key characters with their meanings attached:

⇧shift ⌃control ⌥option ⌘command ↵enter ⇥tab ⌫delete ⎋escape ⇲end ⇱home
⇟page down ⇞page up ←left arrow →right ↓down ↑up βbeta ßeszett!

## From OS X

| Key combination | What it does                                              |
|-----------------|-----------------------------------------------------------|
| ⌃space          | Invoke Quicksilver (default)                              |
| ⌘⎋              | Invoke Quicksilver with Finder or frontmost app selection |

## Within Quicksilver

| Key combination   | What it does                                                                                                        |
|-------------------|---------------------------------------------------------------------------------------------------------------------|
| ↵ or ⌃O           | Execute current Command                                                                                             |
| ⌃↵                | Collapse current Command into first pane as a single item                                                           |
| ⇥                 | Move focus to next pane                                                                                             |
| ⌘⇧letter          | [Execute Command for Action associated with ⇧letter](http://lovequicksilver.com/post/7413266835/putting-in-a-shift) |
| ⌫                 | Clear entered keystrokes in current pane                                                                            |
| ⌫                 | Clear selection in current pane if no entered keystrokes                                                            |
| ⌘↵                | Run the alternate for the current action                                                                            |
| ⌘⌃D (twice?)      | Set as default item for current search (Broken in 10.7?)                                                            |
| ⌘K                | Show task viewer                                                                                                    |
| ⌘L                | Show Clipboard History (requires Clipboard Plugin)                                                                  |
| ⌘⌃Q               | Restart Quicksilver                                                                                                 |
| ⌘R                | Rescan catalog                                                                                                      |
| ⌘⌥S               | Show Shelf (requires Shelf Plugin)                                                                                  |
| ⌘T                | Open Fonts (flaky\*)                                                                                                |
| ⇟ or ⌃V           | Next page in list                                                                                                   |
| ⇞ or ⌥V (broken?) | Previous page in list                                                                                               |
| ↓ or ⌃N or ⌃J     | Next item in list                                                                                                   |
| ↑ or ⌃P or ⌃K     | Previous item in list                                                                                               |
| ⇲                 | End of list                                                                                                         |
| ⇱                 | Start of list                                                                                                       |
| ⌘,                | Preferences                                                                                                         |
| ⌘?                | Guide                                                                                                               |
| ⌘' or ⌘⌃:         | Triggers                                                                                                            |
| ⌘;                | Catalog                                                                                                             |
| ⌘" or ⌘⇧'         | Plug-ins                                                                                                            |
| ⎋ or F5           | Dismiss list if visible                                                                                             |
| ⎋ or F5           | Dismiss Quicksilver if no list visible                                                                              |

## Within the first pane

| Key combination | What it does                                                    |
|-----------------|-----------------------------------------------------------------|
| ⎋ or F5         | Reset search to top level of Catalog if list visible            |
| hold letter     | Execute default Command for Object associated with letter       |
| \~ or \` or ⌘⌥N | Home folder                                                     |
| ⌘A              | Select all in list                                              |
| ⌘G              | Grab Finder or frontmost app selection                          |
| ⌘⌥G             | [Grab 'n Drop](Grab_'n_Drop "wikilink")                         |
| ⌘\[             | Go back to the previously selected object (browse history back) |
| ⌘\]             | Go forward to next selected object (browse history forward)     |
| → or / or ⌃L    | Move down into folder/item                                      |
| ← or ⇧/ or ⌃H   | Move up out of folder/item                                      |
| ⌥→ or ⌥/        | Show hidden files                                               |
| ,               | Collect items [Comma Trick](Comma_Trick "wikilink")             |
| ⌥,              | Uncollect items [Comma Trick](Comma_Trick "wikilink")           |
| .               | Enter text mode                                                 |
| =               | Calculate mathematical expression (requires Calculator Plugin)  |

## Within the second pane

| Key combination | What it does                                        |
|-----------------|-----------------------------------------------------|
| hold letter     | Execute Command using Action associated with letter |

## Spacebar behavior

Determine this in Preferences\>Preferences\>Command. The table describes
the effect of each option.

| Option                 | What it does                                                                            |
|------------------------|-----------------------------------------------------------------------------------------|
| Normal                 | Returns items with space(s) in the name.                                                |
| Select Next Result     | Next item in list                                                                       |
| Jump to Argument Field | Moves the focus to pane 3 and subsequently selects the next Action that requires pane 3 |
| Switch to Text Mode    | Also adds a space to the typed text (pane 1 only)                                       |
| Show Item's Contents   | Drill down into Object (pane 1 only)                                                    |

## Emacs-style keybindings in text entry mode

| Key combination | What it does                     |
|-----------------|----------------------------------|
| ⌃A              | Start of line                    |
| ⌃E              | End of line                      |
| ⌃B              | Back one character               |
| ⌃F              | Forward one character            |
| ⌃D              | Forward delete                   |
| ⌃H              | Delete                           |
| ⌃K              | Forward delete line              |
| ⌃N              | Down one line                    |
| ⌃O              | Line break / Carriage return (?) |
| ⌃P              | Up one line                      |
| ⌃V              | Last character                   |
| ⌃Y              | Paste forward deleted line (?)   |
|                 |                                  |

Standard OS X shortcuts work in Quicksilver, too: ⌘H Hide, ⌘W Close, ⌘Q
Quit, ⌘X Cut, ⌘C Copy, ⌘V Paste, ⌘B Bold, ⌘U Underline, ⌘⌥T Show Char
Palette

Some shortcuts, such as the main invocation hotkey, can be modified in
[Preferences](Preferences "wikilink"), and others can be added with
[Triggers](Triggers "wikilink").

Note that system-wide shortcuts (such as ⌘⎋ to enter Front Row) might
supersede application shortcuts—you may have to disable these in System
Preferences to expose the Quicksilver key combination.

(\*Appearance of the Fonts pane depends on Preferences being last
activated in the current Space (10.6).)