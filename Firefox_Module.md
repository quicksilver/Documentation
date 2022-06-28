Features:

-   Adds a new preset to the Catalog that imports bookmarks from
    Firefox, Mozilla, and Netscape
-   Allows Firefox to handle javascript bookmarklets

## Getting the plugin to work with Firefox 3+

-   Open <about:config> in Firefox Location bar
-   Search for "browser.bookmarks.autoExportHTML"
-   Double click it to enable it (Or right click it and hit toggle)
-   Restart Firefox & Quicksilver...

Enabling "browser.bookmarks.autoExportHTML" makes Firefox export it's
bookmarks from its SQLite database to a bookmarks.html file. At the
moment, it is currently not possible to do the same for History