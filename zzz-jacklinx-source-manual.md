# JackLinx Manual #

## 1.1 Introduction ##

# Concept

JackLinx is a mash-up application: no new code, no new applications, no new functions.
JackLinx is mixing the best of existing stuff into a practical and hopefully easy to use music learning environment for children and young students.

# Design

# Prototype

### JackLinx as a solution for the music classroom

JackLinx is an open source music learning environment for children and young music students.

It is geared to practical music making and creative group activity. 

JackLinx makes full use of a wide range of musical styles, multimedia, learning material and music applications.

JackLinx is a full fledged computer musiclab made easy and economical.

#### JackLinx Platform: Musiclab - Learning Environment - Music Recording Studio - Digital Bandstand - Multiple Instruments - Network Orchestra.

JackLinx uses existing Linux audio and music applications and integrates these into a coherent and logically arranged music learning platform.

#### JackLinx Content Packages: Songs - Backing Tracks - Playalongs - Lessons - Multimedia - Courses - Scores - Assignments.

A series of music lessons rich in multimedia content is provided.

####Economy: Open Source Software and Content - Low hardware requirements.

The JackLinx Platform is open source software and builds on open source software.

The JackLinx Content Package builds on open content that is freely available on the internet.

JackLinx can be used on legacy and refurbished general office hardware.

#### Safety: Guided and controlled access to educational activities.

Measures and techniques are suggested and supported for controlling and locking down access to undesired options and content to ensure compatibility with your safety policies and the reliable and safe deployment of JackLinx in your educational setting.

####You are welcome to use JackLinx as an obvious solution for the music curriculum in your school ...

### JackLinx as a Linux Audio Session Manager ###

JackLinx is a Linux Audio Session Manager.
Other Linux audio session managers are a.o:
- Ladish
- Non Session Manager
- Chino

