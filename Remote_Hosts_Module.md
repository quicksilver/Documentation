Given a text file with a list of machines in it (either hostname, Fully
Qualified Domain Name, or IP address), this plug-in indexes them as
"remote host" objects and provides the following actions:

-   SSH
-   SSH as root
-   SSH as… \[username in 3rd pane\]
-   Telnet
-   Telnet to port… \[port number in 3rd pane\]
-   FTP
-   HTTP
-   HTTPS
-   Screen Sharing (VNC)
-   Browse with CIFS
-   Mount share with CIFS… \[share name in 3rd pane\]
-   Browse with AFP
-   Mount share with AFP… \[share name in 3rd pane\]
-   MS Remote Desktop \[requires the CoRD application\]

There is also a "Use as Remote Host" action that applies to text. If you
type a hostname by hand, paste it, or pull it from an application using
⌘⎋ or ⌘G, this action will "convert" it to a remote host in Quicksilver
so you can connect to it, etc.

Some of the above actions also provide "alternate" actions. Hit ⌘↩
instead of ↩ to run the alternate.

`Action      Alternate`
`-------     -------------`
`SSH         SSH as root`
`FTP         Get FTP URL`
`HTTP        Get HTTP URL`
`HTTPS       Get HTTPS URL`

The "Get XYZ URL" actions are useful in situations where you need to
paste the URL to a remote machine, or want to open it in something other
than the default application.

Selecting a host in Quicksilver and hitting → or / will show IP
Addresses and aliases for that host (if available). Quicksilver treats
these as strings, so you can use "Large Type", paste them into the
current application, send them via IM or e-mail, etc.

1.  1.  Lights-Out Management

The LOM address is itself another "remote host" in Quicksilver. With it
selected, you can use one of the above actions to connect to it.

The plug-in will scan \~/.hosts for a list of machines by default. The
file is treated as UTF-8. It should contain one host per line. The
hostname or FQDN should be the first thing on each line, but other
metadata is allowed (separated by a single space). An example might look
like this:

`server1.example.com`
`server2`
`server3.example.com ostype:linux`
`server4.example.com ostype:linux lom:10.1.2.3 label:test`
`appleserver.example.com `[`icon:com.apple.xserve`](icon:com.apple.xserve)` ostype:macosx`
`windows.example.com ostype:windows`
`somehost ostype:solaris`

You may already have a file like this for completion in your shell. If
you have existing metadata in this file, it shouldn't break anything,
but it won't necessarily be useful in Quicksilver.

The plug-in scans for items on each host's line that look like this:
key:value. All such data will be stored along with the host in
Quicksilver's catalog, but there are currently only four that will
affect its behavior.

ostype: OS type should be a short, generic word, like "solaris", "linux", "windows", etc. Currently, the only real distinction is between "windows" and everything else. Windows hosts get a different default icon and certain actions don't appear. Default icons for additional OS types may be added in the future.
icon: You can specify an icon to use for a host if you don't like its default. This can be a bundle identifier, like "com.apple.Terminal", the name of an icon in the CoreTypes bundle like "com.apple.mac", or the path to an icon or image file. The usual types of images are supported, but they will most likely get squished into a square (depending on which Quicksilver interface you use).
lom: The Lights-Out Management address will only apply to fancy, rack-mounted servers that provide some sort of network-based LOM. If you don't know what this means, you probably don't need to worry about it. The information itself should be an IP address, hostname, or FQDN for the system's LOM interface.
label: By default, all hosts in your catalog will be labeled with their hostname, FQDN, or IP address (as it appears in your file). Setting a label in the file will append to the default, not replace it. Quicksilver searches the text in the label as you type to search for things. If you have many hosts with similar names, they can be hard to get to quickly. Using this item to append to the label can be useful to group or "tag" systems for faster searching.

You can optionally pull hosts from \~/.ssh/known_hosts. There is a
preset (disabled by default) under "Remote Hosts" in the Modules section
of the Catalog.

1.  1.  Tips

After installation, you may want to check the precedence of the actions
and make sure they're to your liking. The actions only apply to "remote
hosts" in the catalog, so moving them up rather high on the list
shouldn't interfere with other tasks. You may also want to disable some
of the ones you never think you'll use.

For more than a few machines, you should use a script to generate a
.hosts file from DNS, LDAP, a database, or some other authoritative
source if possible, rather than managing it by hand. You might also
schedule a job to update the file on a regular basis.

If you find yourself using "SSH as…" frequently, you may want to add
something like this to your \~/.ssh/config:

`Host server.domain`
`  User someuser`

See the ssh_config(5) man page for details.

Finally, don't forget the "comma trick". You can select multiple hosts
using the comma or ⌘A, then connect to them all at once.

1.  1.  Why?

If you have more than two or three systems that you regularly interact
with, this plug-in will speed up the process tremendously.

I have over 100 systems that I connect to via SSH on a regular basis --
sometimes as a regular user, sometimes as root. That is the main
motivation behind this plug-in. But once Quicksilver knows about all
these remote systems, it makes sense to start adding other actions
besides those related to SSH, which is where some of the additional
functionality comes in.

I've kept a list of systems I use in \~/.hosts for years to allow shell
completion on hostnames. It made sense to have Quicksilver use this as
well. In the past, Quicksilver was made aware of these through .term
files in \~/Library/Application Support/Terminal under 10.4 and using
.inetloc files in 10.5+. It was a pain to keep in sync with \~/.hosts,
you needed duplicate entries if you wanted to connect as root, via
telnet, etc. and the resulting functionality was limited.

1.  1.  Known Issues and To Do Items

-   There's no interface for configuring a custom catalog entry (to pull
    hosts from different files) although you can add them, and such
    entries will work if you edit them in Catalog.plist by hand.
-   The extra step of converting text in the first pane to a remote host
    before being able to connect is intentional. I wanted to give the
    actions some default priority to make them easier to access in the
    most common use cases. If I supported strings and assigned these
    priorities, the remote host actions would end up being higher than
    other defaults for things typed by hand, such as "Large Type". If we
    let "Large Type" remain as default, you would need to select an
    action like "SSH" by hand each and every time.
-   I've attempted to add the obvious NFS actions, but the "Internet
    Locations" for this protocol doesn't seem to work everywhere. If you
    use "Connect to Server…" in the Finder and type
    <nfs://server/share_name>, it works. But open
    <nfs://server/share_name> from Terminal fails. This is essentially
    what the plugin is asking the system to do, so if open doesn't like
    it, we're out of luck. Sorry.

1.  1.  Possible Future Actions

-   Ping
-   Scan with nmap
-   Etc.

1.  1.  Pie-in-the-Sky Stuff

-   Optionally use the output from a command as the source instead of a
    file (so you could pull a list of hostnames from LDAP, DNS, etc. in
    real-time)
-   Make each host object a target for file copy operations (resulting
    in an SCP to the default user's home directory?)
-   Right-arrow into a host to get a list of files (via SCP or SFTP?)

1.  1.  Credit

This would not be possible without the information found at
<http://lipidity.com/apple/quicksilver-plugins-in-objective-c>.