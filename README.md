# null - Hobbyweight (12lbs)

# Overview

null is a hobbyweight robot that uses two independent egg beater style weapons.

# Revision 2 (Under Construction)
For my next revision of null, FreeCAD released the 1.1 update. Because of this, and since the redesign would not share any components, I migrated from onshape back to FreeCAD. Finally, FreeCAD had the ability to create a main sketch that could be reference for all other components. 

<img src="https://github.com/Collin-Brock/Combat-Robotics/blob/main/assets/nullV2MainSketch.PNG" alt="null CAD" width="600" height="400">

I took this top-down modeling method to its extreme. All the important parameters went into the VarSet (a collection of variables and properties). I also found the iterative sketch solver to be very robust; I was able to designate constraints and belt lengths and parametrically derive the position of each of the pulleys. Using the Gear add-in, I also was able to create the HTD3 belts and parametrically derive the rest from those generated shapes. Now I can change the drive gearing on the fly! I used this extensively to pack the robot into the smallest possible package.

<img src="https://github.com/Collin-Brock/Combat-Robotics/blob/main/assets/nullV2CAD.png" alt="null CAD" width="600" height="400">
The wheels needed to be geared down just a bit more, so I took a small 1:4 gearbox driving pulley in the middle of the wheels driving the front wheels from the inside and the back from the middle. The only shared component between this version and the first is the weapons, as these were the most difficult to manufacture. The external pieces are made of carbon fiber and Overture's High Speed 95A TPU. All the armor components are held on with M5 aluminum standoffs, and the TPU is screwed into with tri-lobe screws for plastics.

# Revision 1

<img src="https://github.com/Collin-Brock/Combat-Robotics/blob/main/assets/nullv1.PNG" alt="null CAD" width="600" height="400">

For the first revision, I wanted to try and use Onshape again. I moved away from FreeCAD because of a frustration I had with not being able to top-down model like I wanted to. At this point in its development, it was not possible to reference other sketches into other sketches parametrically. There was the ability to create independent copies, but changes would not propagate.

The design philosophy for this was something that I could build very rapidly, and keep the belts inside of the uprights. One of the coolest aspect from this design, the belts on the interior of the upright, was also its downfall. The parts I manufactured with my custom CNC machine (A Millennium Machines Milo Build Kit by LDO Motors - V1.5) and full size knee mill. The weapons were made of S7 that I manually machined then heat treated in an old pottery kiln.

<img src="https://github.com/Collin-Brock/Combat-Robotics/blob/main/assets/KilnWarmingUp.jpg" alt="Kiln Warming Up" width="400" height="400"> <img src="https://github.com/Collin-Brock/Combat-Robotics/blob/main/assets/KilnHot.jpg" alt="null V1 Weapon Heat Treat" width="400" height="400">
<img src="https://github.com/Collin-Brock/Combat-Robotics/blob/main/assets/nullDone.jpg" alt="null Finished" width="600" height="400">

I had several issues with this first revision. The worst of these was the main shaft bending. This was due to using a low carbon hollow tube steel tube. The other problems were due to the belts being inside of the uprights. These rubbed on the uprights and were easily able to escape where they were supposed to be.

<img src="https://github.com/Collin-Brock/Combat-Robotics/blob/main/assets/nullV1Bent.jpg" alt="null Issues" width="600" height="400">

Using onshape was a good experience overall. I did not like the equations editor and the solving algorithms that are standard with the package however.

# xlrom8r - PLANTweight (plastic 1lbs (Under Construction)

xlrom8r is a plastic antweight full meltybrain spinner. It uses one driven wheel with an accelerometer to rotate and translate.

This project is loosely based on the OpenMeltv2 project. This was my first full design and layout of a circuit board.

<img src="https://github.com/Collin-Brock/Combat-Robotics/blob/main/assets/xlrom8rv1.1.1.jpg" alt="xlrom8r Prototype vs. V1.1.1" width="600" height="400">

During this process I learned several very important items.The first of these is the FS2A receiver. I found some cheaper old stock receiver that have different firmware. Newer FS2A firmware allows you to be able to set the failsafe (what the board outputs when it looses connection) in the transmitter. The older boards need to be connected to the transmitter then the micro switch needs to be pressed while the sticks are giving a zero output to set the failsafe.

The other item that I learned is that mosfet technology has rapidly improved in the last 10 even 5 years. The OpenMeltv2 BOM spec mosfet RFP30N06LE is quite outdated and has a really bad Rds resistance of 47mOhms. This causes lots of extra heat in the robot. During testing with an unbalanced frame it got so hot that it melted the PLA plastic with an aluminum heat sink attached.

To upgrade we used an STP60NF06. This mosfet has an Rds of 16mOhm. This give us much less heat output with a very comparable on and off time and the same voltage rating.

