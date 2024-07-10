<div align="center">

###### *Welcome to the most complete database of all AppImage packages and portable applications for GNU/Linux.*

# PORTABLE LINUX APPS

### *the first AUR-inspired AppImage Software Center!*

--------

#### *This site lists **2094** Appimage packages and standalone applications.*

*From here you can download them, install them, update them (for real), get more information about the sources and their developers... and if you want, you can contribute yourself by adding the missing information, because this site is **open source**!*

--------

| *[Go to the applications list](https://portable-linux-apps.github.io/apps.html)* | *[Install "AM", the package manager](https://github.com/ivan-hc/AM)* |
| - | - |
| [<img src="https://github.com/Portable-Linux-Apps/Portable-Linux-Apps.github.io/assets/88724353/3d0442a9-02d7-4bb5-8da7-6da7111d872a" width="512" height="256">](https://portable-linux-apps.github.io/apps.html) | [<img src="https://github.com/Portable-Linux-Apps/Portable-Linux-Apps.github.io/assets/88724353/b0cbada6-9054-46ed-84ab-35db379dbf53" width="512" height="256">](https://github.com/ivan-hc/AM) |

</div>

------------------------------------------------------------------------
### Main Index
------------------------------------------------------------------------

- [What are the portable linux apps?](#what-are-the-portable-linux-apps)
- [How is this site different from other sites that list AppImage packages?](#how-is-this-site-different-from-other-sites-that-list-appimage-packages)
- [Is there a centralized repository for AppImage packages?](#is-there-a-centralized-repository-for-appimage-packages)
- [Differences between "AM" and "AppMan"](#differences-between-quotamquot-and-quotappmanquot)
  - [Ownership](#ownership)
  - [About "sudo" usage](#about-quotsudoquot-usage)
  - [How apps are installed](#how-apps-are-installed)
  - [How to use "AM" in non-privileged mode, like "AppMan"](#how-to-use-quotamquot-in-non-privileged-mode-like-quotappmanquot)
- [What programs can be installed](#what-programs-can-be-installed)
- [How to update all programs, for real](#how-to-update-all-programs-for-real)
- [Installation](#installation)
  - [How to install "AM"](#how-to-install-quotamquot)
  - [How to install "AppMan"](#how-to-install-quotappmanquot)
- [External links index (tutorials, troubleshooting, sandboxing and more](#external-links-index)
- [Related projects](#related-projects)

--------

### What are the portable linux apps?
*Portable Linux Apps are standalone applications for GNU/Linux that can (theoretically) run everywhere, also on a USB stick. These applications can be AppImage packages (see [appimage.org](https://appimage.org/)) or standalone archives (for example Firefox, Blender, Thunderbird...).*

--------

### How is this site different from other sites that list AppImage packages?
*This catalog aims to survey and list all the AppImages and autonomous programs, and aims to provide a centralized point where you can document yourself on individual apps and where you can easily reach the URLs to the sources, both through the pages dedicated to each app and by reading the "installation scripts".*

*Yeah, each app has its own installation script, PKGBUIL style, but with an alternative package manager named "**[AM](https://github.com/ivan-hc/AM)**", which works like the more classic APT, PacMan/YAY, DNF... and which can therefore place them in specific paths of the filesystem , like any program, and allows updates via a system of scripts called "AM-updater". If an app can't update itself, the dedicated "AM-updater" script will use an application-specific method to always update your favorite apps to the latest version. FOR REAL!*

*This catalog is open source. You can edit its pages, update them and see the sources clearly, as a "wiki".*

#### About other catalogs
*While I recognize the role they have had so far in supporting the diffusion of AppImage as a packaging format, through the years, as a former user, I would like to underline what led me to open an alternative catalogue:*
- *"appimage.github.io" is more of a tool for verifying the validity of the AppImages, but as a catalog is limited to showing only that an app exists or has existed, so many of them are no more available, many pages have no buttons to the sources and all pages have no additional information on individual apps, each page is simply a copy/paste message that says "This App is available as an AppImage..." etcetera.*
- *"appimagehub.com" publishes packages on proprietary servers of dubious transparency, the sources are not always shown, but those responsible for uploading simply declare that "they are not the developers", despite having a donation button available, effectively leading them to earning on work of others.*

*Furthermore, **none of them track updates consistently**.*

*From the aforementioned defects I understood what a catalog of portable applications should NOT do to be reliable.*

--------

## Is there a centralized repository for AppImage packages?
*This catalog is just the frontend for a database that aims to extend not only to x86_64 architecture apps listed here, but also to all others, including the latest aarch64 and the oldest i686.*

*All the installation scripts are stored in the repository of the "AM" package manager, which I have already mentioned above.*

*Click the link or the picture down below lo know more...*

<div align="center">

## *[https://github.com/ivan-hc/AM](https://github.com/ivan-hc/AM)*

[<img src="https://github.com/ivan-hc/AM/assets/88724353/671f5eb0-6fb6-4392-b45e-af0ea9271d9b">](https://github.com/ivan-hc/AM)

</div>

*The code of this Command Line Interface is available at [this link](https://github.com/ivan-hc/AM/blob/main/APP-MANAGER).*

*The [database](https://github.com/ivan-hc/AM/tree/main/programs) of "AM" does not stores packages but installation scripts, as the Arch User Repository (AUR) does with PKGBUILDs.*

*Each script points directly to a program ready to be downloaded, more often as AppImage packages, but also portable apps stored in TAR, ZIP and DEB archives, scripts, standalone binares... and in some cases a script can build on-the-fly AppImage packages in a way similar to an AUR helper using [pkg2appimage](https://github.com/AppImageCommunity/pkg2appimage) and/or [appimagetool](https://github.com/AppImage/AppImageKit).*

------------------------------------------------------------------------

# Differences between "AM" and "AppMan"
*"AM" and "AppMan" differ in how they are installed, placed and renamed in the system and how/where they install apps:*
- *"**AM**" is installed system-wide (requires `sudo`) in `/opt/am/` as "**APP-MANAGER**", with a symlink named "`am`" in `/usr/local/bin`.*
- *"**AppMan**" is portable, you need just to rename the "APP-MANAGER" script as "`appman`" and put it wherewer you want. I recommend to place it in `$HOME/.local/bin` to be used in $PATH, to be managed from other tools.*

*Both can be updated using "[Topgrade](https://github.com/topgrade-rs/topgrade)".*

------------------------------------------------------------------------

### Ownership
- *"**AM**" is owned by the user that have installed it, since other users have not read/write permissions in "/opt/am";*
- *"**AppMan**" is for all users, since it works locally, everyone can have its own apps and configurations.*

------------------------------------------------------------------------

### About "sudo" usage
- *"AppMan" can request the root password only in the very rare case in which you want to install a library;*
- *"AM" requires the root password only to install, remove apps, enable a sandbox for an AppImage, or enable/disable bash completion.*

*All options cannot be executed with "`sudo`".*

------------------------------------------------------------------------

### How apps are installed

------------------------------------------------------------------------

- *"**AM**" installs apps system wide, in `/opt` (see [Linux Standard Base](https://refspecs.linuxfoundation.org/FHS_3.0/fhs/ch03s13.html)), using the following structure:*
```
/opt/$PROGRAM/
/opt/$PROGRAM/$PROGRAM
/opt/$PROGRAM/AM-updater
/opt/$PROGRAM/remove
/opt/$PROGRAM/icons/$ICON-NAME
/usr/local/bin/$PROGRAM
/usr/local/share/applications/$PROGRAM-AM.desktop
```
*NOTE, all installation scripts used before June 28, 2024 show launchers in /usr/share/applications with suffix "AM-" instead of the "AM.desktop" extension, like this:*

```
/usr/share/applications/AM-$PROGRAM.desktop
```
*From 8 July 2024 this configuration is no longer available. Reinstall the application to get the new configuration.*

*The change to the default location for .desktop files from /usr/share/applications to /usr/local/share/applications was made to bring "AM" in line with GNU/Linux standards for installing system-wide third-party applications, see [here](https://refspecs.linuxfoundation.org/FHS_3.0/fhs/ch04s09.html).*

------------------------------------------------------------------------

- *"**AppMan**" is more flexible, since it asks you where to install the apps in your $HOME directory. For example, suppose you want install everything in "Applicazioni" (the italian of "applications"), this is the structure of what an installation scripts installs with "AppMan" instead:*
```
~/Applicazioni/$PROGRAM/
~/Applicazioni/$PROGRAM/$PROGRAM
~/Applicazioni/$PROGRAM/AM-updater
~/Applicazioni/$PROGRAM/remove
~/Applicazioni/$PROGRAM/icons/$ICON-NAME
~/.local/bin/$PROGRAM
~/.local/share/applications/$PROGRAM-AM.desktop
```
*NOTE, all installation scripts used before June 28, 2024 show the launchers with suffix "AM-" instead of the "AM.desktop" extension, like this:*
```
~/.local/share/applications/AM-$PROGRAM.desktop
```
*From 8 July 2024 this configuration is no longer available. Reinstall the application to get the new configuration.*

*The configuration file for AppMan is in `~/.config/appman` and contains the path you indicated at first startup. Changing its contents will result in changing the paths for each subsequent operation carried out with "AppMan", the apps and modules stored in the old path will not be manageable.*

*At first startup you can indicate any directory or subdirectory you want, as long as it is in your $HOME.*

------------------------------------------------------------------------

### How to use "AM" in non-privileged mode, like "AppMan"
*As already mentioned above, at "[Ownership](#ownership)" the user who installed "AM" is the sole owner, having write permissions for both /opt/am and for all installed apps.*

*However, every user of the same system is allowed to use the option `--user` or `appman`, to use "AM" as "AppMan" and to install apps locally and withour root privileges:*
```
am --user
```
*To switch "AM" back to "AM" from "AppMan Mode", use the always suggested option `--system`:*
```
am --system
```
*To perform a test and see if you are in "AppMan Mode" or not, run for example the command `am -f` to see the list of the installed apps.*

*In this video I'll install LXtask locally:*

https://github.com/ivan-hc/AM/assets/88724353/65b27cf6-edc5-4a4c-b2f9-42e8623dc76f

*NOTE: non-privileged users can update their own local applications and modules, but cannot update /opt/am/APP-MANAGER.*

*It is therefore suggested to use pure "AppMan" instead of the "AppMan Mode" of "AM".*

------------------------------------------------------------------------

| [Install "AM"/"AppMan"](#installation) | [Back to "Main Index"](#main-index) |
| - | - |

------------------------------------------------------------------------
# What programs can be installed
*"AM"/"AppMan" installs, removes, updates and manages only standalone programs, ie those programs that can be run from a single directory in which they are contained. The database aims to be a reference point where you can download all the AppImage packages scattered around the web, otherwise unobtainable, as you would expect from any package manager, through specific installation scripts for each application, as happens with the AUR PKGBUILDs, on Arch Linux. You can see all of them [here](https://github.com/ivan-hc/AM/tree/main/programs), divided by architecture.*

*NOTE that currently my work focuses on applications for [x86_64](https://github.com/ivan-hc/AM/tree/main/programs/x86_64) architecture, but it is possible to extend "AM" to all other available architectures. If you are interested, you can deliberately join this project to improve the available lists.*

*1. **PROGRAMS**, they are taken:*
- *from official sources (see Firefox, Thunderbird, Blender, NodeJS, Chromium Latest, Platform Tools...);*
- *extracted from official .deb/tar/zip packages;*
- *from the repositories and official sites of individual developers.*

*2. **APPIMAGES**, they are taken:*
- *from official sources (if the upstream developers provide them);*
- *from AppImage recipes to be compiled on-the-fly with [pkg2appimage](https://github.com/AppImage/pkg2appimage) and [appimagetool](https://github.com/AppImage/AppImageKit);*
- *from unofficial third-party developers, but only if an official release is not available.*

*3. **FIREFOX PROFILES** to run as webapps, the ones with suffix "ffwa-" in the apps list.*

*4. **THIRD-PARTY LIBRARIES**, needed if they are not provided in your distribution's repositories. These are to be installed in truly exceptional cases.*

*You can consult basic information, links to sites and sources used through the related command `am -a $PROGRAM` or `appman -a $PROGRAM`, that uses the same pages of this site.*

------------------------------------------------------------------------

| [Back to "Main Index"](#main-index) |
| - |

------------------------------------------------------------------------
# How to update all programs, for real
*One of the reasons why many users hate Appimages is because they cannot be updated. Or at least not all.*

*This project was born to dispel this myth and to solve the problem. And the solution is much more trivial than you expect.*

*There are several methods to update apps, here are the most common ones, in order of priority:*
- *the "comparison between versions" is the most widespread in the database, the version of the app installed is compared with the one present at the source, be it an official site or another site that tracks it;*
- *if an AppImage package has a .zsync file, that will be used to download binary deltas (especially useful with large files, but not very popular among developers);*
- *some portable apps are self-updatable (see Firefox and Thunderbird);*
- *if an app or script is extremely small (a few kilobytes), it is downloaded directly from scratch;*
- *in rare cases, if a file .zsync is broken, we use [appimageupdatetool](https://github.com/AppImage/AppImageUpdate);*
- *in some cases, the apps have a fixed version, both due to the developers' choices to abandon a portable package in favor of other more common platforms, and because a software is no longer developed.*

### How to update all installed apps
*Option `-u` or `update` updates all the installed apps and keeps "AM"/"AppMan" in sync with the latest version and all latest bug fixes.*

https://github.com/ivan-hc/AM/assets/88724353/f93ca782-2fc6-45a0-a3f2-1fba297a92bf

*1. To update only the programs, use `am -u --apps` / `appman -u --apps`*
*2. To update just one program, use `am -u $PROGRAM` / `appman -u $PROGRAM`*
*3. To update all the programs and "AM"/"AppMan" itself, just run the command`am -u` / `appman -u`*
*4. To update only "AM"/"AppMan" and the modules use the option `-s` instead, `am -s` / `appman -s`*

*NOTE, non-privileged users using "AM" in "AppMan Mode" cannot update /opt/am/APP-MANAGER (points 3 and 4). See "[How to use AM in non-privileged mode, like AppMan](#how-to-use-quotamquot-in-non-privileged-mode-like-quotappmanquot)".*

### How to update everything using "Topgrade"
*Keeping your system up to date usually involves invoking multiple package managers. This results in big, non-portable shell one-liners saved in your shell. To remedy this, Topgrade detects which tools you use and runs the appropriate commands to update them.*

*Install the "topgrade" package using the command*
```
am -i topgrade
```
or
```
appman -i topgrade
```

*Visit [github.com/topgrade-rs/topgrade](https://github.com/topgrade-rs/topgrade) to learn more.*

*NOTE, "AppMan" users must install `appman` in ~/.local/bin to allow updates via Topgrade. See "[How to install AppMan](#how-to-install-quotappmanquot)".*

------------------------------------------------------------------------

| [Back to "Main Index"](#main-index) |
| - |

------------------------------------------------------------------------
# Installation
*This section explains how to install "AM" or "AppMan".*

*If you don't know the difference, please read "[Differences between "AM" and "AppMan"](#differences-between-quotamquot-and-quotappmanquot)" first.*

#### Core dependences
*Below are the **essential system dependencies** that you must install before proceeding:*
- *"`coreutils`" (contains "`cat`", "`chmod`", "`chown`"...);*
- *"`curl`", to check URLs;*
- *"`grep`", to check files;*
- *"`sed`", to edit/adapt installed files;*
- *"`wget`" to download all programs and update "AM"/"AppMan" itself.*

#### Dependency only for "AM"
- *"`sudo`", required by "AM" to install/remove programs, sandbox AppImages and enable/disable bash-completion.*

*NOTE: use "AppMan" for non privileged use or if you prefer to gain administration privileges using alternative commands such as `doas` or similar.*

#### Extra dependences (recommended)
*The following are optional dependencies that some programs may require:*
- *"`binutils`", contains a series of basic commands, including "`ar`" which extracts .deb packages;*
- *"`unzip`", to extract .zip packages;*
- *"`tar`", to extract .tar* packages;*
- *"`zsync`", about 10% of AppImages depend on this to be updated.*

### Proceede

- [How to install "AM"](#how-to-install-quotamquot)
- [How to install "AppMan"](#how-to-install-quotappmanquot)


## How to install "AM"
*"**AM**" is ment to be installed at system level to manage apps.*

*The script "[INSTALL](https://github.com/ivan-hc/AM/blob/main/INSTALL)" is the one that take care of this.*

#### Using "Wget"
```
wget https://raw.githubusercontent.com/ivan-hc/AM/main/INSTALL
chmod a+x ./INSTALL
sudo ./INSTALL
```
*or directly*
```
wget https://raw.githubusercontent.com/ivan-hc/AM/main/INSTALL && chmod a+x ./INSTALL && sudo ./INSTALL
```

#### Using "GIT"
```
git clone https://github.com/ivan-hc/AM.git
cd AM
chmod a+x INSTALL
sudo ./INSTALL
```

### Structure of the "AM" installation
*In both cases, the "INSTALL" script will create:*
- *the script "/opt/am/APP-MANAGER"*
- *the script "/opt/am/remove" (to remove "AM" using the command `am -R am`)*
- *the directory "/opt/am/.cache" (where all processes will been executed)*
- *the directory "/opt/am/modules" (containing the .am modules for the non-core options)*
- *the symlink "/usr/local/bin/am" for "/opt/am/APP-MANAGER"*

*NOTE, if you don't feel comfortable having to always use root permissions, the installation method for "AppMan" is totally different. If you are interested, go [to the next paragraph](#how-to-install-quotappmanquot), else [Back to "Main Index"](#main-index) or see "[all the available options" at [github.com/ivan-hc/AM#usage](https://github.com/ivan-hc/AM#usage).*

------------------------------------------------------------------------
## How to install "AppMan"
*"**AppMan**" can be used in different places, being it portable.*

*However, to be easily used its recommended to place it in your local "$PATH", in `~/.local/bin`.*

#### Use "AppMan" in "$PATH"
*To do so, you must first enable that "$PATH":*
- *add `export PATH=$PATH:$(xdg-user-dir USER)/.local/bin` in the ` ~/.bashrc`*
- *create the directory `~/.local/bin` if it is not available*

*To do all this quickly, simply copy/paste the following command:*
```
mkdir -p ~/.local/bin && echo 'export PATH=$PATH:$(xdg-user-dir USER)/.local/bin' >> ~/.bashrc && wget https://raw.githubusercontent.com/ivan-hc/AM/main/APP-MANAGER -O appman && chmod a+x ./appman && mv ./appman ~/.local/bin/appman
```
#### Use "AppMan" in "Portable Mode"
*"AppMan" can run in any directory you download it, copy/paste the following command to download "APP-MANAGER", rename it to `appman` and make it executable:*
```
wget https://raw.githubusercontent.com/ivan-hc/AM/main/APP-MANAGER -O appman && chmod a+x ./appman
```

### Structure of the "AppMan" installation
*Unlike "AM" which needs to be placed in specific locations, "AppMan" is portable. The modules and directories will be placed in the directory you chose:*
- *the script "appman" is wherever you want*
- *the directory "$HOME/path/to/your/custom/directory/.cache" (where all processes will been executed)*
- *the directory "$HOME/path/to/your/custom/directory/modules" (containing the .am modules for the non-core options)*
- *the configuration file "$HOME/.config/appman/appman-config" (the only fixed directory)*

------------------------------------------------------------------------

| [Back to "Main Index"](#main-index) |
| - |

------------------------------------------------------------------------
# Uninstall
- *To uninstall "AM" just run the command `am -R am`*
- *To uninstall "AppMan" just remove it and the directory `$HOME/.config/appman`*

*Note, before you remove your CLI, use the option `-R` to remove the apps installed using the following syntax:*
```
am -R {PROGRAM1} {PROGRAM2} {PROGRAM3}...
```
or
```
appman -R {PROGRAM1} {PROGRAM2} {PROGRAM3}...
```

*to have a list of the installed programs use the option `-f` or `files` (syntax `am -f` or `appman -f`).*

*See also "[How to update or remove apps manually", at [github.com/ivan-hc/AM#how-to-update-or-remove-apps-manually](https://github.com/ivan-hc/AM#how-to-update-or-remove-apps-manually).*

------------------------------------------------------------------------
### External links index
------------------------------------------------------------------------
*All the guides listed here are available at [***github.com/ivan-hc/AM***](https://github.com/ivan-hc/AM)*

[Usage (all the available options)](https://github.com/ivan-hc/AM#usage)

[Guides and tutorials](https://github.com/ivan-hc/AM#guides-and-tutorials)
- [Install applications](https://github.com/ivan-hc/AM#install-applications)
- [List the installed applications](https://github.com/ivan-hc/AM#list-the-installed-applications)
- [List and query all the applications available on the database](https://github.com/ivan-hc/AM#list-and-query-all-the-applications-available-on-the-database)
- [Update all](https://github.com/ivan-hc/AM#update-all)
- [Backup and restore installed apps using snapshots](https://github.com/ivan-hc/AM#backup-and-restore-installed-apps-using-snapshots)
- [Remove one or more applications](https://github.com/ivan-hc/AM#remove-one-or-more-applications)
- [Convert Type2 AppImages requiring libfuse2 to Type3 AppImages](https://github.com/ivan-hc/AM#convert-type2-appimages-requiring-libfuse2-to-type3-appimages)
- [Integrate local AppImages into the menu by dragging and dropping them](https://github.com/ivan-hc/AM#integrate-local-appimages-into-the-menu-by-dragging-and-dropping-them)
  - [How to create a launcher for a local AppImage](https://github.com/ivan-hc/AM#how-to-create-a-launcher-for-a-local-appimage)
  - [How to remove the orphan launchers](https://github.com/ivan-hc/AM#how-to-remove-the-orphan-launchers)
  - [AppImages from external media](https://github.com/ivan-hc/AM#appimages-from-external-media)
- [How to use "AM" in non-privileged mode, like "AppMan"](https://github.com/ivan-hc/AM#how-to-use-am-in-non-privileged-mode-like-appman)
- [Sandbox an AppImage](https://github.com/ivan-hc/AM#sandbox-an-appimage)
  - [How to enable a sandbox](https://github.com/ivan-hc/AM#how-to-enable-a-sandbox)
  - [How to disable a sandbox](https://github.com/ivan-hc/AM#how-to-disable-a-sandbox)
  - [Sandboxing example](https://github.com/ivan-hc/AM#sandboxing-example)
  - [About Aisap sandboxing](https://github.com/ivan-hc/AM#about-aisap-sandboxing)
- [How to enable bash completion](https://github.com/ivan-hc/AM#how-to-enable-bash-completion)
- [How to update or remove apps manually](https://github.com/ivan-hc/AM#how-to-update-or-remove-apps-manually)
- [Downgrade an installed app to a previous version](https://github.com/ivan-hc/AM#downgrade-an-installed-app-to-a-previous-version)
- [Create and test your own installation script](https://github.com/ivan-hc/AM#create-and-test-your-own-installation-script)
  - [Option Zero: "AppImages"](https://github.com/ivan-hc/AM#option-zero-appimages)
  - [Option One: "build AppImages on-the-fly"](https://github.com/ivan-hc/AM#option-one-build-appimages-on-the-fly)
  - [Option Two: "Archives and other programs"](https://github.com/ivan-hc/AM#option-two-archives-and-other-programs)
  - [Option Three: "Firefox profiles"](https://github.com/ivan-hc/AM#option-three-firefox-profiles)
  - [How an installation script works](https://github.com/ivan-hc/AM#how-an-installation-script-works)
  - [How to test an installation script](https://github.com/ivan-hc/AM#how-to-test-an-installation-script)
- [Third-party databases for applications (NeoDB)](https://github.com/ivan-hc/AM#third-party-databases-for-applications-neodb)

[Troubleshooting](https://github.com/ivan-hc/AM#troubleshooting)
- [An application does not work, is old and unsupported](https://github.com/ivan-hc/AM#an-application-does-not-work-is-old-and-unsupported)
- [Cannot download or update an application](https://github.com/ivan-hc/AM#cannot-download-or-update-an-application)
- [Cannot mount and run AppImages](https://github.com/ivan-hc/AM#cannot-mount-and-run-appimages)
- [Spyware, malware and dangerous software](https://github.com/ivan-hc/AM#spyware-malware-and-dangerous-software)
- [Stop AppImage prompt to create its own launcher, desktop integration and doubled launchers](https://github.com/ivan-hc/AM#stop-appimage-prompt-to-create-its-own-launcher-desktop-integration-and-doubled-launchers)
- [The script points to "releases" instead of downloading the latest stable](https://github.com/ivan-hc/AM#the-script-points-to-releases-instead-of-downloading-the-latest-stable)
- [Wrong download link](https://github.com/ivan-hc/AM#wrong-download-link)

------------------------------------------------------------------------

| [Back to "Main Index"](#main-index) |
| - |

------------------------------------------------------------------------
# Related projects
#### External tools and forks used in this project
- [aisap](https://github.com/mgord9518/aisap), sandboxing solutions for AppImages
- [appimagetool/go-appimage](https://github.com/probonopd/go-appimage), get rid of libfuse2 from your AppImages
- [pkg2appimage](https://github.com/AppImage/pkg2appimage), create AppImages on the fly from existing .deb packages
- [repology](https://github.com/repology), the encyclopedia of all software versions

#### My other projects
- [AppImaGen](https://github.com/ivan-hc/AppImaGen), easily create AppImages from Ubuntu PPAs or Debian using pkg2appimage and appimagetool;
- [ArchImage](https://github.com/ivan-hc/ArchImage), create AppImages for all distributions using Arch Linux packages. Powered by JuNest;
- [Firefox for Linux scripts](https://github.com/ivan-hc/Firefox-for-Linux-scripts), easily install the official releases of Firefox for Linux;
- [My AppImage packages](https://github.com/ivan-hc#my-appimage-packages) the complete list of packages managed by me and available in this database;
- [Snap2AppImage](https://github.com/ivan-hc/Snap2AppImage), try to convert Snap packages to AppImages.

------------------------------------------------------------------------

###### *You can support me and my work on [**ko-fi.com**](https://ko-fi.com/IvanAlexHC) and [**PayPal.me**](https://paypal.me/IvanAlexHC). Thank you!*

--------

*© 2020-present Ivan Alessandro Sala aka 'Ivan-HC'* - I'm here just for fun! 

------------------------------------------------------------------------

| [**ko-fi.com**](https://ko-fi.com/IvanAlexHC) | [**PayPal.me**](https://paypal.me/IvanAlexHC) | [Install "AM"/"AppMan"](#installation) | ["Main Index"](#main-index) |
| - | - | - | - |

------------------------------------------------------------------------

