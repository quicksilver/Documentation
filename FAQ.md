## Doesn't Spotlight make Quicksilver unnecessary?

No. Spotlight find things, but all it lets you do is open them.
Quicksilver finds things and then lets you do all sorts of stuff with
them, with just a keystroke or two. Find out more
[here](http://qsapp.com/about.php#spotlight)

## Why don't I see feature 'x' in Quicksilver?

Make sure you have the appropriate plug-in(s) installed. If it's
something in the first pane you don't see, make sure it's enabled in the
catalog and scanned (so that the catalog source has a number next to the
checkbox).

## Why isn't action 'x' available in Quicksilver's second pane?

If an action appears to be unavailable in Quicksilver's second pane (the
actions pane), ensure you have the action enabled in the Actions section
of Quicksilver's \[qs://preferences#QSPrefPane main preferences\]. If
the action you're looking for is obtained from a certain plugin, ensure
you install the plugin before checking the 'Actions' preferences.

## Why doesn't Quicksilver find the files I want?

Quicksilver will index files (and other useful items) from anywhere on
your computer that you tell it to. To add more files to the catalog of
items that Quicksilver keeps track of, you can either customize the
existing catalog entries so that they include more files, or you can add
new folders to the catalog to include the files in them (and in their
subfolders, if you like).

See the [Catalog](Catalog "wikilink") article.

## I customized my catalog, and now Quicksilver has slowed to a crawl! What happened?

You probably set one of your custom entries to have an infinite depth on
a folder that contained a vast number of files. See [Why is Quicksilver
using so much memory and/or
CPU?](#Why_is_Quicksilver_using_so_much_memory_and/or_CPU? "wikilink").

## I'm used to Quicksilver in English and don't want it translated into my language. How do I make that happen?

Localisation is great, but if you want to keep Quicksilver in English,
you can do this by running a simple command from Terminal.app:

`defaults write com.blacktree.Quicksilver AppleLanguages -array English`

Once entered, restart Quicksilver and it should be in (American) English
only.

## Quicksilver's window keeps disappearing and won't stick. What's wrong?

Certain applications, such as Windowshade X and Spirited Away, are known
not to play nicely with Quicksilver. See the list of [Known Bad
Applications](Known_Bad_Applications "wikilink").

## Why doesn't getting the Finder Selection always work correctly?

Unfortunately, this is due to a bug that only Apple can fix. See the
[Finder Selection](Finder_Selection "wikilink") article for more
information and for a workaround.

## Why won't my triggers save?

1.  Triggers are saved in
    `~/Library/Application Support/Quicksilver/Triggers.plist` if the
    permissions of that file or directory don't allow you to write, then
    no trigger will be saved. There have also been reports of this file
    becoming corrupted.
2.  If you have triggers using actions from some plugin and then
    uninstall that plugin, the triggers remain and QS can be confused.
    Sometimes a particular trigger doesn't display, sometimes only one
    of many triggers appears in the prefs. To fix, reinstall the needed
    plugins, delete the related triggers, then remove the plugin.

## Why does Quicksilver not install any plugins or hang when trying?

Check that your user account owns
`~/Library/Application Support/Quicksilver/` and the Plugins folder
beneath it. You can check and change this if needed in the Ownership &
Permission section of the folder's Info window. (To show the Info
window, either select the folder in Quicksilver's first pane and choose
the Get Info action in the second pane, or navigate to it in Finder,
right click on it, and choose Get Info from the contextual menu that
pops up.) After making sure the folder exists and you own it and have
permissions to write to it, restart Quicksilver.

Another possible cause is that you are running Little Snitch. LIttle
Snitch is a reverse firewall that prevents applications on your computer
from contacting websites unless explicitly authorized. To install
plugins, configure Little Snitch to allow Quicksilver to contact the
server where the plugins are.

## Why is Quicksilver using so much memory and/or CPU?

Quicksilver keeps the entire index in memory and scans the catalog
sources regularly. Usually when it uses too many resources it's because
the catalog is configured too large. The default `~/Documents/` source
is configured to a depth of 2, if you create a custom source of infinite
depth it will make the catalog large. Also if you configure a source for
your home directory (\~) it will probably scan many unnecessary files
(`~/Library`, etc.). This is also why your music and pictures aren't in
the global catalog and should be accessed via the iTunes and iPhoto
plug-ins which require you to type → to get into your music files and
photos.

