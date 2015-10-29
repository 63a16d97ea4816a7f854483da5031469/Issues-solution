#Checkout specific revision from SVN by using command line:

You should never use TortoiseProc.exe as a command-line Subversion client! TortoiseProc should be used for TortoiseSVN GUI automation only. See the note in TortoiseSVN's Manual:

Remember that TortoiseSVN is a GUI client, and this automation guide shows you how to make the TortoiseSVN dialogs appear to collect user input. If you want to write a script which requires no input, you should use the official Subversion command line client instead.
Use Subversion command-line svn.exe client. With the command-line client you can run

Checkout a working copy in REV revision:

**svn checkout --revision REV https://svn.example.com/svn/MyRepo/trunk/**

The successful command is:

**svn checkout --revision 38270 https://lei.cao@10.180.8.8/svn/........**






svn checkout https://svn.example.com/svn/MyRepo/trunk/@REV

Update your local working copy to REV revision:

svn update --revision REV

Export (i.e. download) a file or a development branch in REV revision:

svn export --revision REV https://svn.example.com/svn/MyRepo/trunk/

svn export https://svn.example.com/MyRepo/trunk/@REV

You may notice that with svn checkout and svn export you can enter REV number as --revision REV argument and as trailing @REV after URL. The first one is called operative revision, the second one is called peg revision. Read SVNBook for more information about peg and operative revisions concept.


> http://rubyrobot.org/tutorial/subversion-with-mac-os-x

simple svn commands of MAC:

svn log

svn status

update the SVN files:

svn update

check the latest 5 items of SVN for current SVN folder:

svn log -l 5 -v 


Now we want to update the repository with the changes we made. This process is called "committing":
$ svn commit -m "Added some text"




The common commands:

Here is a list of common commands:

ls 
list files and directories

cd 
change directory
mkdir 
create a new directory
cp 
copy files or directories
mv 
move (rename) files or directories
rm 
remove files or directories


The personal commands of mac/linux:
ls -lrt



