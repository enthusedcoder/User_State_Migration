# User_State_Migration_tool

Note that this tool comes with the tools needed for it to run already included.


![PIC](https://i.imgur.com/KbujIS0.png)

A simple GUI which makes use of Microsoft's User State Migration Toolkit to create a backup of the current user profile or an offline computer.  There are a few tools that exist which can perform similar tasks, but almost none of them are free to use, and the only one that I am aware of which is [free to use](https://toolslib.net/downloads/viewdownload/317-capture-user-customizations/) only works on Windows 10 and is restricted specifically to the creation of a ppkg file for the purposes of creating recovery media.  This in of itself is insanely useful, but only really in regards to creating the recovery media, and only works when run on the operating system for which the recovery media will be created.

## How this tool is different

This tool utilizes features in the User State Migration Toolkit (which from this point on will be referred to as USMT) which are available to all the different versions of the toolkit that exist.  More specifically, the USMT was designed as a command line tool to be used as a task in operating system deployments to automate the process of migrating user data and configurations that already exist on the device to the new operating system which is installed as part of the deployment process.  This tool can be run on a live operating system or can be run from a Windows Pre-installation environment to backup user profiles on a system that will not boot.

## What this tool does

The first thing that it does is it uses another Microsoft commandline tool, **Streams**, to remove any alternate data streams found on any of the files which will be a part of the backup process.  "Alternate Data Stream" refers to a feature of NTFS file systems which enables applications to store multiple sets of data in a file.  The "Zone.Identifier" alternate data stream" is the stream which causes files (usually downloaded from the internet) to be blocked.  This process is performed in order to prevent errors in the backup process due to blocked files/folders.

![streams](https://i.imgur.com/A1YoxmW.png)

After all the files have been unblocked, the tool will begin the backup of the user profiles installed on the computer.

![backup](https://i.imgur.com/VX0fvb6.png)

After the backup has completed, you can then navigate to the folder where you designated the backup should be saved, and you will see the files needed for the migration as well as a local copy of the backed up files captured with the directory structures preserved.

![Mig](https://i.imgur.com/CJNaOLt.png)

![Look at back](https://i.imgur.com/M5u1HPY.png)

