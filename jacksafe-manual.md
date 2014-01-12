# JackSafe - Manual

The JackSafe Package is a student safety add-on for Jacklinx. It can be used as an active component in a dumbed down restricted JackLinx workstation.

The primary concern with child safety is to restrict access to options to do indecent things or to be exposed to indecency.

To do this you can make a child safe embedded kiosk mode installation with:
- a minimal operating system: Debian Mini
- a guest user with restricted privileges
- a minimal window  manager: Openbox
- no desktop
- a minimal set of applications: limited to the applications needed by JackLinx
- a minimal set of libraries: limited to those needed by the Jacklinx applications.
- a minimal user menu: limited to the menu items needed for using JackLinx
- automatic reset of user configurations: user intervention is frequently erased by a root cronjob.


# Safety effect of this configuration
The net effect of these measures will be an installation comparable to a public internet kiosk like Webconverger or a standalone media player installation like XBMC. These type of installations are characterized by a extremely limited set of buttons, menu elements or control elements for user intervention. Often configurations are automatically reset to default at logon or shutdown. In effect these dumbed down installations make a desktop computer into a specialized tool with embedded software. Embedded means: The user controls the software by physical buttons, a limited touchscreen or a webinterface. When limited to essential menu-buttons a dumbed down desktop works in the same way.

Of course - contrary to a real embedded system - any user can reach the command line interface by hitting ALT-CTRL-F1. But even then the hacker would need a admin/root password to do anything indecent. 

# Install minimal operating system
Minimal Debian or Ubuntu server.
No extra software installed.

# Create restricted users
- root
- jackuser

# Install OpenBox as window manager

Install openbox as root:

```
apt-get install openbox
```

This process will install:
- xorg - x-server
- lightdm - graphical login manager
- openbox - window manager

After reboot you will be presented with the LightDM graphical login screen that only shows Openbox as an option. 

# Minimal set of applications: Install JackLinx dependencies

As root: Use the script provided.
This script not only installs the JackLinx applications but also all related dependencies. These include all Gnome libraries. As a result the Gnome desktop becomes one of the desktop options in the login screen.
As we do not wsnt the user to be able to choose Gnome we have to delete Gnome from the desktop options list:

# Configure restriction of window/desktop managers to OpenBox.

To make sure that OpenBox will be the only desktop option systemwide we have to remove all other desktops - if installed at all - from the desktop option list:

As root: Use an editor to open:

```
/usr/share/xsessions
```

Delete all entries in the file xsessions except OpenBox.

Please note: The installation of the graphical applications needed by JackLinx will attract and install a large set of libraries from the KDE and Gnome desktop repositories. These libraries are needed for the proper functioning of the graphical interfaces of these applications. It does not mean however that the KDE or Gnome desktops as such are being installed.


# Restrict menu items in OpenBox user menu.
By default OpenBox shows all available Debian applications in its menu. We can systemwide restrict the options by deleting menuitems from the menu configuration file:

As root open for editing the file:

```
/etc/xdg/openbox/menu.xml
```
Delete all unwanted menu-items or replace the configuration file *menu.xml* with the provided JackSafe master.
You might choose to save the original file *menu.xml* as *menu-backup.xml*.

# Automatic reset of user directory - *under development*

Install cronjob to reset default homedirectory.

Use rsync to remove added stuff and restore changed stuff.

Source dir = /opt/jacklinx/usr/master
Destination directory = ./home/jackuser



 



