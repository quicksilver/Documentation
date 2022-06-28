``` applescript
(*
Creates a new task in TaskUnifier.

You need to download tucl.jar http://www.taskunifier.com/pages/addon_commandline and then update tuclPath to the correct path.
You also need to "Enable communicator" in the TaskUnifier Preferences > Advanced

Save it in  ~/Library/Application Support/Quicksilver/Actions/TaskUnifier-AddTask.scpt to make it available in the 2nd pane of Quicksilver (using the 1st pane as the task text).
If you also add the Actions folder to your Catalog then you will also have the option of using it in the first pane, with an action of "Process Text", and then putting the task text in the third pane. This is useful for triggers.
*)

using terms from application "Quicksilver"
    on process text theTask
        set tuclPath to "~/bin/tucl.jar"
        set theCommand to "java -jar " & tuclPath & " \"" & theTask & "\""
        do shell script "$SHELL -lic " & quoted form of theCommand
    end process text
end using terms from
```