# Dopamine - Beetleweight (3lbs)
Watch Dopamine in action:

[Cage Side Dopamine Fights](https://youtu.be/8gMDauhMamM)

[Competition Stream](https://www.youtube.com/live/L-PKoHOr0sI)

<img src="https://github.com/Collin-Brock/Combat-Robotics/blob/main/assets/Dopamine%20Finished.png" alt="Finshed Dopamine" width="600" height="400">

# Overview

Dopamine is a three-pound vertical spinner and was designed and built in just two weeks entirely using FreeCAD 1.0. While I use SolidWorks professionally, I like to challenge myself to use open-source tools whenever it is possible, and I was excited to give the newly released 1.0 version!

# Current Version

<img src="https://github.com/Collin-Brock/Combat-Robotics/blob/main/assets/Dopamine4WDLayout.png" alt="Dopamine Today" width="600" height="400">

After the original write up from Dopamine I've slowly iterated on the design.

# Version 3?

I was happy with the performance of the first revision. The weapon had a ton of power, and the body held up well! However, there are numerous changes that I will make to compete with this robot again:

- Retain the heatsink to the weapon ESC as it came off in my third match and melted the solder joints, rendering my weapon useless.
- Carbon fiber top and bottom plate for rigidity and weight
- Wheels closer to the weapon axis to limit gyroscopic forces
- Thinner body design to remove weight
- Removable wheel guards for ease of assembly
- Forks in the front to corral opponents

I had used FreeCAD for viewing CAD, creating small single parts, and for its CAM workbench. This was my first full FreeCAD project!

# Version 2

<img src="https://github.com/Collin-Brock/Combat-Robotics/blob/main/assets/Dopamine%20Cad.PNG" alt="Final CAD" width="600" height="400">

Putting together all I learned, I was aggressive in removing unnecessary features in the model tree and cognizant of every single geometry reference. Splitting the body into the two uprights and a main body section, I was able to cut the weight needed to make this robot compete! With about five days left until the competition, I quickly sliced and printed all the components on my Voron 2.4. When the part came in the day before the competition, I finally got all the parts together and finished the build. 

Some quick changes I made were adding a button head cap screw to the bottom of both uprights. This allowed me to cut down the uprights and use the button head screws as a slider on the floor. This gave me better, more consistent ground clearance. I also used a 3D Pen to fix damage during the competition. This worked wonderfully, and the "welds" were stronger than the printed material. I also added a small hole in the uprights for a weapon lock per competition rules.

# Version 1
<img src="https://github.com/Collin-Brock/Combat-Robotics/blob/main/assets/Dopamine%20V1.PNG" alt="Concept 1" width="600" height="400">

This is version 1 of dopamine with a single body frame. This is also where I faced significant technical issues. I went to use the chamfer tool to create the drafted edge on the front, but couldn't create it with the exact dimension, so I used a very small value to approximate it.  Finally, when going to add all the needed edge blends to give the 3D printed TPU the best fighting chance, I noticed the fillet tool wouldn't work. As it turns out, there are major limitations with the fillet algorithm. It cannot remove a geometry reference like the infinitesimally small line I had created with the chamfer tool way back at the start of modeling. I did manage to work around this using a swept cut.

On top of that, I'd dimensioned off of internal references in the body for many of my sketches. The solver algorithm can't solve sketches when the geometry moves over the dimension line. [Here's the open issue on GitHub](https://github.com/FreeCAD/FreeCAD/issues/17579). It is non-trivial to add directionality and relationships to fix this, so I now had an extremely fragile model tree that I could only edit by making numerous small dimensional changes so the solver could properly update, that is, if the topological naming algorithm could interpret my very numerous geometry changes. Along with this fragile model, I needed to make massive changes, as I was once again far too close to the weight budget than I was comfortable with.

# Concept 1
My initial concept involved two vertical weapon motors at an off-angle to each other in order to maximize the offensive surface area.

<img src="https://github.com/Collin-Brock/Combat-Robotics/blob/main/assets/Dopamine%20Concept%201.PNG" alt="Concept 1" width="600" height="400">

With the newly introduced topological naming algorithm in the 1.0 release and the limited changes I made to these files, I had no technical issues with modeling. The assembly workbench is unfortunately not nearly as stable, and as shown in the linked image, it broke for nearly every change. The real issue with this concept was weight. After figuring in all the components and the body's weight, I realized this concept would be extremely challenging to pull off, especially with my limited timeline.

For these reasons, I pivoted away from that concept to a single weapon vertical spinner, with the hopes of creating something as simple as possible.

# Previous Robots
[Missouri S&T Combat Robotics Fight Compilation](https://youtu.be/2jmfZkLVLY4)
