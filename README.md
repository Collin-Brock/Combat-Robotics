# Previous Robots
[Missouri S&T Combat Robotics Fight Compilation](https://youtu.be/2jmfZkLVLY4)
# Dopamine - Beetleweight (3lbs)
Watch Dopamine in action:

[Cage Side Dopamine Fights](https://youtu.be/8gMDauhMamM)

[Competition Stream](https://www.youtube.com/live/L-PKoHOr0sI)

<img src="https://github.com/Collin-Brock/Combat-Robotics/blob/main/assets/Dopamine%20Finished.png" alt="Finshed Dopamine" width="600" height="400">

#Overview

Dopamine is a three pound vertical spinner, and was designed and built in just two weeks entirely using FreeCAD 1.0. While I use SolidWorks professionally, I like to challenge myself to use open-source tools whenever it is possible, and I was excited to give the newly released 1.0 version!


I had used FreeCAD for viewing CAD, creating small single parts, and for its CAM workbench. This was my first full FreeCad project!

My first concept involved two vertical weapon motors at an off-angle to each other.

<img src="https://github.com/Collin-Brock/Combat-Robotics/blob/main/assets/Dopamine%20Concept%201.PNG" alt="Concept 1" width="600" height="400">

With the newly introduced topological naming algorithm in the 1.0 release and the limited changes I made to these files, I had no technical issues with modeling. The assembly workbench is unfortunately not nearly as stable and as shown in the linked image, broke for nearly every change. The real issue with this concept was weight. After figuring in all the components and the body's weight, I realized this concept would be extremely challenging to pull off, especially with my limited timeline.

I then pivoted away from that concept to a single weapon vertical spinner, with the hopes of creating something as simple as possible.

<img src="https://github.com/Collin-Brock/Combat-Robotics/blob/main/assets/Dopamine%20V1.PNG" alt="Concept 1" width="600" height="400">

This is version 1 of dopamine with a single body frame. This is also where I started to have significant technical issues. I went to use the chamfer tool to create the drafted edge on the front. I couldn't create it with the exact dimension, so I used a very small value to approximate the edge.  Finally, when going to add all the needed edge blends to give the 3D printed TPU the best fighting chance, I noticed the fillet tool wouldn't work. As it turns out, there are major limitations with the filleting algorithm. They cannot remove a geometry reference like the infinitesimally small line I had created with the chamfer tool way back at the start of modeling. I did end up getting it to work using a swept cut. I also dimensioned off of references in the body for many of my sketches. The solver algorithm cannot solve sketches when the geometry moves over the dimension line. [Open Github Issue](https://github.com/FreeCAD/FreeCAD/issues/17579). It is non-trivial to add directionality and relationships to fix this. I now had an extremely fragile model tree that I could only edit by making numerous small dimensional changes so the solver could properly update, that is, if the topological naming algorithm could interpret my very numerous geometry changes. Along with this fragile model, I needed to make massive changes, as I was once again far too close to the weight budget than I was comfortable with.

Version 2!

<img src="https://github.com/Collin-Brock/Combat-Robotics/blob/main/assets/Dopamine%20Cad.PNG" alt="Final CAD" width="600" height="400">

Putting together all I learned, I was aggressive in removing unnecessary features in the model tree and cognizant of every single geometry reference update. Splitting the body into the two uprights and a main body section, I was able to cut the weight needed to make this robot compete! With about five days left until the competition, I quickly sliced and printed all the components on my Voron 2.4. When the part came in the day before competition, I finally got all the parts together and finished the build.

Version 3?

I was happy with the performance of the first revision. The weapon had a ton of power, and the body held up well! However, there are numerous changes that I will make to compete with this robot again. The most important being retaining the weapon ESC's heatsink so that it doesn't come off and melt the solder joints on the ESC. The design changes planned are:
- Carbon fiber top and bottom plate for rigidity and weight
- Wheels closer to the weapon axis to limit gyroscopic forces
- Thinner body design to remove weight
- Removable wheel guards for ease of assembly
- Forks in the front to corral opponents
