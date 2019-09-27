# PythonBackdoor
A python backdoor that should be able to run on all platforms and can handle multible clients.

## Features
* Handling multible clients
* Adding clients to groups and manipulate them all at once
* Executing commands with timeout
* Uploading/Downloading files with progess bar
* Zip folders or files
* Take screenshots

## Upcoming Features
* Keylogger
* Webcam access
* Ipv6 support

## How to use
The server uses a group system to control the clients. You can address them with their indices(0, 1, ...) or with the groups, in which they are.
When they connect all clients are automatically in the 'all' group. So for example you can list all connected clients with `l all`.
You also can address multiple groups or indices at once for example `l 1 2 3` but if ou select one client two times it will count as once: `l all 1`.
In some commands I had to split the attributes with @ because I wanted to be able to send spaces for example:
 `c echo test @ all` here I could not make out the point where the second argument starts so I needed the @.

* `h` - show command list
* `o [option] [value]` - set option; option can be:
    - `cmd_timeout`, value is timeout in seconds
    - `zip_compression`, value is compression level from 0 to 9
* `l [clients]` - print a table of the clients
* `t [tag] @ [clients]`" - tag clients(tags can be seen when you list clients. They are just to keep better track)
* `r [clients]` - remove clients
* `g [mode] [clients] @ [group names]` - edit groups; mode can be:
    - `add` - add client to group 
    - `rm` - remove client from group
* `c [command] @ [clients]` - remotely execute command
* `d [path to open] @ [path to save] @ [clients]` - download a file from target
* `u [path to open] @ [path to save] @ [clients]` - upload a file to target
* `s [monitor] [path_to_save] @ [clients]` - capture screenshot; monitor can be -1 for all monitors or 0, 1, 2, ... for one specific
* `z [path to open] @ [path to save] @ [clients]` - compress folder or file to .zip
* `x` - exit server

## Required modules

* texttable
* mss

This is my first project on github so feel free to give tips.