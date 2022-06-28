## AppleScript Actions

See [AppleScripts](AppleScripts "wikilink") for general overview of
using AppleScript with Quicksilver.

### Overview

AppleScripts Actions are used from Quicksilver's second pane and they
behave exactly like any normal Quicksilver Action.

AppleScript Actions give you the ability to manipulate anything in
Quicksilver's catalog. Most AppleScript Actions can use the comma trick,
and Quicksilver's 3rd pane.

### Creating AppleScript Actions

The AppleScript format for a Quicksilver action is as follows:

``` applescript
using terms from application "Quicksilver"
    on HANDLER_NAME

    end HANDLER_NAME
end using terms
```

`HANDLER_NAME` is the important bit. There are several potential
handlers.

### Open Handlers

Each script should have one "open" or "process" handler. The open or
process handler is what QuickSilver will call to do the actual work
(i.e. it's what is called when you activate the QuickSilver action).

<table>
<thead>
<tr class="header">
<th><p>Handler Name</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><pre class="applescript"><code>open files _items_</code></pre></td>
<td><p>Receives direct objects from Quicksilver. Use this handler if you
want an AppleScript Action to accept files from Quicksilver's 1st
pane</p></td>
</tr>
<tr class="even">
<td><pre class="applescript"><code>open files _items_ with _indirect_items_</code></pre></td>
<td><p>Receives direct objects and indirect objects from Quicksilver.
Use this handler if you want an Action to accept files from
Quicksilver's 1st pane and also take an item from Quicksilver's 3rd pane
(requires the <code>get argument count</code> handler.</p></td>
</tr>
<tr class="odd">
<td><pre class="applescript"><code>process text _text_</code></pre></td>
<td><p>Receives text from Quicksilver from Quicksilver's 1st pane to
process in the AppleScript</p></td>
</tr>
<tr class="even">
<td><pre class="applescript"><code>open _items_</code></pre></td>
<td><p>An old handler for sending files to Quicksilver. Should not be
used, and is replaced by the <code>open files _items_</code>
handler</p></td>
</tr>
</tbody>
</table>

#### Returning Items to Quicksilver

At the end of an AppleScript, you can return items to Quicksilver by
using `return xxx` in any of the Open Handlers in the table above.

At the moment, you can only return strings, URLs or an array (of strings
or URLs), but Quicksilver can inspect these strings and work out what
they might be. For example if you return a valid file path, Quicksilver
will turn the string into a file object. If you return an email address,
Quicksilver will turn it into an email.

An example:

``` applescript
using terms from application "Quicksilver"
    on open files _items_
        -- do something with the _items_
        return "AppleScript complete!" -- return a string
    end open files
end using terms
```

### Argument Handlers

Argument handlers tell QuickSilver what the script expects. QuickSilver
calls them when it starts up. It then uses that info to decided what
types of objects to show the script for and if it should show the third
pane.

<table>
<thead>
<tr class="header">
<th><p>Handler Name</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><pre class="applescript"><code>get argument count</code></pre></td>
<td><p>Specify whether the AppleScript action uses the 3rd pane or not.
If this handler is not present in the AppleScript, the value defaults to
1. If you would like to always use the 3rd pane with your Action then
<code>return 2</code> in this handler. if you would like the third pane
to be optional, use <code>return 3</code> in this handler.</p></td>
</tr>
<tr class="even">
<td><pre class="applescript"><code>get direct types</code></pre></td>
<td><p>Specify the types of 1st pane objects for which the action
displays. See the <a href="AppleScript_Types"
title="wikilink">AppleScript Types</a> page for more
information</p></td>
</tr>
<tr class="odd">
<td><pre class="applescript"><code>get indirect types</code></pre></td>
<td><p>Specify the types of objects that display in Quicksilver's 3rd
pane. Only used if <code>get argument count</code> returns
<code>2</code> or <code>3</code>. See the <a href="AppleScript_Types"
title="wikilink">AppleScript Types</a> page for more
information.</p></td>
</tr>
</tbody>
</table>

### Examples

For examples on how to use these handlers, see the
[AppleScripts](AppleScripts "wikilink") page. Also see the [AppleScript
Action templates](AppleScript_Action_templates "wikilink").

### Customising the Action Icon

In order to customise the icon of the action, change the AppleScript
file's icon. Do this by finding the file in Finder, choosing "Get Info"
(by right clicking or pressing ⌘I) then paste your preferred icon over
the icon in the Get Info window.

<figure>
<img src="Set_as_action_icon.png" title="Set_as_action_icon.png"
width="379" alt="Set_as_action_icon.png" />
<figcaption aria-hidden="true">Set_as_action_icon.png</figcaption>
</figure>

### Adding Script Actions to Quicksilver

Save your AppleScript file in
`~/Library/Application Support/Quicksilver/Actions/My AppleScript Action.scpt`
(where \~ is your Home folder) and relaunch Quicksilver.

Once saved, you can search for your action in Quicksilver's 2nd pane,
based on the name of the AppleScript file. In the example from the line
above, the Action name would be My AppleScript Action'.