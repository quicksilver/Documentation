The Plugins List is the list of plugins that is sent from the QSApp.com
server to Quicksilver.

The list is created using the
[QS-Builder](https://github.com/ddlsmurf/qs-builder) ruby script, and a
separate list compiled for each combination of OS version / QS version
pair.

The ruby script will need to be run, and the QSApp.com server updated
when any of the following happen

### Plugin Related Events

-   A brand new plugin is released
-   A plugin version is updated. Here we *may* need to check the
    compatibility of the plugin with previous QS version. If for example
    the new plugin adds a brand new feature, it should be available for
    previous QS users if possible. Maybe we assume it works for all
    versions -- unless stated (key in .plist?)
-   A plugin is seen to break with a new QS version
-   A plugin is seen to break with a new OS version

### QS Related Events

-   A new QS version is released. Any reports on broken plugins from
    users (we can't be expected to test them all). Ties to \#3 above
-   QS adds support for a new OS (new 'OS' folder (?))
-   QS drops support for a new OS (remove an old 'OS' folder (?))

### OS Related Events

-   A new OS version is released (ties in with \#4 in 1st list)