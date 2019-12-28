## Emulators Scoop Bucket

There's no easy way to keep track of all existing emulators out there, and keep them up-to-date. To make it worse, what if you want a stable and a developer release of the same emulator? It makes it even more difficult! [Scoop](http://scoop.sh) helps you get the programs you need, with a minimal amount of point-and-clicking. It's highly scalable and easily customized. It's almost like a package manager our *NIX friends know and love. It makes it easy to download, install, update and uninstall apps on your computer, as easy as `scoop install <app-name>`, cool right? Check our [contribution guide](#Contributing) to help us expand this bucket.

## Installation
#### Installing Scoop
Make sure [PowerShell 5](https://aka.ms/wmf5download) (or later, include [PowerShell Core](https://docs.microsoft.com/en-us/powershell/scripting/install/installing-powershell-core-on-windows?view=powershell-6)) and [.NET Framework 4.5](https://www.microsoft.com/net/download) (or later) are installed. Then run:

    Invoke-Expression (New-Object System.Net.WebClient).DownloadString('https://get.scoop.sh')

    # or shorter
    iwr -useb get.scoop.sh | iex
Scoop will be installed by default on your user's home folder, likely on `C:\Users\<username>\scoop\`.

#### Installing Emulators Scoop Bucket
To make it easy to install apps from this bucket, with [scoop](#-Installing-Scoop) installed, run

    scoop bucket add emulators https://github.com/hermanjustnu/scoop-emulators.git
The bucket will be installed on `C:\Users\<username>\scoop\buckets\emulators\`.

To find which apps are available to install (from all installed buckets), run

    scoop search

#### Installing Emulators from the Scoop Bucket
With the emulators' scoop bucket installed, run

    scoop install <app-name>
    # examples:
    scoop install retroarch
    scoop install citra-nightly
The emulators will be installed on `C:\Users\<username>\scoop\apps\<app-name>\current`. For each installed emulator there will be key folders or files that will persist across your installs/updates, this is managed by [Scoop](http://scoop.sh), which is very convenient, especially if you want to keep your save data and customizations across installations. Shortcuts will be automatically created on your start menu.

#### Notes on the Install Path
Unfortunately as of today, there's no way to specify a custom install folder per installed app in [Scoop](http://scoop.sh), there is however an alternative for that. You can create a [Symbolic Link](https://www.howtogeek.com/howto/16226/complete-guide-to-symbolic-links-symlinks-on-windows-or-linux/) and basically add a living shortcut to where you want your emulator to be located. For that, open a command prompt as Administrator and run

    mklink /D "<destination-path>" "C:\Users\<username>\scoop\apps\<app-name>\current"

## Updates
#### Updating Scoop
To update scoop itself, run

    scoop update

#### Updating Emulators from the Scoop Bucket
To update all the apps installed on your computer via [Scoop](http://scoop.sh), run

    scoop update *

To update a specific emulator via scoop, run

    scoop update <app-name>
    # examples:
    scoop update retroarch
    scoop update citra-nightly

#### Automating Updates
If you're like me and don't want to remember commands, or even to update, you can very simply create a PowerShell script and perhaps even add it to Windows' Task Scheduler, to run daily or in your preferred schedule. The script contents would just be:

    scoop update
    scoop update *
This bucket will always have at least one commit per day for the nightly builds. And is immediately updated once the included emulators get a newer version.

## Contributing
Thank you for considering contributing to the Emulators Scoop Bucket! You may propose new features or improvements of existing bucket behavior in the GitHub issue board. If you propose a new feature, please be willing to implement at least some of the code that would be needed to complete the feature.

### Credits
- [lukesampson](https://github.com/lukesampson) for creating Scoop and the original Retroarch manifest.
- [Ash258](https://github.com/Ash258) for creating the original RPCS3 manifest.