Also network drives configured to be scanned can make the catalog large.
Note the "Find All Applications" catalog source (in the Applications
set) will scan your entire machine, including network drives for
applications.

If you have the "Clipboard Module" plugin installed and configured in
the Clipboard Preferences to Capture History you might have large
clippings in the history. This causes Quicksilver to use lots of memory.
To clear it you can use the clear button in the Clipboard History panel.

## Quicksilver crashes! How do I fix it?

**Problematic Applications**

First, check to make sure you aren't running any [Known Bad
Applications](Known_Bad_Applications "wikilink").

**Console.app**

Check the log in Console.app to see if there are any log messages or
crash reports hinting at what might have gone wrong. Look on the left
hand side for log messages titled 'Quicksilver' If you find some
reports, send them to the [bug
tracker](https://github.com/quicksilver/Quicksilver/issues).

**Catalog**

If Quicksilver crashes at startup, firstly try running Quicksilver with
a disabled Catalog. This can be done by holding ⇧ when launching
Quicksilver. If Quicksilver launches with no problems, then one of your
catalog entries is problematic. Try disabling them in turn to find the
problem. This is done by opening
`~/Library/Application Support/Quicksilver/Catalog.plist` and changing
the 'Enabled' key for each entry to 'NO'.

**Cache**

If Quicksilver is trying to read a corrupt cache, this can cause it to
crash. Try [clearing the
cache](#How_do_I_clear_Quicksilver's_cache? "wikilink").

**Plugins**

An out of date or incompatible plugin may be causing Quicksilver to
crash. First, make sure you are using all the latest plugins by going to
the [application preferences](http://qs.qsapp.com/application) and
clicking the button to check for updates.

If this does not help, try disabling plugins all plugins, then
re-enabling them one at a time to try and find which one may be
problematic.

**Shelf Problem**

If this doesn't solve your problem, see if you have a
`~/Library/Application Support/Quicksilver/Shelves/` folder. Quit
Quicksilver, move it out of the way and start Quicksilver again.
Sometimes the shelf gets corrupted or if you've copied a huge (say
photoshop file) to the clipboard history QS tries to allocate huge
amounts of memory and fails.

## How do I clear Quicksilver's cache?

If you start to see strange changes in behavior that was previously
working fine, clearing out the cache will probably fix it. A common
example of such a problem is when searching for something, you can only
get an entry that ends in "(Catalog)". To clear the cache:

1.  Quit Quicksilver
2.  Move `~/Library/Caches/com.blacktree.Quicksilver/` to the Trash
3.  Move `~/Library/Caches/Quicksilver/` to the Trash
4.  Start Quicksilver

It may take a minute for the catalog to become repopulated.

## How do I back up or reset Quicksilver's settings?

Reinstalling Quicksilver doesn't change any saved configuration.
Quicksilver stores all it's state in the following locations (\~
represents your home folder):

-   `~/Library/Application Support/Quicksilver/`
-   `~/Library/Preferences/com.blacktree.Quicksilver.plist`
-   `~/Library/Caches/Quicksilver/`
-   `~/Library/Caches/com.blacktree.Quicksilver/`

**To back up Quicksilver's settings**, copy the first two items in the
list to a safe location (e.g. your Desktop folder).

**To reset Quicksilver to it's initial configuration**, open the
'Application' section of Quicksilver's \[qs://preferences#QSPrefPane
main preferences\] and click the 'Reset Preferences' button.

If your problem stops then you know it caused by something wrong in your
previous configuration. Try copying items back one-by-one from your
backup, restarting Quicksilver after putting back each file, until you
find the cause of your trouble. Here's what the files in the app support
directory do:

-   `Actions.plist` - list of installed actions
-   `Catalog.plist` - the configured catalog sources
-   `Mnemonics.plist` - learned inputs, defaults and abbreviations
-   `PlugIns.plist` - the list of available plug-ins and how they are
    configured
-   `Triggers.plist` - the configured triggers
-   `Caches/` - another cache folder
-   `Indexes/` - folder of indexed items
-   `PlugIns/` - installed plug-ins
-   `Shelves/` - where items on the Shelf and clipboards are stored
-   `Actions/` - not installed by default. The user can create this
    folder to add scripts that implement custom actions
-   `Templates/` - not installed by default. The user can create this
    folder to add template files to use with the Make New... action