An overview of Linux Audio Sessions Managers is found here:
[http://lwn.net/Articles/533594/](http://lwn.net/Articles/533594/)

What sets JackLinx apart from other session managers is the fact that JackLinx has been explicitly designed for the music classroom where children from 6 to 16 are beint taught music under the guidance of a music teacher.

## 1.2 Screenshots ##

### Desktop 1 - Musical Performance ###
![](http://i1178.photobucket.com/albums/x378/felison1/desktop-1-populated.jpeg)

### Desktop 2 - Patching ###
![](http://i1178.photobucket.com/albums/x378/felison1/desktop-2.jpeg)

### Desktop 3 - Synthesizers ###
![](http://i1178.photobucket.com/albums/x378/felison1/desktop-3.jpeg)

### Desktop 4 - Effects ###
![](http://i1178.photobucket.com/albums/x378/felison1/desktop-4.jpeg)

### Desktop 5 - Recording
![](http://i1178.photobucket.com/albums/x378/felison1/desktop-5-populated.png)

## 1.3 Features ##

- Open Source.
- Integrating quality Linux Audio and Music Applications
- Easy to use framework for controlling complex setups.
- Play music using keyboard or USB controller
- Play melody, chords, bass.
- Choose from 128 standard midi instrumental sounds.
- Play together in a multi instrument band over the network
- Mix your own keyboard playing with backing tracks.
- Mix your own keyboard playing with music tracks played from the internet
- Play together in a band against a common backing track.
- Make your own personal monitor mix while playing band over the network.
- Test your sight reading and keyboard playing with integrated PIanoBooster.
- Record your solo and bandwork with integrated sequencer QSynth.
- Attach external USB midi keyboard controllers and drumpads.
- Perform with your network band over the teacher console and classroom PA system

### Beginner solo work

- Play music using the computer keyboard or attached USB midi keyboard.
- Learn to play songs reading inscluded onscreen musical scores.
- Learn to play songs following included instructional videos.
- Learn to play songs playing along with included backing tracks.
- Learn to play songs playing along with Youtube videos or other webcontent.
- Play chords with one finger using the One Finger Chord System
- Perform for a small audience playing over the PC loudspeaker
- Perform for the whole class playing over the classroom PA system

### Advanced solo work

- Boost your piano skills with Piano Booster.
- Activate various effects like reverb and flanger.
- Record your solo performance with a sequencer
- Edit, master and mixdown your work.

### Beginner Band work

- Play band together with classmates over the local network.
- Play band with headphones. Split a class of 24 students up in 6 isolated bands of 4.
- Play different musical parts in your band: guitar, piano, bass and drums.
- Play with your network ensemble along a common backing track.
- Make you own personal monitor mix of the different parts in the network band.
- Perform for a small audience playing over the PC loudspeaker
- Perform for the whole class playing over the classroom PA system

### Advanced band work

- Play four part ensemble music reading included onscreen scores: soprano, alto, tenor, bass.
- Mix the audio output of multiple bands (sections) into a larger orchestra.
- Activate various effects like reverb and flanger.
- Record your band performance with a sequencer.
- Edit, master and mixdown your work.


## 2.1 System Requirements

JackLinx has been developed with modest legacy hardware in mind.
The target audience for JackLinx is the underfunded educational institution anywhere on the globe.
The typical set of hardware would include obsolete or refurbished general office desktop systems.
Pentium 4 and 500 Mb RAM would be a minimum.

### System requirements single workstation

- Any system suited to run Ubuntu 12.04
- Operating system: Xubuntu or Lubuntu 12.04
- All JackLinx dependencies (that is the very apps that are managed and controlled) are sourced from the Ubuntu 12.04 repository.
- Window manager: Preferably a lean window manager like XFCE or LXDE
- Screen resolution: The JackLinx geometry presets have been designed for XVGA (1280 x 1024)

### System requirements multiseat networked classroom setup

- One PC per student with 100 Mbps network card
- Router with DHCP server
- Ethernet switch 100 Mbps
- Wired or wireless ethernet network
- Optional: internet gateway
- Optional: Network Attached Storage (NAS)


## 2.2 Getting JackLinx and JackPakx

JackLinx and JackPakx are available from GitHub:

[https://github.com/felison](https://github.com/felison)

There are two separate packages to obtain and install: 
- one package for the platform called JackLinx
- one package for the content called JackPakx

### 2.2.1 Getting the JackLinx and JackPakx packages

#### Getting the latest source code and build a Debian package yourself.
You can get the latest development files from GitHub. The are binaries that are arranged as an image that finally has to be installed in your system root directory. You will have to build a debian package yourself.

- Downloading from GitHub as zip file
- Cloning from github

#### Preparing the source for making Debian packages

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

### 2.2.2 Getting precompiled Debian packages

Precompiled Debian packages and installation script can be downloaded from Box.net:
[https://app.box.com/s/fzif6j3ekaqzpb5xchcr](https://app.box.com/s/fzif6j3ekaqzpb5xchcr)

You will find there:

- Script for installing dependencies
- Debian package for installing JackLinx
- Debian package for installing JackPakx

## 2.3 Installing JackLinx and JackPakx Debian packages

### 2.3.1 Dependencies
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
### 2.3.2 Installing the JackLinx platform

Use Gdebi package installer to install either the self compiled or ready made packages.

In case the package sits in your home directory and is called jacklinx-131208-1915.deb run the follwing command from the command line:

```

sudo gdebi ./jacklinx-131208-1915.deb

```
Alternatively: 

1. Use your file manager to browse to the debian package.
2. Right click and open with Gdebi to install the package.

### 2.3.3 Installing the JackPakx content package

The same installation procedure applies for the JackPakx debian package. 

## Starting the JackLinx application

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

## Setting up student workstations:

1. Log in as user
2. Start JackLinx by clicking 'Menu' / 'Educational' / 'JackLinx'.
3. In JackLinx go to 'General Menu' / 'Advanced'
4. Click the menu item 'Set Application Presets' to load the application presets.
5. Click the menu item 'Set Devilspie Presets'. to load the window geometry presets.


## 2.4 Networking JackLinx

Installing JackLinx:

- Log in as admin or superuser (sudo user)
- Install the debian package jacklinx.deb using GDebi package installer.
- Note: The Debian package does not (yet) meet the official Debian policy requirements and will be rejected by Ubuntu Installer.
- However, after installation with GDebi JackLinx is listed in the Synaptic package manager.

## 2.5 Clustering JackLinx

# 3.0 User Manual #

### 3.0.1 General Menu

#### Panic

The panic button send a midi reset message to the synthesizer. It stops any notes that remain hanging after closing a midi application.

#### Reset Windows

The Reset Windows button resets all open windows to their default position and geometry.

#### USB Channel

The USB Channel Menu Button opens the USB Channel Menu. With this menu you can choose the midi channel an attached USB midi controller will send messages to. Most cheap USB midi controllers send only on midi channel 1.

- Switch to Channel 02 - Soprano
- Swicth to Channel 03 - Alto
- Switch to Channel 04 - Tenor
- Switch to Channel 05 - Bass
- Switch to Channel 09 - Chords
- Switch to Channel 10 - Drums

#### Presets

This button opens the Presets Menu.

- Load presets for applications
- Load presets foor display XVGA

#### Help
#### About
#### Stop JackLinx

The Stop JackLinx Button will stop and close all JackLinx windows and processes.

### 3.0.2 Desk Switch Menu

- Desk 1 - Home - Performance Apps & Media Players CTRL-F1
- Desk 2 - Jack - JackControl & GMidiMonitor CTRL-F2
- Desk 3 - Synth - QSynth & QMidiRoute CTRL-F3
- Desk 4 - Effect - Effect Inserts CTRL-F4
- Desk 5 - Track - QTractor - Sequencer CTRL-F5
- Desk 6 - Tech - Advanced Technical Apps CTRL-F6

### 3.0.3 The persistent applications on all 6 desktops

#### VMPK - Virtual Midi Piano Keyboard

Panic

Sometimes midi notes will continue to make sound - they "hang". The panic button sends a general midi reset command to the synthsizer that stops all hanging notes.
Channel

Here you choose the midi channel that the keyboard will send messages on. The channels are the same as the channels on the mixer. You can choose a different instrument for each channel.

- Channel 02 Used for the Soprano part Routed to Mixer Strip 02-S
- Channel 03 Used for the Alto part Routed to Mixer Strip 03-A
- Channel 04 Used for the Tenor part Routed to Mxer Strip 04-T
- Channel 05 Used for the Bass part Routed to Mixer Strip 05-B
- Channel 09 Used for One Finger Chord System Routed to Mixer Strip 09-C
- Channel 10 Used for Drums Routed to Mixer Strip 10-D

Base Octave
Transpose
Velocity
Bank (Bank Select)
Program (Program Select)

#### Jack Mixer

- 02-S - Channel 02 - Soprano
- 03-A - Channel 03 - Alto
- 04-T - Channel 04 - Tenor
- 05-B - Channel 05 - Bass
- 09-C - Channel 09 - Chords -One Finger Chord System
- 10-D - Channel 10 - Drums - Percussion
- Midi - Midi apps: KMidiMon, PianoBooster
- Flsh - Flash Audio from Firefox
- Play - Media players
- Scor - MuseScore audio
- Othr - Other audio sources
- MdDn - Mix Down from QTractor
- Main - Main Audio Output


## 3.1 Desktop 1 - Musical Performance ###
![](http://i1178.photobucket.com/albums/x378/felison1/desktop-1-populated.jpeg)

This is the desktop screen that you use for playing music.
With the desktop menu you can open media:

### 3.1.1 Menu item "Web" ##
Web opens the internet browser Firefox. You can access all possible websites. The default website is the site JackLinx Content.

### 3.1.2 Menu item "Demo" ##
Demo opens a menu with demo content collected to show the possibilities of the JackLinx platform.

### 3.1.3 Menu item  "Custom"
Custom opens any content menu that your teacher or administrator had prepared for your class.
## 3.1.4 Menu item "Players"
Players open a menu that allows you to start various mediaplayers. The focus is not on the content but on the player. Most players allow you to browse and open content from various respositories, be it on your hard drive, on a network drive or an internet repository.

## 3.2 Desktop 2 - Patching

## 3.3 Desktop 3 - Synthesizer

## 3.4 Desltop 4 - Effects

## 3.5 Desktop 5 - Recording

## 3.6 Desktop 6 - Technical

# 4.0 Learning Music with JackLinx and JackPakx

## 4.1 General principles and strategies for music education.

The first question to be answered in any music educational setting would be:
### What do we want the kids to do, why and how?
The second question will be in our current endeavour:
### What do we want the kids to do with a computer, why and how?

Music learning is in the first place a multifaceted activity. Music learning and playing involves many human capacities simultaneously:
- listening and hearing
- rational thinking
- emotional imvolvement
- improvisation
- body movement and dance
- singing and vocal expression
- playing instruments
- connecting and communicating with other people
- reading and interpreting visual instructions (scores)
- seeing and interpreting video, dance, movement, animation.

Music education benefits from a rich variety of musicking types. 

From the work of Christopher Small and David Elliot we quote some guiding principles that have been an inspirationfor our own music lessons and for the development of JackLinx and PackPakx:

- music education is a practice
- music education is multifaceted
- multicultural music education asks for immersion in multicultural practice
- music education asks for collective work

Ref. Musicking - Christopher Small

[http://en.wikipedia.org/wiki/Christopher_Small](http://en.wikipedia.org/wiki/Christopher_Small)

Ref. Praxial Music Education - Music Matters - David Elliot

[http://www.davidelliottmusic.com/praxial-music-education/foundational-issues-of-praxial-music/](http://www.davidelliottmusic.com/praxial-music-education/foundational-issues-of-praxial-music/)

From these general considerations we could derive specific white paper with activities for a software solution.

The aim of JackLinx is to provide a platform that should be instrumental to submerse the student in a multifacetedmultimedia musical environment that stimulates and challenges the simultaneous use and exercise of various musicaland musicking capacities. Ir should encompass many different musical practices and styles.

The aim of JackPakx is to provide a rich and varied repertoire of music learning material that makes use of the various possibilities of JackLinx. It should encompass many different musical practices and styles.

JackLinx and JackPakx combined should cater for:

- Songs to learn to play on a keyboard.
- Material and fragments from the music appreciation repertoire to play with.
- Playalong tracks and backing tracks for solo and group playing. 
- Composing 
- Beat making
- Sequencing
- Audio editing

## 4.2 Specific JackLinx workflows

## 4.3 Specific JackPakx content categories



### Learning to play a song by imitation

### Learning a song by reading a score

# 5.0 Vision, Concept, Design and Architecture

The current version of JackLinx is in fact a first realisation and prototype of a wider vision and concept regarding the possibilities of open source music and audio software in music education.

Given the fact that working with open source music and audio sofware in the current stage of development and evolution requires a good deal of demanding and exacting configuration and setting up, there will remain a need for session managing applications like JackLinx that appropriately can assist children and beginning music students to work with a more than just a simple one dimensional workflow.

The Linux world in general suffers from a wide gap between passioned developers and advanced users on the one sideand relatively slow adoption by the general public and public and private institutions on the pther hand. The open source vanguard group still did not succeed in making Linux popular.

This general observation is even more true for this geeky subset of Linux folks that deals with audio and music software and is dominated by rarely distributed musicians, technicians, developers and geeks. The result is a plethora of projects, architectures, applications that provoke an impression of splinter groups and deep internal division which definitely does not promote the cause of popularisation.

The wider vision that was the motivation to develop jackLinx remains:

Developing truely accessible and immediately practical tools for using open source audio and music software in music education.

#### In JackLinx we have made many technical choices for the sake of accessibility, predictability, practicality and educational feasibility. JackLinx is opinionated software. It works exactly because these choices have been made. It is predictable because of these choices. It will become safe and well-known terrain for kids. It is opinionated just like LEGO building bricks: the form, dimension, working and colour has been decided for you - no options left - this is what you get. And that is exactly why kids can build and play with it. Kids do not want to be bothered with thousands of options and choices. One mouseclick will give them Jingle Bells - another Mary had a Little Lamb - or Twinkle Twinkle Little Star - or Bach - or Mozart - or Blues. Just another click and they play in a band.
## JackLinx as a mash-up project.

JackLinx does not bring any new original code nor any new original GUI. JackLinx is 100% mashed up from existing applications. This is simply because as a developer I did not want to dive into deep coding. There are many excellent applications out there and no need to invent another wheel. The real problem however was to get all these excellent applications to work together in a simple and reliable way. The Bash scripting language is powerful enough tomanage other applications and sessions. An important condition for incorporating any existing application in this mashup however is that the application can be controlled and managed from the command line or trough editable configuration files. This was an important criterium for selecting or rejecting component applications.
Another important criterium was that any component appliciation should be obtainable from the Ubuntu 12.04 repository.


## JackLinx as yet another Linux audio session manager
JackLinx is a Linux Audio Session Manager. There are already some well developed Linux audio session managers:
- Ladish
- Non Session Manager
- Chino
- KXStudio

An overview of Linux Audio Sessions Managers is found here:
[http://lwn.net/Articles/533594/](http://lwn.net/Articles/533594/)

Why then make another session manager? 
The existing session managers seem to have professional technicians and musicians as a target group that are willing to save and recall various personalised session profiles.
With JackLinx we wanted to make something even more stupidly simple for kids to play with: just one hardcoded session profile that starts at one mouseclick and provides immediate plug and play for a sharp selection of applications. 

What sets JackLinx apart from the existing session managers is the fact that JackLinx has been explicitly designedfor the hectic music classroom where 24 children from 6 to 16 are being taught music under the guidance of a musicteacher who has no time to assist 24 kids to fire up 24 Jack sessions on 24 workstatuins. JackLinx should fire up at one click and activate a Jack patchbay listening for connections. And we think it does. Hence the stopwatch at startup time that kills itself when keyboard and mixer are standby within 5 seconds.

*Issue: Maybe the existing session managers can be functional in the primary and secondary regular music classroom. We would like to hear about it.*

## JackLinx as yet another Linux music educational tool

There are already a lot of Linux music tools and tool collections for education.
LMMS
Pianobooster
MuseScore
Ubuntu Studio



#### Still the choices are open to debate in the community. #### 

####Hence the open source approach that allows and invites discussion in the kitchen.

# 6.0 Configuration files
In JackLinx there are 2 categories of configuration files:

- 5.0.1 Inactive configuration files (presets).
- 5.0.2 Active configuration files.

*Development perspective:  In further development all active configurations files could be 'presetable' by the user at the click of a menu button. Even the strictly static patchbay could be presetable and generate basically different session infrastructures. But this would overshoot the basic need for a predictable working environment for our target group in the general music classroom setting. People wanting complete configurability might prefer another session manager or even no session manager at all.*  

## 6.0.1 Inactive default configuration images.
Inactive default configuration files are template images stored as a shared resource in /opt/jacklinx/share. 
They sit there inactively waiting to be copied into the user environment where they will be functional as runtime config ("dot-files") for the live configuration of running applications.
These files are copied by the "set-" scripts into their specific location in the user home directory.

In fact different config images can be copied into the user directory for different sessions.
As different images however need to have the same filename they have been stored in numbered container folders.

A start in this repect has been made for two sets of Devilspie presets: One set for one screen resolution and
another set of presets for another screen resolution.

*Development perspective: Different sets of Devilspie presets can cater for different screen resolutions.*

- devilspie
- gmplayer
- hydrogen
- jackrack
- kimidimon
- mscore
- pianobooster
- qjackctl
- qmidinet
- qsynth
- qtractor
- vmpk

## 6.0.2 Active configuration files.
Active configuration files that are directly read by applications at startup. These files sit in /etc/opt/jacklinx

- Keyboardmap - read by VMPK
- Mixer Layout - read by JackMixer
- Patchbay - read by QJackCtl
- Menu configuration files - read by 9menu - prefix "mnu-"
- qmr-chordmaker - read by QMidiRoute


# 7.0 Scripts
The scripts have been ordered in groups, each group with a specific prefix:
- 6.1 Scripts controlling menu elements. Prefix "mnu-"
- 6.2 Scripts controlling applications. Prefix: "app-"
- 6.3.Scripts controlling setting configuration files. Prefix "set-" 
- 6.4 Scripts controlling midi processing. Prefix "mdd-" and "swt-"
- 6.5 Scripts controlling pulseaudio. Prefix "pulseaudio-"

### 7.2.1 Scripts to start the main audio application stack
In a Linux audio session the correct configuration and starting up of the necessary audio infrastructure is a complex and demanding task that normally is far beyond the scope of children and young music students. 

Several layers of software have to be started correctly and on top of each other. Higher layers can onkly be started when lower layers are running properly.

In fact this complexity is the one big show stopper for using Linux audio - especially JACK - in the music classroom. The need to tackle this challenging task is the main reason to start developing JackLinx at all. 
The process of setting up and configuring is similar to installing and connecting appliances in a physical analog audio studio:

- Step 0: Choosing components and designing a layout for various workflows.
- Step 1: Installing an audio cable infrastructure and a central patchbay.
- Step 2: Connecting infrastructural appliances such as a mixing desk, meters, audio processors.
- Step 3: Connecting essential musician oriented appliances like synthesizers, keyboards.
- Step 4: Connecting optional applicances such as effects, recording equipment.

In JackLinx the setup of similar layers is scripted in layers that build on top of each other.

- Layer 0: Providing a choice of applications and appropriate configuration files.
- Layer 1: Basic infrastructure: jackd qjackctl patchbay
- Layer 2: Basic appliances: jackmixer, midi router, pulse-audio-sink, meterbridge, gmidimonitor
- Layer 3: Essential musician oriented appliances: qsynth, vmpk, qmidiroute
- Layer 4: Optional appliances like effects and recorder to be started by clicking menu items.

Each of the first three layers is started in two steps: 

- a *"pre"* script that checks and clears the environment for the layer.
- a *"run"* script that starts the actual software components of the layer.

The first script *app-start-jacklinx.sh* triggers simultaneously three scripts:

- *app-start-layer-1-pre.sh*
- *app-start-layer-2-pre.sh*
- *app-start-layer-3-pre.sh*

These *"pre"* scripts check and clear the environment. When certain conditions are met they will trigger the next step:

- *app-start-layer-1-pre.sh* triggers *app-start-layer-1-run.sh*
- *app-start-layer-2-pre.sh* triggers *app-start-layer-2-run.sh*
- *app-start-layer-3-pre.sh* triggers *app-start-layer-3-run.sh*

In *app-start-layer-2-pre.sh* and *app-start-layer-3-pre.sh* an all-important condition is that layer 1 has been started properly, that is to say: that the condition that *jackd* is running is met. These scripts contain a piece of code that suspends further execution until the condition *"jackd is running"*  is met.

#### Image: Function graph showing the start procedure for the main application stack.
![](http://i1178.photobucket.com/albums/x378/felison1/function-graph-start-stack.png)

*Issue: This set of scripts has been been developed by trial and error. Sofar it has been working effectively. However, a much more smooth and faster set of scripts could certainly be developed.*

## 7.2.2 Scripts to start single applications ##
These scripts start most applications on a ad-hoc as needed basis.
These scripts are triggered by clicking a menu item.

## 7.3.Scripts to set configuration files. Prefix "set-" 

## 7.4 Scripts to control midi channel routing. Prefix "mdd-" and 'swt-".

Some USB midi keyboard have a built-in function to change the midi channel. Some USB midi keyboard do not have this function. In such case a special set of scripts give the option to change midi channel.

There are 6 MidiDings python scripts that actually change midichannel - with prefix "mdd-"
There are 6 bash scripts that switch the 6 python scripts on and off. - with prefix "swt-" 

*Issue: This particular set of scripts has been been developed by trial and error. Sofar it has been working effectively. However, a much more smooth and faster set of scripts could certainly be developed.*

## 7.6 Scripts to control Pulseaudio connections to Jack.

In order to be able to play flash generated audio signals from e.g. YouTube it was necessary to control the connection and disconnection of Pulseaudio streams to Jack.
The scripts *pulseaudio-load-sink.sh* and *pulseaudio-kill-sink.sh* do exactly that.

*Issue: This particular set of scripts has been been developed by trial and error. Sofar it has been working effectively. However, a much more smooth and faster set of scripts could certainly be developed.*






# 8.0 Safety #

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

#### Approach A - Pulling the internet plug.

This radical approach involves complete lockout of internet access or strict firewalling. Obviously this can be achieved by literally pulling the plug of internet access.

#### Approach B1 - External firewalling and filtering - Blacklisted sites.

In most educational institutions an institution-wide control policy will be in place to restrict access to malicious internet sites. This can be applied for only registered authenticated users and/or for anononymous guest users. Alternatively - if a working institution-wide filter is not in place - one could set up a gatewayserver for the local JackLinx subnet with a content filter.
Popular Linux content filters are:
-     Dansguardian
-     Squid

Both contentfilters can work with the (commercial) URLBlackList that blacklists over 3 million websites including sites related to a.o. shopping, email, weapons, adult content etc. etc.

#### Approach B2 - BYOD-Bring-Whatever-Device-Connects-to-the-Internet

In some institutions wired or wireless internet only access is provided for anonymous guests under a Bring-Your-Own-Device (BYOD) scheme. Microsoft SCCM 2012 is an example of a network administration manager that allows for specific models of BYOD policies. One such Microsoft BYOD education policy model is called Bring-Whatever-Device-Connects-to-the-Internet. See this Microsoft article about BYOD policies in education.
As JackLinx by default accesses only safe internet sites such a scheme would enable full JackLinx operation.
Technically a fully isolated subnet of JackLinx nodes connected to the wireless network through a single wireless point-to-point ethernet bridge would function as one single BYOD device.

#### Approach C  - Parental control

A standard home and family solution involves installation and configuration of parental control programs. Normally these programs involve a parent login account from where privileges and restrictions for child login account can be configured.
The access control architecture of JackLinx parallels this idea: There is an admin/teacher account from where privileges and restriction fro a student account can be set.
In case of the use of parental control software the admin/teacher account would double as the parent account and the anonymous student account would double as an anonymous child account.
Of the shelf parental control software is available.

#### Approach D - Limiting the use of networking protocols and ports.

JackLinx relies on three networking protocols, each using their own specific port ranges:

- IP-ethernet for accessing WAN or LAN servers serving HTML content.
- UDP protocol for exchanging midi-over-lan signals with other JackLinx stations.
- Universal-Plug-and-Play (UPNP) for accessing XBMC servers on Network Attached Storage (NAS)

This means for example that potentially dangerous programs that rely on internet chat relay protocol can be lockedout by blocking the protocol and the required port ranges.

#### Approach E - Authenticated personal login and logging user activity.

This approach would involve a central LDAP authentication server and enforcing login against this server at each workstation. This is a standard arrangement in the Linux world.
This approach enables logging of user activity which in turn enables forensic detection after the act to identify misuse.
Authentication against a server can still include approaches B and C.

#### Approach F - Selectively installing programs, functions, features and options.

The central idea is to only install those packages and programs tha are really needed and avoid programs that can create unwanted exposure. Minimal installation of functions needed for using JackLinx:

- A minimal installation of Operating System
- Only installing the applications and packages needed for running JackLinx
- Functionalities that are not needed and can create exposure to malicious user action:

File managers that give access to external drives and system files.
Command line terminals that enable controlling the system by commands
Texting, editing and chatting programs that enable the creation and exchange of malicious text. Image editing programs that enable the creation of malicious imagery. Any configuration managers that enable tweaking settings and configurations.

#### Approach G - Digitally restricting users by user policy.

In a typical Linux environment different users can be given different priviliges and restrictions. Normally a admin - or superuser -  account of highest level has the privilege to set and control provileges for lower leveluser accounts. This is the default approach used in JackLinx to protect software integrity. It parallels the parental control approach.

In a default JackLinx system there would be 2 user accounts:
The almighty admin/teacher (sudo) account with super-user privileges.
The anonymous student account, for which privileges and restrictions are set by the admin/teacher. The standard Debian/Ubuntu system allows for various standard privileges/restrictions to be set for the user account.

#### Approach H - Restricting and disabling functions by BIOS settings.
The use of CD-ROM drives and USB drives can be restricted in the BIOS settings. This assumes that the BIOS configuration is protected by a login andpassword.

#### Approach I - Frequently cleaning and resetting systems to defaults.
Users can change settings and configurations. Users can edit and store files.
With the use of automated scripts and scheduled cronjobs traces of user activity can be deleted and default configurations can be reset to default. 

#### Approach J - Physically locking down functions and features.
Physical system components like CD-ROM drive and or USB connectors can be removed or disabled.
In a JackLinx system the CD-ROM drive would only be needed for installation of the operating system. Thus, after installation of the operating system  theCD-ROM drive unit could be removed from te system. The user has no possibilty to use the CD-REOM drive for viewing malicious content on f.x. DVDs.
Similarly a USB connector can be disabled by filling it with glue or resin. The user has no way of accessing a USB datastick with malicious content.

#### Approach K - JackLinx in a Microsoft SCCM 2012 environment.

The latest 2012 version of Microsoft System Center Control Manager (SCCM 2012) allows for the centralized administration and control of Linux operated workstations. Specifically Ubuntu 12.04 LTS is supported.
Administering Linux machines would require a piece of Microsoft software to be installed on each Linux machine that takes care of communications with the SCCM 2012 administration console. Deploying JackLinx within such a framework would result in certain security advantages that will have to be detailed. At least one of the results would bethat the central admin can monitor which software packages are installed on the system.Practical integration of Linux nodes in the SCCM 2012 framework is discussed here and here.

# 9.0 Future Perspective #

The wider vision behind JackLinx however allows for many different realizations of the same concept.
As long as the wider vision is respected in depth, any resulting plethora of different JackLinx solutions will notcreate isolated communities that exclude and frustrate the wider community, but will enrich the wider community with accesible and workable options for cultural development and empowerment.

- Dear Linux Developer: Please fork. When your kid can learn music with it you support music and actwisely.
- Dear Music Teacher: Let them play. When you use community driven open tools you support the community and act wisely.

The causes of open source promotion and music education promotion can go hand in hand.
When they reach towards each other they will both benefit.

### Colofon ###
This document has been edited in MarkDown.
