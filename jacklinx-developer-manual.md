# JackLinx Developer Manual

In this manual it is assumed that you have familiarized yourself with:
- JackLinx Student Manual
- JackLinx Teacher Manual
- JackLinx Administrator Manual

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



