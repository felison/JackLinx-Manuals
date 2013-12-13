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


# 8 Safety #

## Child Safety ##

When JackLinx is deployed in an unprotected environment anyone can compromise the ehical and moral integrity of the learning environment.
Several - not mutual excluding - approaches can lead to protection and will be discussed in detail below:

- A - Blocking internet access completely. This is the most radical and effective way to control dangers from the World Wide Web.

- B - Restricting internet access by selective external firewalling and filtering out malicious sites.

- C - Restricting internet access by selective internal parental control programs.

- D - Selectively filtering, restricting and enabling the use of network protocols.

- E - Enforcing authenticated use and monitoring and logging unethical and immoral uses.
- F - Selective installation of programs, options and functions to restrict users.
- G - Restricting users by user policy.
- H - Restricting users by BIOS settings.
- I - Frequently and automatically cleaning up and restoring systems to defaults.
- J - Physically cripling and locking down features and options to restrict users.
- K - Administering JackLinx stations in a Microsoft System Center 2012 environment.

### Approach A - Pulling the internet plug.

This radical approach involves complete lockout of internet access or strict firewalling. Obviously this can be achieved by literally pulling the plug of internet access.

### Approach B1 - External firewalling and filtering - Blacklisted sites.

In most educational institutions an institution-wide control policy will be in place to restrict access to malicious internet sites. This can be applied for only registered authenticated users and/or for anononymous guest users. Alternatively - if a working institution-wide filter is not in place - one could set up a gatewayserver for the local JackLinx subnet with a content filter.
Popular Linux content filters are:
-     Dansguardian
-     Squid

Both contentfilters can work with the (commercial) URLBlackList that blacklists over 3 million websites including sites related to a.o. shopping, email, weapons, adult content etc. etc.

### Approach B2 - BYOD-Bring-Whatever-Device-Connects-to-the-Internet

In some institutions wired or wireless internet only access is provided for anonymous guests under a Bring-Your-Own-Device (BYOD) scheme. Microsoft SCCM 2012 is an example of a network administration manager that allows for specific models of BYOD policies. One such Microsoft BYOD education policy model is called Bring-Whatever-Device-Connects-to-the-Internet. See this Microsoft article about BYOD policies in education.
As JackLinx by default accesses only safe internet sites such a scheme would enable full JackLinx operation.
Technically a fully isolated subnet of JackLinx nodes connected to the wireless network through a single wireless point-to-point ethernet bridge would function as one single BYOD device.

### Approach C  - Parental control

A standard home and family solution involves installation and configuration of parental control programs. Normally these programs involve a parent login account from where privileges and restrictions for child login account can be configured.
The access control architecture of JackLinx parallels this idea: There is an admin/teacher account from where privileges and restriction fro a student account can be set.
In case of the use of parental control software the admin/teacher account would double as the parent account and the anonymous student account would double as an anonymous child account.
Of the shelf parental control software is available.

### Approach D - Limiting the use of networking protocols and ports.

JackLinx relies on three networking protocols, each using their own specific port ranges:

- IP-ethernet for accessing WAN or LAN servers serving HTML content.
- UDP protocol for exchanging midi-over-lan signals with other JackLinx stations.
- Universal-Plug-and-Play (UPNP) for accessing XBMC servers on Network Attached Storage (NAS)

This means for example that potentially dangerous programs that rely on internet chat relay protocol can be lockedout by blocking the protocol and the required port ranges.

### Approach E - Authenticated personal login and logging user activity.

This approach would involve a central LDAP authentication server and enforcing login against this server at each workstation. This is a standard arrangement in the Linux world.
This approach enables logging of user activity which in turn enables forensic detection after the act to identify misuse.
Authentication against a server can still include approaches B and C.

### Approach F - Selectively installing programs, functions, features and options.

The central idea is to only install those packages and programs tha are really needed and avoid programs that can create unwanted exposure. Minimal installation of functions needed for using JackLinx:

- A minimal installation of Operating System
- Only installing the applications and packages needed for running JackLinx
- Functionalities that are not needed and can create exposure to malicious user action:

File managers that give access to external drives and system files.
Command line terminals that enable controlling the system by commands
Texting, editing and chatting programs that enable the creation and exchange of malicious text. Image editing programs that enable the creation of malicious imagery. Any configuration managers that enable tweaking settings and configurations.

### Approach G - Digitally restricting users by user policy.

In a typical Linux environment different users can be given different priviliges and restrictions. Normally a admin - or superuser -  account of highest level has the privilege to set and control provileges for lower leveluser accounts. This is the default approach used in JackLinx to protect software integrity. It parallels the parental control approach.

In a default JackLinx system there would be 2 user accounts:
The almighty admin/teacher (sudo) account with super-user privileges.
The anonymous student account, for which privileges and restrictions are set by the admin/teacher. The standard Debian/Ubuntu system allows for various standard privileges/restrictions to be set for the user account.

### Approach H - Restricting and disabling functions by BIOS settings.
The use of CD-ROM drives and USB drives can be restricted in the BIOS settings. This assumes that the BIOS configuration is protected by a login andpassword.

### Approach I - Frequently cleaning and resetting systems to defaults.
Users can change settings and configurations. Users can edit and store files.
With the use of automated scripts and scheduled cronjobs traces of user activity can be deleted and default configurations can be reset to default. 

### Approach J - Physically locking down functions and features.
Physical system components like CD-ROM drive and or USB connectors can be removed or disabled.
In a JackLinx system the CD-ROM drive would only be needed for installation of the operating system. Thus, after installation of the operating system  theCD-ROM drive unit could be removed from te system. The user has no possibilty to use the CD-REOM drive for viewing malicious content on f.x. DVDs.
Similarly a USB connector can be disabled by filling it with glue or resin. The user has no way of accessing a USB datastick with malicious content.

### Approach K - JackLinx in a Microsoft SCCM 2012 environment.

The latest 2012 version of Microsoft System Center Control Manager (SCCM 2012) allows for the centralized administration and control of Linux operated workstations. Specifically Ubuntu 12.04 LTS is supported.
Administering Linux machines would require a piece of Microsoft software to be installed on each Linux machine that takes care of communications with the SCCM 2012 administration console. Deploying JackLinx within such a framework would result in certain security advantages that will have to be detailed. At least one of the results would bethat the central admin can monitor which software packages are installed on the system.Practical integration of Linux nodes in the SCCM 2012 framework is discussed here and here.



