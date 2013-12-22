# Junior Music Lab Design Specifications

These design specifications embody a general concept of an envisioned  music educational software. As such it is guiding different practical implementations on different platforms:

- [JackLinx and JackPakx](http://www.jacklinx.nl) for the Debian-Ubuntu platform.
- [JackLinx Web Content](http://content.jacklinx.nl/en/) for the internet platform.
- [Dolce] (https://git.sugarlabs.org/dolce) for the OLPC-Sugar platform.

JackLinx and JackPakx have been developed most extensively and can stand as a functional mock-up demo of the concept. Dolce for Sugar is still a conceptual project but can take inspiration and example from the JackLinx mock-up.

## Principles of praxial music education

Praxial music education specifies multidimensional hands on involvment with music material. 
- Listening and/or reading is not enough; you have to try to play and re-enact what you read and listen to.
- Playing in itself is not enough; you have to try to digest, analyse, understand and share what you are playing.
- Playing solo is not enough; you have to play together with someone else.
- Playing solo is not enough; you have to play in relation to a supporting or backing track.
- One dimensional is a no brainer - multidimensional activity creates new connections in the brain.

### Design requirement: cater for *and-and-and-and* activity types.

Include more than one musical activity into multidimensional linked activity types:
- **and** playing **and** reading a score
- **and** reading a score **and** playing
- **and** playing solo **and** playing with a backing track
- **and** viewing a video **and** playing solo
- **and** playing solo **and** playing together with an ensemble

These linked activity types require desktops that link various functional application windows:
- **and** a keyboard **and** a score **and** an instruction video on one desktop
- **and** a keyboard **and** a score **and** a backing track **and** a network ensemble on one desktop

These linked **and-and-and-and** audio applications require a patchbay layout and an audio mixer that can mix and balance the levels of these different audio sources.

## Ergonomic layout of GUI screens. 

### Tradition: Score at eye level, keyboard at hands level.

When you study and practice instrumental music you are most probably familiar with a standard ergonomic arrangement of your the work place:
- your eyes on a score or other visual display in front of you - on eye-level.
- your hands on the instrument in front of you - on hands level.

This arrangement caters for fundamental assumption that working with music involves the integration of multiple human functionalities: reading (eyes), interpretation (mind), expression (heart) and execution (hands).

A music educational digital tool has to acknowledge from this fact and subsequently has to cater for it by offeringan arrangement of GUI functions and windows that mimics the real life work place. 

Many music educational software however sems to focus on one of the two elements only: either the score is presented, or the keyboard is presented.

In my opinion you have to present both: the display on top and the instrumental controls in the bottom.

By the way: this has been the most common layout principle for complex machine interfaces for ages: 16th century organ consoles have their score display - the music stand - in fromt of the eyes, the keyboards at hand level, pedals at foot level and stops and registers on the sides like a modern website menu. Similarly a television set has the tube on top and the knobs in the bottom.

### GUI design requirement: displays on top, controls in the bottom, menu's on the side.

These general design requirements have been implemented in following three platforms:

- JackLinx Platform
- JackLinx web content
- Dolce for Sugar










