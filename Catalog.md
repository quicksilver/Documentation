# Catalog

### Overview

The items Quicksilver has access to are defined by the contents of its 'Catalog'. You can view what Quicksilver currently contains in its Catalog by opening the Quicksilver preferences (open Quicksilver and press ⌘,) and clicking the 'Catalog' icon.

![Quicksilver\_Catalog.png](Quicksilver\_Catalog.png)Quicksilver\_Catalog.png

### Adding to the Catalog

#### Files and Folders

To add new files or folders to Quicksilver's catalog, perform one of the following:

* Find your file(s) or folder(s) in Finder, and drag it into the Catalog Preferences Window
* Click the '+' in the bottom of the Catalog Preferences Window and select 'File & Folder Scanner'

![](images/addcatalog.png)

#### Other Items

The types of items that Quicksilver can be add to its Catalog can be extended through the installation of plugins. The table below shows a few (but not all!) of the plugins that can add new catalog 'Sources' to Quicksilver.

| Plugin              | Added Catalog Source | Description                                                                                                                                                                                                                                                                 |
| ------------------- | -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Built in            | Synonym              | Allows you to specify a new name for an item in Quicksilver's catalog by providing a synonym. E.g. you could create a synonym for 'Sparrow.app' called 'Mail' so that when you search for 'Mail' you can select 'Sparrow.app'                                               |
| Web Searches Plugin | Web Search List      | Allows Quicksilver to catalog Web Search URLs for searching websites. The URL you enter must contain '\*\*\*' in place of the search string. E.g. for a Web Search on Google.com, the Search URL would be [`http://google.com/search?q=`](http://google.com/search?q=)`***` |
| Remote Hosts Plugin | Remote Hosts         | Allows you to define a file which Quicksilver scans for 'Remote Host' items. See the [Remote Hosts](https://docs.qsapp.com/documentation/remote\_hosts) documentation for more information                                                                                                                      |
| Spotlight Plugin    | Spotlight            | Add files to the catalog based on a Spotlight search. To do so, you define the spotlight query and limit the search to a specific folder.                                                                                                                                   |

### Customizing a pre-existing catalog entry

Quicksilver's default configuration tells it to look for files in a limited number of places. For example, it will look for files your Documents folder, but not inside any subfolders of your Documents folder. To tell Quicksilver to look deeper into these subfolders, you'll need to customize the Documents catalog entry. To do this, go to the 'User' section of Quicksilver's \[qs://preferences#QSCatalogPrefPane catalog preferences] and select the Documents source. Click the ⓘ button at the bottom of the preferences window to open the info drawer for the catalog entry, and then select the Attributes tab in it. Click on "Create Copy". This will clone the default Documents entry into your catalog's 'Custom' section. Now in the 'Source Options' tab of the info drawer, set the depth to your custom value.

### For further information on customizing your catalog

See the [Quicksilver User's Guide](Quicksilver\_User's\_Guide/).
