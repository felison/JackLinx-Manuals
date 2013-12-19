# JackLinx Administrator Manual

# 1 System Requirements

JackLinx has been developed with modest legacy hardware in mind.
The target audience for JackLinx is the underfunded educational institution anywhere on the globe.
The typical set of hardware would include obsolete or refurbished general office desktop systems.
Pentium 4 and 500 Mb RAM would be a minimum.

## System requirements single workstation

- Any system suited to run Ubuntu 12.04
- Operating system: Xubuntu or Lubuntu 12.04
- All JackLinx dependencies (that is the very apps that are managed and controlled) are sourced from the Ubuntu 12.04 repository.
- Window manager: Preferably a lean window manager like XFCE or LXDE
- Screen resolution: The JackLinx geometry presets have been designed for XVGA (1280 x 1024)

## System requirements multiseat networked classroom setup

- One PC per student with 100 Mbps network card
- Router with DHCP server
- Ethernet switch 100 Mbps
- Wired or wireless ethernet network
- Optional: internet gateway
- Optional: Network Attached Storage (NAS)

# 2 Getting JackLinx and JackPakx

JackLinx and JackPakx are available from GitHub:

[https://github.com/felison](https://github.com/felison)

There are two separate packages to obtain and install: 
- one package for the platform called JackLinx
- one package for the content called JackPakx

## 2.1 Getting the JackLinx and JackPakx packages

### Getting the latest source code and build a Debian package yourself.
You can get the latest development files from GitHub. The are binaries that are arranged as an image that finally has to be installed in your system root directory. You will have to build a debian package yourself.

- Downloading from GitHub as zip file
- Cloning from github

### Preparing the source for making Debian packages

- Put all directories and files in a directory called ./jacklinx respectively ./jackpakx
- Remove the (hidden) directory .git
- Remove README.md
- Remove LICENSE.md
- Make sure you end up with  directory images identical to these:


in case of JackLinx:
```
./jacklinx/DEBIAN
./jacklinx/etc
./jacklinx/opt
./jacklinx/usr

```

in case of JackPakx:

```
./jackpakx/DEBIAN
./jackpakx/opt

```

Now run the following command to make a Debian package:

in case of JackLinx:

```
dpkg -b ./jacklinx jacklinx-yymmdd-time.deb
```
in which you substitute yymmdd for actual year-month-date and time for the time of the day.

You should end up with a debian package in your home directory:

```
./jacklinx-yymmdd-time.deb

```
in case of JackPakx:

```
dpkg -b ./jackpakx jackpakx-yymmdd-time.deb
```
in which you substitute yymmdd for actual year-month-date and time for the time of the day.

You should end up with a debian package in your home directory:

```
./jackpakx-yymmdd-time.deb

```

## 2.2 Getting precompiled Debian packages

Precompiled Debian packages and installation script can be downloaded from Box.net:
[https://app.box.com/s/fzif6j3ekaqzpb5xchcr](https://app.box.com/s/fzif6j3ekaqzpb5xchcr)

You will find there:

- Script for installing dependencies
- Debian package for installing JackLinx
- Debian package for installing JackPakx

# 3 Installing JackLinx and JackPakx Debian packages

## 3.1 Dependencies
By nature and design JackLinx uses and controls a set of ready made of the shelf software applications.
Normally in a debian package these would have been listed as dependecies and would be installed autimatically by adebian package installer. We have chosen however to not let the JackLinx debian package do the heavy lifting of installing all its "dependencies".
You will have to  install the component applications in a separate process.
Either manually using apt-get install , Aptitude or any other package installer.

The list of packages that are needed and used is:

#### alacarte pulseaudio-module-jack devilspie wmctrl smbfs 9menu jackd qjackctl mididings jack-mixer qmidiroute qmidinet vmpk qsynth meterbridge kmidimon kmetronome gnome-mplayer mscore pianobooster qtractor hydrogen mixxx xsysinfo gmidimonitor patchage stopwatch aconnectgui jack-rack sysinfo rox-filer

Optionally this script can be used to install the packages from the command line interface:

```
#!/bin/bash
# JackLinx
# Script to install dependencies for JackLinx platform

sudo apt-get install alacarte pulseaudio-module-jack devilspie wmctrl smbfs 9menu jackd qjackctl mididings jack-mixer qmidiroute qmidinet vmpk qsynth meterbridge kmidimon kmetronome gnome-mplayer mscore pianobooster qtractor hydrogen mixxx xsysinfo gmidimonitor patchage stopwatch aconnectgui jack-rack sysinfo rox-filer

```
## 3.2 Installing the JackLinx platform

Use Gdebi package installer to install either the self compiled or ready made packages.

In case the package sits in your home directory and is called jacklinx-131208-1915.deb run the follwing command from the command line:

```

sudo gdebi ./jacklinx-131208-1915.deb

```
Alternatively: 

1. Use your file manager to browse to the debian package.
2. Right click and open with Gdebi to install the package.

## 3.3 Installing the JackPakx content package

The same installation procedure applies for the JackPakx debian package. 

# 4 Starting the JackLinx application

Options to start JackLinx:

At installation a jacklinx.desktop file is installed in /usr/share/applications/jacklinx.desktop
Under XFCE - and perhaps other window managers) - this desktop menu item will appear under category Education.

Alternatively: Open a terminal and run the command: 

```
/opt/jacklinx/bin/app-start-jacklinx.sh

```
Alternatively: Make a desktop starter (fx using Alacarte):
- to start JackLinx point to: 

```
/opt/jacklinx/bin/app-start-jacklinx.sh

```
- to include the JackLinx icon point to: 

```
/opt/jacklinx/share/graphics/jacklinx.png
```

# 5 Setting up student workstations:

1. Log in as user
2. Start JackLinx by clicking 'Menu' / 'Educational' / 'JackLinx'.
3. In JackLinx go to 'General Menu' / 'Advanced'
4. Click the menu item 'Set Application Presets' to load the application presets.
5. Click the menu item 'Set Devilspie Presets'. to load the window geometry presets.


# 6 Networking JackLinx

Installing JackLinx:

- Log in as admin or superuser (sudo user)
- Install the debian package jacklinx.deb using GDebi package installer.
- Note: The Debian package does not (yet) meet the official Debian policy requirements and will be rejected by Ubuntu Installer.
- However, after installation with GDebi JackLinx is listed in the Synaptic package manager.

# 7 Clustering JackLinx

More to come ...
