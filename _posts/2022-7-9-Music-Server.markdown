---
title: "Raspberry Pi Music Server"
layout: post
date: 2022-7-9 9:41
image: https://content.instructables.com/ORIG/F4K/TN69/L3D0ZNAF/F4KTN69L3D0ZNAF.jpg?auto=webp&frame=1&width=1024&height=1024&fit=bounds&md=9356a5837f8b1a3989619c8fe36d7e75
hidden: true
projects: true
headerImage: true
tag:
- Project
- Raspi
- Music
- Server
category: project
author: Alek V.
description: "This is a Raspberry Pi Music Server I built from Scratch"
---

## Introduction

Today I will show you how to create your own Raspberry Music Server. 

I designed my Music Server with two goals in mind, 

To have a fast, fully functional Music Server 
To make it look as aesthetically pleasing as possible without sacrificing functionality.
In this Instructable, I will lay out what materials I used, the design process, the steps to follow, as well as some improvements for the future.

**Let's dive in!**

## Supplies

### Tools:
1. Jigsaw or a Router
2. Pine Wood 3"x21"
3. 3d Printer
4. Sandpaper with grits of 120, 220, 400
5. Drill
6. 1-inch Drill bit
7. Fusion 360
8. 3d Printer
9. Flame Torch
10. Dremel
11. 3mm Drill bit
12. Table Saw(You can probably use a circular saw)
13. Vice
14. 3" Wide Metal Pipe
15. Metal Clamp
16. Brasso
17. Thick Rosin Core Solder

### Materials:
1. PETG Filament
2. 0.025x2x12 Inch Brass x3
3. Pine Wood at least 25 inches Long
4. Raspberry Pi 0W
5. Pimoroni Pirate Audio 3W Speaker Amp
6. Speaker Spikes and Screw Mounts
7. Pimoroni 3W Speakers x2
8. M2x20mm Hex Nuts and Bolts x2
9. Left Angled Micro USB Male to Micro USB Female
10. SD Card
11. Raspberry Pi Female Header
12. Screws
13. M3x30mm Nuts and Bolts x4

## Step 1: Design

I've seen speakers with brass siding, and so wanted to somehow integrate that into my music server. For the design, I first used Fusion 360 to model the speaker, from there I created a 1:2 scale drawing depicting the dimensions of the speaker and its shell.

## Step 2: 3D Printing

My print settings were as follows:

Infill: 20
Printing Speed: 35
Color: Red
Filament: PETG
Filament Brand: Matterhackers
Printer Model: Lulzbot Taz 5
Printer Extruder Temperature: 235˚C
Printer Bed Temperature: 60˚C

I went with red, but any color should look fine.

## Step 3: Creating the Main Body

Below, I attached a pdf showing the accurate dimensions of the front wood plate. The process is quite simple, I used a table saw to cut two 10.5" x 3" rectangles, using a jigsaw to round the edges. I routed the hole for the Pimoroni Pirate Audio Hat, using a Router and a Dremel.

I then drilled two 1" holes, 1/2" away from the edge of the board, for the speakers. For the backplate, I drilled one 1" hole, 1/2" away from the edge for the power supply. I then sanded the edges with sandpaper grit: 50, 120, 220, and 400.

Using Gorilla Super Glue, I then glued the backplate to the back of the plastic speaker shell.

After the glue dried, I marked 4 places for the Speaker Spike Mounts to go, making each 2" away from the edge.

Then, using a soldering iron, I slowly melted each Spike Mount into its place, careful not to push it too deep. I drilled three more holes, one in the middle, about 1/8" above the bottom edge, and two more, one on the left and one on the right, about 1/8" below the top, to attach the front plate to the speaker.

To attach the speakers, line up the speaker with the speaker holes and mark two of the 4 holes in the speaker opposite from each other. Do that for both speaker holes, then drill.

Lastly, drill two 2mm holes into the spots called "Holes for M2 Bolts" in the front plate.

## Step 4: Brass

This is my first time working with brass, so please bear with me as I outline the process for bending and soldering the brass. The Youtube Channel Diy Perks has many awesome videos, that I recommend for learning more about brass.

First, I cut the first two pieces of brass to an eight-inch length, for the top and bottom of the speaker. After cutting the third piece of brass in half for the sides, I then put the 3" metal pipe in a vise and tightened it securely for a mold to bend the brass sides. After making sure the metal pipe was firmly in place, I used a metal clamp to bend the brass sides into a semicircle. I applied heat via a propane flame torch, to make the brass hold its place, for, without heat, the brass will reform into its original shape. After repeating that process for the other side, I put the pieces of brass on the speaker shell, making positively sure that everything lined up.

