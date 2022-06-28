Several templates for AppleScript actions are given here. To learn what
they mean and how to use them, see [AppleScript
Actions](AppleScript_Actions "wikilink").

Note that Quicksilver is fully backwards-compatible with AppleScript
actions written using obsolete templates, so those will still work with
the latest version of Quicksilver, but they will not benefit from the
new features available using the current templates. To use these new
features, update your scripts to use the current template.

## Current Templates

These templates will work for version 1.0 of Quicksilver and above.

If there is one that you use frequently, consider saving the template
(perhaps with a link to this page commented at the top) in your
\~/Library/Application Support/Quicksilver/Actions folder. Once there,
you can use Finder's Info pane to set it as "Stationary" (with or
without being "Locked"), and every time it is opened through Finder, it
will open a duplicate copy without changing the original. Prevent the
template from showing up as an "action" by unselecting it in
Quicksilver's preferences (Preferences -\> Actions, uncheck), and
instead add it to your Quicksilver catalog for easy access through
Quicksilver.

### Process files or folders in Quicksilver's first pane

\<syntaxhighlight lang="applescript" enclose="div”\> using terms from
application "Quicksilver"

` on open files direct_objects `

`   (* Your script goes here *)`

` end open files`

` --This handler may be omitted if the action accepts for all direct object types.`
` on get direct types`
`   (* Possible values to return can include any of: `
`       "NSFilenamesPboardType"`
`       "NSStringPboardType"`
`       "Apple URL pasteboard type"`
`       "QSFormulaType"`
`       "qs.process"`
`       "qs.command"`
`       "QSRemoteHostsType"`
`       "com.apple.itunes.track" `
`   See `[`http://qsapp.com/wiki/AppleScript_Types`](http://qsapp.com/wiki/AppleScript_Types)` for details. *)`
`   return {"NSFilenamesPboardType"}`
` end get direct types`

end using terms from

</syntaxhighlight>

### Process files or folders in Quicksilver's first pane with one or more indirect objects (third pane)

\<syntaxhighlight lang="applescript" enclose="div”\> using terms from
application "Quicksilver"

` on open files direct_objects with indirect_objects`

`   (* Your script goes here *)`

` end open files`

` on get argument count`
`   (* Use "return 1" (or omit this entire handler) to never show the third pane. `
`   Use "return 2" to force the third pane to show. `
`   Use "return 3" to make the third pane optional. *)`
`   return 2`
` end get argument count`

` --This handler may be omitted if the action accepts all direct object types.`
` on get direct types`
`   (* Possible values to return can include any of: `
`       "NSFilenamesPboardType"`
`       "NSStringPboardType"`
`       "Apple URL pasteboard type"`
`       "QSFormulaType"`
`       "qs.process"`
`       "qs.command"`
`       "QSRemoteHostsType"`
`       "com.apple.itunes.track" `
`   See `[`http://qsapp.com/wiki/AppleScript_Types`](http://qsapp.com/wiki/AppleScript_Types)` for details. *)`
`   return {"NSFilenamesPboardType"}`
` end get direct types`

` --This handler may be omitted if the action accepts all indirect object types.`
` on get indirect types`
`   (* Possible values to return can include any of: `
`       "NSFilenamesPboardType"`
`       "NSStringPboardType"`
`       "Apple URL pasteboard type"`
`       "QSFormulaType"`
`       "qs.process"`
`       "qs.command"`
`       "QSRemoteHostsType"`
`       "com.apple.itunes.track" `
`   See `[`http://qsapp.com/wiki/AppleScript_Types`](http://qsapp.com/wiki/AppleScript_Types)` for details. *)`
`   return {"NSFilenamesPboardType",  "NSStringPboardType"}`
` end get indirect types`

end using terms from

</syntaxhighlight>

### Process text in Quicksilver's first pane

\<syntaxhighlight lang="applescript" enclose="div”\> using terms from
application "Quicksilver"

` on process text direct_object`

`   (* Your script goes here *)`

` end process text`

` --This handler may be omitted if the action accepts all direct object types.`
` on get direct types`
`   (* Possible values to return can include any of: `
`       "NSFilenamesPboardType"`
`       "NSStringPboardType"`
`       "Apple URL pasteboard type"`
`       "QSFormulaType"`
`       "qs.process"`
`       "qs.command"`
`       "QSRemoteHostsType"`
`       "com.apple.itunes.track" `
`   See `[`http://qsapp.com/wiki/AppleScript_Types`](http://qsapp.com/wiki/AppleScript_Types)` for details. *)`
`   return {"NSStringPboardType", "Apple URL pasteboard type"}`
` end get direct types`

end using terms from

</syntaxhighlight>

### Process text in Quicksilver's first pane with one or more indirect objects (third pane)

\<syntaxhighlight lang="applescript" enclose="div”\> using terms from
application "Quicksilver"

` on process text direct_object with indirect_objects`

`   (* Your script goes here *)`

` end open files`

` on get argument count`
`   (* Use "return 1" (or omit this entire handler) to never show the third pane. `
`   Use "return 2" to force the third pane to show. `
`   Use "return 3" to make the third pane optional. *)`
`   return 2`
` end get argument count`

` --This handler may be omitted if the action accepts all direct object types.`
` on get direct types`
`   (* Possible values to return can include any of: `
`       "NSFilenamesPboardType"`
`       "NSStringPboardType"`
`       "Apple URL pasteboard type"`
`       "QSFormulaType"`
`       "qs.process"`
`       "qs.command"`
`       "QSRemoteHostsType"`
`       "com.apple.itunes.track" `
`   See `[`http://qsapp.com/wiki/AppleScript_Types`](http://qsapp.com/wiki/AppleScript_Types)` for details. *)`
`   return {"NSStringPboardType", "Apple URL pasteboard type"}`
` end get direct types`

` --This handler may be omitted if the action accepts all indirect object types.`
` on get indirect types`
`   (* Possible values to return can include any of: `
`       "NSFilenamesPboardType"`
`       "NSStringPboardType"`
`       "Apple URL pasteboard type"`
`       "QSFormulaType"`
`       "qs.process"`
`       "qs.command"`
`       "QSRemoteHostsType"`
`       "com.apple.itunes.track" `
`   See `[`http://qsapp.com/wiki/AppleScript_Types`](http://qsapp.com/wiki/AppleScript_Types)` for details. *)`
`   return {"NSFilenamesPboardType",  "NSStringPboardType"}`
` end get indirect types`

end using terms from

</syntaxhighlight>

## Obsolete templates

### Requires at least Quicksilver β61

#### Process text in Quicksilver's first pane with an indirect object (third pane)

\<syntaxhighlight lang="applescript" enclose="div”\> using terms from
application "Quicksilver"

` on process text dObject with iObject`
`   activate`
`   set message to "Direct is '" & dObject & "'"`
`   if class of iObject is list then`
`     -- user used the comma trick to add multiple objects to the indirect object (the third pane)`
`     set message to message & " indirect has " & (number of items in iObject) & " items:"`
`     repeat with i from 1 to number of items in iObject`
`       set message to message & return & tab & quote & (item i of iObject) & quote`
`     end repeat`
`   else if class of iObject is text then`
`     -- there is only one item in the third pane`
`     set message to message & " indirect is '" & iObject & "'"`
`   end if`
`   display dialog message buttons {"OK"} default button 1`
` end process text`

` on get argument count`
`   return 2 -- if you want the third pane to be filled, otherwise return 1 (or leave this handler out)`
` end get argument count`

end using terms from

</syntaxhighlight>

### Prior to Quicksilver β61

#### Process text in Quicksilver's first pane

\<syntaxhighlight lang="applescript" enclose="div”\> using terms from
application "Quicksilver"

`on process text the_text`
` --Enter your code to work with the_text here.`
` end process text`

end using terms from

</syntaxhighlight>

#### Process files or folders in Quicksilver's first pane

\<syntaxhighlight lang="applescript" enclose="div”\> on open the_items

` --If only one file was selected in the first pane, the_items will be an alias to that file.`
` --If the comma trick was used to select multiple files in Quicksilver's first pane, the_items will be a list of aliases`
` `
` --Enter your code to work with the_items here.`

end open

</syntaxhighlight>