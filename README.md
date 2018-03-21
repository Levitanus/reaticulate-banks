# reaticulate-banks
banks for reaticulate extension of Reaper

## disclaimer
This banks are not like built-in reaticulate banks. They not suited for factory instruments, but, generally, more complex and customized solution for making templates with optimal ergonomic (for particularly my style of work).

Solution for each library consists of:
- reaticulate bank (file "bank"), content of which has to be copied to your Reaticulate.reabank file. **check for banks numbers for avoiding conflicts with other banks**
- vienna ensemble project (we're working with vienna, yep?)
- rtrack-template file, consists of tracks and vienna plug-in with it's preferences
- kontakt multi for each kontakt instance inside vienna
- personal libraries JSFX plugins, if needed for placing them after reaticulate JSFX
- here are placed only banks files. "content" has to be downloaded from the google drive (because git doesn't like binaries)

# google drive links

**Orchestral tools - Berlin Woodwinds (Rewive + SFX)**
- https://drive.google.com/drive/folders/1bxtwXPRAM1nM9HwC8-0cgFEm4oSUJ7tS?usp=sharing

**Orchestral Tools - Berlin Brass (main + muted)**
- https://drive.google.com/drive/folders/1EOSbBo2TE4QHyg1LHUjeX9Aj6_uXdvwb?usp=sharing

**Orchestral Tools - Berlin Percussion (+ Timpani)**
- https://drive.google.com/drive/folders/1224qY_cykdMmSHN1rIH1KJO-zak0CBOn?usp=sharing

**Spitfire Audio - Harp Redux**
- https://drive.google.com/drive/folders/1qhxwoulAReBbNJfilGHjs2c3nitUDjan?usp=sharing

**Spitfire Audio - Symphonic Strings**
- https://drive.google.com/drive/folders/1_dSudJ_9AJKPNZ858hh97ZRzEjp4dLZR?usp=sharing

**Russian Folk template (Ilya Efimov + Siberian Samples)**
- https://drive.google.com/drive/folders/1XRVJRCBNa-MhneQbqLoS0P6Q6BXyg0NR?usp=sharing

# instalation
- download binaries from the google drive link
- copy Effect folder reaper resource path (can be accessed with "show reaper resource path" action).
- copy contents of solution bank to the reaticulate bank with checking bank numbers
- load rtrack-template file
- if something haven't loaded, build vienna instances with solution multis, being guided by instructions in the **building** section

# building
for manually building of vienna instances:
- create instance and connect in to the instrument. *solutions often are multi-instrumental*
- load kontakt instances with multis, beign guided by prefix of multi name. 
- prefix has folowing structure: \{instance}\_\{instrument\}. \[B\{midi-bus number\} Ch\_\{midi-channel\}, out\{vienna outs\}\]**
## let's get closer
- \{instance} is vienna instance number. In multi-instrumental solution there are several instruments, usually named "BWW1", "BWW2" etc. number defines which reaper track from the "instruments" folder has to be connected to instance, and what instance has to handle kontakt with particular multi.
- \{instrument\} is just for alphabetic sorting of files inside explorer
- \{midi-bus number\} is midi-bus of kontakt, being set inside vienna channel. *my instances are using up to 10 midi-buses, check preferences of vienna for setting their amount not less, than 10.*
- the same for \{midi-channel\}. Note, than midi channel can be set to all.
- \{vienna outs\} are audio channels, being sent to the Reaper. If channels range is more, than two (for example, 1-4), more outs from kontakt have to be used (with "+" button)
- for example: "01\_01. \[B1 Ch_all, out1-2\] BWW picc Core" means that this is first instance of BWW solution, kontakt is loaded on the midi-bus 1 and midi-channel mode set to "all". Kontakt has only one pair of audio-outs: 1-2.

# JSFX
There is JSFX called **OT micpos manager**. It's alpha version of plugin for making life easier during orchestration, by using only one mic pos.

Then You can export the same tracks several times with other mic positions, just connected this plugin to every output midi channel of every vienna instrument, which using OT libraries with capsule.

Plugin is buggy, so use at your own risk)

I'll make the normal solution for managing capsule mic positions soon.

# concept
I'm adept of manual multi-track layering of samples during mockup. (not modwheel fun;) )
So this concept is based on two possibilities and one desire:

- get the access to any articulation simultaneously with others
- have global settings per instrument
- make as less tracks as possible

So every tweakable "instrument" (real-world instrument or section) has preferences, being accepted by all tracks, and every track, connected to the "instrument" can play any of it's patch.
Basically, There is only one midi-track per one "instrument", but it can be copied as many times as You need for proper layering (layer tracks inside midi folders).