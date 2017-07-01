# Linux Tips

## Easy File Management

From terminal type:

`mc`

Retropie comes installed with a "graphical" file manager named Midnight Commander. 
It has two windows to do file operations like copy from one window to another, 
delete, rename, etc. You can navigate through folders by using the arrows keys and 
hitting enter -- or **if you're connected to your Pi using SSH you can use your
mouse.**

Some keyboard commands:

|Key|Description|
|--|--|
|ctrl-t|highlight file (copying, moving more than one file)|
|tab|move cursor to the opposite window|
|f1-f10|file operations|

----

## SSH without password

On your Mac or Linux machine, generate your machine's key:

`ssh-keygen`

Copy it to your Pi (or other machine...):

`ssh-copy-id pi@retropie.local`

or by IP address

`ssh-copy-id pi@192.168.1.69`

You can also open FTP, SFTP in your windows! Under the top navbar both `Left` and `Right` use the `FTP link...` or `SFTP link...` menu items. Enter the full url of the host you want to connect to. E.g. `pi@ftp://192.168.1.69`. Now you can copy from Pi to Pi.
