# ConnectingGuide
A comparison of some methods of connecting to a remote server for development purposes from Mac

How best to connect to a server on Mac? I hold the following (highly subjective and inexperienced) opinions on the matter.

Summary:
For long-term convenience pick a remote editing plugin for your chosen text editor. I recommend this method.
For simplicity use the command 'scp' to copy files to your server.
Mac does have an equivalent to Putty called Cyberduck ...but see below.

More detail:
A plugin for your text editor (IDE). This is probably best. The point of accessing your server is usually to edit so might as well; no need to leave your development environment; enhance an existing tool you already installed and know; plugins are simpler that programs, right?; an equivalent to 'nppftp' plugin for Notepad++ is the Remote Development bundle for Visual Studio Code
Cons: something else to install and learn, but worth it; since there are loads of IDEs a class helper cant really learn your specific one and plugin, you may need to read both docs and figure it out yourself; I discovered I needed to add my key with 'ssh-add' for it to work
marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack

Cyberduck a remote file "browser". A direct equivalent to puTTY!; many features (probably) since it’s a stand alone program
Cons: a stand alone program to install and learn and use, unlike Finder, Terminal or your IDE; a bulky memory hog?
cyberduck.io/

Mountainduck a remote disk mounter. Enables shared folders in Finder like Windows. For the proper GUI file manager experience
Cons: still not in your IDE. Install and learn
mountainduck.io/

'sshfs' a command line package for mounting servers as a disk in Finder, like a command line equivalent to Putty. Seems to more permanently mount the disk into your system
Cons: it seems to not be built in (anymore?) so if you’re going to install and learn something you might as well look at all options; not simple, I cant work it :) , probably need Homebrew the package manager which means installing something to install something, but Homebrew is great anyway
github.com/osxfuse/osxfuse/wiki/SSHFS

'scp' secure copy, for file transfer. This is the simplest method of file transfer; quick; built in; exercises have few files anyway;
Cons: transfers single files at a time unless you zip them; not everyone likes command line

'ssh -i...' allows you to issue commands to your server, meaning you edit the files directly on the server with the command line editor. You already possess the private key, so no setup other than follow what the output tells you to do; the command is built in; no install; immediate results
Cons: needed every time you connect with this method; command line
'ssh-add" adds your key to a key manager. It shortens the ssh command for repeat use; it’s needed for some editor plugins to work, see below
Cons: another step; command line

'rsync' a better scp synchronises multiple files, and only the changes not the entire files every time
Cons: another command to learn (and I haven’t); command line

Mac owners, what do you think?
