# HTML5 Raycasting
This project consists of raycasting demos built in JavaScript. The vector based example is a port of Lode Vandevenne's C++ raycaster to JavaScript/HTML5: <a href="https://zerodayarcade.com/demos/raycaster">Live Demo</a>. <br/><br/>
I've also included a euclidean angles example and a debugging version showing the overhead 2D view along side the rendered raycaster. These are meant to serve as a jumping off point for you to build a Wolfenstein 3D style raycasting game in the browser, or to learn about how raycasters work. In my opinion, the modern browser is a fantastic medium for this.

<img width="1141" alt="rc1" src="https://github.com/ZeroDayArcade/HTML5_Raycaster/assets/141867962/76cc2bf1-64bf-4e83-9025-2b43de7245d6">


I've set the maps to the same layout in each approach for comparison. All demos should look nearly identical when rendered. The vectors-based version uses less code and is a good choice for building off of, while the euclidean example uses angles intuitively and works in a similar way to many other raycasters.

## Euclidean Version
By "euclidean" it is simply meant that we are using a player angle, field of view (fov) and iterating through that fov at different ray angles calcuated based on the player angle, fov and current ray number. We then use a series of trigonometric calculations to cast rays and determine the ultimate line height for each ray. This version uses one of the most common techniques for raycasting and is relatively intuitive when programming game logic by thinking in terms of the player's xy position and angle. Like other examples that use this technique, "fisheye" correction is needed before rendering, though this only amounts to multiplying the calculated distance by the cosine of the playerAngle - rayAngle.

<img width="280" alt="rc4" src="https://github.com/ZeroDayArcade/HTML5_Raycaster/assets/141867962/17448fa1-0a6f-4ba2-9733-6e86bdcf6ddf">&nbsp;&nbsp;&nbsp;&nbsp;<img width="498" alt="rc3" src="https://github.com/ZeroDayArcade/HTML5_Raycaster/assets/141867962/baf340ae-541f-4cd4-8124-2adbfc59783f">


## Vectors Version
This version primarily uses vectors in XY space rather than doing a series of trigonometric calculations. Though initially thinking in terms of fov and player angle can be intuitive, ultimately the same calculations can be accomplished more efficiently and with less code using a vector based approach. This version is ported from Lode Vandevenne's C++ tutorial into a JavaScript version. See his excellent tutorial here: https://lodev.org/cgtutor/raycasting.html

## 2D View and Debugging
It can both be informative in learning about how raycasters work, as well as extremely useful for debugging to see the overhead 2D view that the raycaster builds it's semi 3D graphics from. I've included a debugging version here to show the two side-by-side. This can be very helpful for designing levels and testing. Because more rendering is needed to show both, you'll probably want to run this at a lower frame rate which can easily be changed in the section toward the bottom of the code by changing the value of the FPS variable.

<img width="1141" alt="rc1" src="https://github.com/ZeroDayArcade/HTML5_Raycaster/assets/141867962/8fd4b4ab-d9ae-4c8c-a518-27ea0091f56f">


## Texturing Walls, Adding Ceilings and Floors
These demos are meant as a jumping off point and include single color walls with some basic lighting. Using textured walls like in Wolfenstein 3D and other famous raycasters is fairly straightforward, as is creating ceilings and floors. For this, I'll point you to Lode Vandevenne's fantastic tutorial:

Adding Textures: https://lodev.org/cgtutor/raycasting.html#Textured_Raycaster   
Floors and Ceilings: https://lodev.org/cgtutor/raycasting2.html

<img width="396" alt="rc4" src="https://github.com/ZeroDayArcade/HTML5_Raycaster/assets/141867962/5ee239bf-d361-47d1-85b5-18fe368b7897">

## Sprites, Items, and Enemies
Sprites representing items and enemies can easily be added as well. Items/weapons can often be rendered as a simple overlay after walls have been rendered. For some really nice Wolfenstein-style sprites to play around with, checkout these sprites from a GZDoom mod by user itsmeveronica: https://www.moddb.com/mods/volkograd-3d/images/makarov-reload-animation#imagebox. You can right-click and save the images, and then load them into the canvas. For details on code implementation, see this tutorial: https://lodev.org/cgtutor/raycasting3.html 

![rc5](https://github.com/ZeroDayArcade/HTML5_Raycaster/assets/141867962/550d1030-d47a-46fc-b103-7730b1febf88)
![rc6](https://github.com/ZeroDayArcade/HTML5_Raycaster/assets/141867962/a5bf1123-9733-483d-b787-ff1589c6b9d9)


## Full 3D Graphics

Raycasters use a semi-3D graphics technique that takes advantage of the fact that there is no vertical movement or angling to greatly simplify the math and allow for level and game design strategies similar to 2D games while producing 3D looking graphics.<br/><br/>It is also possible to build full 3D graphics engines in JavaScript using software rendering where you explicitly dictate the value of each pixel in the JavaScript code. And of course you can create more advanced and modern 3D graphics in HTML5 games if you use WebGL and GPU-accelerated 3D rendering. For a very simple example of 3D software rendering in JavaScript, see this <a href="https://zerodayarcade.com/demos/3d-wireframe">Wireframe Demo</a> (and the <a href="https://github.com/ZeroDayArcade/HTML5_3D-Wireframe-Cube">Code</a>) which draws SVG polygons to the DOM to produce a 3D cube.

### See the <a href="https://zerodayarcade.com/demos/raycaster">Live Raycasting Demo</a>