Before soldering everything together, I drilled the holes for the speaker spike mounts on the bottom brass strip. I also drilled three holes in the top brass strip with a 2.1" spacing to keep the brass together. It will be easier to drill the holes now, than later.

I then used a Sharpie to mark out where the pieces will need to be soldered together. Using thick solder and a flame torch, I tried to solder together the brass. It took a while, but I managed to solder all 4 pieces of brass together. I did, however, run into a problem of the solder not sticking and had to finally cut a strip of solder 2" long laying it horizontally, like a sandwich, in between the two brass strips I was soldering, holding everything together with a vice. I then applied heat to the brass, while at the same time tightening the vice, creating a satisfactory adhesive for the brass. I then soldered the edges of the brass. It took some trial and error, but I am confident that the solder will hold.

After all of that soldering, I sanded the outer side of the brass, removing any leftover residue from the heat and solder. I started with 120 grit sandpaper and worked my up to 400 grit. After that, I finished with Brasso, rubbing the brass with an old towel.

Using some screws I had laying around, I screwed in 3 screws on the top, and hand tightened the 4 speaker spikes on the bottom.

## Step 5: Installing the Software

Before we finish the speaker case, let's take a break and install the software onto our Raspberry Pi Zero W.

For this project, I will be using Mopidy for the music server software and Mopidy-Iris for the web client, since that is what comes preinstalled in the pirate audio installer.

The speaker wiring is pretty straightforward, just gently push each speaker wire into its designated spot.

To install the software onto your Raspberry Pi, first flash the Legacy Buster Raspberry Pi OS to a formatted FAT-32 SD Card. If you are using the Raspberry Pi Imager App, you can turn on SSH and set your WIFI in the advanced setting menu.

Connect the power cable to the female end of the left angle micro USB, and feed that through the hole in the backplate. After that, you can connect the male end of the left angle micro USB cable to the power connector on the Raspberry Pi.

After you have SSH into the Raspberry Pi, you can install the software manually here: https://github.com/pimoroni/pirate-audio/tree/master/mopidy Or by running the following commands:
```
git clone https://github.com/pimoroni/pirate-audio
cd pirate-audio/mopidy
sudo ./install.sh
```
After that has finished installing, restart the system with the command:
```
sudo reboot
```
After the Raspberry Pi has finished rebooting, wait a couple of minutes, then the Pirate Audio display should show the IP address and the port number of the Raspberry Pi e.g.
```
http://192.168.X.X:6680
```
*Replace the Xs with your actual IP Address*
If not you can check for errors by entering the following commands on the Raspberry Pi:
```
sudo systemctl status mopidy
```
Once the Raspberry Pi is up and running and the screen is displaying its IP address, open the link on a computer that is joined to the same network. You should see a menu, select Iris, and wait for it to load up.

It will now take you to the Iris web client, and from there you can view and play the music that is in the Music folder on your Raspberry Pi. You can also enable support for Snapcast, Spotify, LastFM, and Genius.

If you want to further explore the Pirate Audio Software, head over to this Pimoroni tutorial: https://learn.pimoroni.com/article/getting-started-with-pirate-audio

## Step 6: Assembling the Front Plate

Now that we have the software programmed and the brass attached, we will now assemble all of the components onto the front plate.

1. Turn off the Raspberry Pi
2. Disconnect the Pirate Audio Hat and Speakers
3. Feed the Speaker Wires through the Speaker Hole
4. Connect the Speaker Wires to the Pirate Audio, making sure to take note of which speaker is right and left
5. Connect the female header to the Raspberry Pi
6. Plug the Raspberry Pi into the Pirate Audio Hat through the Header Hole
7. Make Sure the Pirate Audio Hat holes line up with the holes drilled in the front plate
8. Take two M2x20mm bolts and slide them through the slots in the Speaker Plate
9. Then slide the bolts through the Pirate Audio Hat, and then through the holes drilled in the wood
10. Put one nut on each bolt and tighten them
11. Take two M3 bolts and slide through the holes drilled for the speaker, making sure the speaker wire is facing inward.
12. Do that for both sides, and tighten with nuts
13. Lastly, using three screws, screw the front plate to the plastic lip of the Speaker Shell

## Step 7: Conclusion

One improvement I might add in the future is to attach some brass mesh to the front of the speaker, to conceal the speaker holes and screws.

Special thanks to my dad for helping with the soldering and routing.

The process of making this media server is somewhat long and tedious, but I do believe the finished product looks quite impressive.

#### Thanks for Reading!
