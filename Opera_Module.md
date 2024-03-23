# Opera\_Module

### Overview

Enables Quicksilver to find the [Opera](http://www.opera.com/) Browser's current tabs, bookmarks and searches. Also adds 10 scripts for moving URLs between browsers, and 'Open with Opera' as an Action. A Proxy Object that allows 'Operas current web page' to be accessed from anywhere using Quicksilver is broken in ß58 10.6.

The author's [Homepage](http://s-softs.com/Projects/QSOpera/index.html) ![Open> with Opera Action 1
1.jpg](images/Open\_with\_Opera\_Action\_1\_1.jpg)

### Preference Items

Activate Quicksilver and press ⌘comma to open [Preferences](https://docs.qsapp.com/documentation/preferences). Each column represents a page within the main Preferences window. Best practise is to activate the items in the columns from left to right. Bullet points indicate items within the containing item. The items to check are in bold.

| Catalog                                                                                                                                                                                                                                                                                                                                                   | <p>Preferences</p><ul><li>Actions</li></ul>                                     |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| <ul><li><p>Modules</p><ul><li><p><strong>Opera</strong></p><ul><li><strong>Opera bookmarks and searches</strong></li><li><strong>Control Scripts</strong></li></ul></li></ul></li></ul><p><br>* Quicksilver</p><ul><li><p></p><ul><li><p><strong>Proxy Objects</strong></p><ul><li><strong>Operas current web page</strong></li></ul></li></ul></li></ul> | <ul><li><p>URLs</p><ul><li><strong>Open with Opera</strong></li></ul></li></ul> |
|                                                                                                                                                                                                                                                                                                                                                           |                                                                                 |

### Commands

To execute [Commands](https://docs.qsapp.com/documentation/commands): select the Objects and Actions for each pane in Quicksilver, and press enter. Items exclusive to the plugin are in bold. Items in brackets are additional instructions for when typing in the panes.

| Pane 1                                                                                             | Pane 2                             | Pane 3       | Extra Requirements                                                                                                                                                                                                                                   | Notes                                                                                                                                                                                                        |
| -------------------------------------------------------------------------------------------------- | ---------------------------------- | ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| URL                                                                                                | **Open with Opera**                |              |                                                                                                                                                                                                                                                      |                                                                                                                                                                                                              |
| <p><strong>Opera bookmarks URLs</strong><br>[→ into Opera bookmarks and<br>searches (Catalog)]</p> | \[Use Actions that work with URLs] |              |                                                                                                                                                                                                                                                      | **Broken in ß58 10.6.**                                                                                                                                                                                      |
| <p><strong>Opera searches URLs</strong><br>[→ into Opera bookmarks and<br>searches (Catalog)]</p>  | Search For…                        | \[Type text] |                                                                                                                                                                                                                                                      | **Broken in ß58 10.6.**                                                                                                                                                                                      |
| <p><strong>Opera's open tab URLs</strong><br>[→ into Opera]<br></p>                                | \[Use Actions that work with URLs] |              | Opera is running and has open tabs!                                                                                                                                                                                                                  |                                                                                                                                                                                                              |
| **URL - Copy from Opera to Safari.scpt**                                                           | Run                                |              |                                                                                                                                                                                                                                                      | <p>Opens Opera's current URL in Safari.<br><br>9 similar scripts for copying and moving URLs<br>between Opera,Safari and Firefox are<br>downloaded and cataloged.</p>                                        |
| **Operas current web page**                                                                        | \[Use Actions that work with URLs] |              | <p>Check 'Enable advanced features'<br>in Preferences, Application</p><p>Proxy Objects checked in the Catalog</p>                                                                                                                                    | **Broken in ß58 10.6.**                                                                                                                                                                                      |
| Current Web Page                                                                                   | **Open with Opera**                |              | <p>Check 'Enable advanced features'<br>in Preferences, Application<br><br>Proxy Objects checked in the Catalog<br><br><a href="Safari_Module/">Safari Module</a> installed, and the<br>'Current Web Page' Proxy Object<br>checked in the Catalog</p> | <p>The 'Current Web Page' object should<br>be named 'Safari's Current Web Page',<br>as that's what it represents.<br>This Command is great for quickly checking<br>the current URL in Safari with Opera.</p> |
|                                                                                                    |                                    |              |                                                                                                                                                                                                                                                      |                                                                                                                                                                                                              |

### Tutorials

Module setup and use.\{{#ev:youtube|IlWinySuoX4\}}

### Plugin Info

This can be found by pressing the 'i' button at the bottom of the Preferences window when the plugin is selected on the Plug-ins page.

Plugin for connecting Quicksilver and Opera.

* Adds a catalog with the bookmarks and searches of Opera
* Adds a "Operas current web page" proxy object
* Adds an "Open with Opera" action
* Adds a couple of scripts for switching between Opera and Safari
* Browse into Opera to get current open tabs
