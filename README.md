

# Robotic Thermoplastic Shape-Winding

[TOC]

**Thermoplastic shape-winding** is a method of creating 3D objects by extruding thermoplastic onto a base form wich is moved by a 6-axis robot. 
The project aimed to find ways of quickly generating threedimensional structures without the need for layer by layer extrusion. 

click the image below for a [video demonstration](http://www.youtube.com/watch?v=9nkImklokDo): 
[![Robotic thermoplastic extrusion ](/images_and_animations/yt_thumbnail01.png)](http://www.youtube.com/watch?v=9nkImklokDo "Robotic thermoplastic shapewinding")



## Installation and requirements 

- [**Rhino 6**](https://www.rhino3d.com/6) (tested in Rhino 6 for Windows)
- [**Grasshopper**](https://www.rhino3d.com/6/new/grasshopper)(included in Rhino 6)

**Required Grasshopper Plugins:** 

- [**visose/Robots**](https://github.com/visose/Robots/)
  - Make sure you install a [robot library](https://github.com/visose/Robots/wiki/Robot-libraries) that has a UR5 such as [KU-Leuven](https://github.com/visose/Robots/wiki/Robot-libraries#ku-leuven)
- [**treesloth**](https://www.food4rhino.com/app/treesloth)



In order to actually extrude thermoplastics you will of course also need: 

- [**Universal Robot UR5**](https://www.universal-robots.com/products/ur5-robot/) or any industrial robot supported in [visose/robots](https://github.com/visose/Robots/wiki/Robot-libraries) (tested on a UR5 CB)
- **Thermoplastic extruder**
  - a common 3D-printing hotend could be enough for small-scale tests
  - the extruder used here is adapted from the [precious-plastic extruder](https://community.preciousplastic.com/academy/build/extrusion)






## Method overview: 
2D shape generation with a randomized algorithm:
![2D shape generation by randomization](https://media.giphy.com/media/ZDFOcmuQBokXXDcpuF/giphy.gif)

Projecting the generated shape onto the 3D base form: 
![projecting the 3D shape to the 3D sphere](https://media.giphy.com/media/W4XHigYEZNN6xbh7s5/giphy.gif)

Optimising the extrusion angle onto the base form (this is currently done manually):
![6D orientation robot](https://media.giphy.com/media/d8LBkWQdMqfxGP67hf/giphy.gif)

Simulating the extrusion process:
![robot simulation](https://media.giphy.com/media/Vi0BAiefmNuPssO3cX/giphy.gif)



Extrude:





## Current shortcomings of the method:

1. Currently, the method relies on manual adjustment of the parameters (especially robot orientation) and input-curves in order to **prevent the robot from reaching its joint-limits**. This step could be done algorithmically, both to find the optimal starting configuration and rotation for the robot as well as constraining the shape-generation method to prevent it from creating impossible shapes. 
2. The [non-spherical wrist of a Universal-Robot](https://www.researchgate.net/profile/Khaled_Elashry2/publication/300721200/figure/fig2/AS:469636585136131@1488981495794/Difference-between-spherical-and-non-spherical-wrist-robots_W640.jpg) causes considerable speed constraints when performing certain movements. A robot with a spherical wrist would have less of these constraints
   **As the speed of the robot is currently not linked to the extrusion speed** this severely impacts the uniformity of the resulting extrusion line. This can be seen [in this video](https://youtu.be/IVRG1TSqpIU).
3. No automated collision avoidance is implemented as of yet

## License 
The code and documentation (text and images) are licensed under the [MIT-License](https://github.com/robin-gdwl/gh_thermoplastic_shapewinding/blob/master/LICENSE)
You are free to share and redistribute the material as well as adapt and transform it (even commercially), however there is no warranty or liability on the part of the creator.

If you use this code directly or as an inspiration for your own project, let me know. I am very interested in seeing where this method could lead. 

