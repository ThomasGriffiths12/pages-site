# Terrain Generation Project
---
# [HOME](https://thomasgriffiths12.github.io) / [CV](https://thomasgriffiths12.github.io/CV) / [PORTFOLIO](https://thomasgriffiths12.github.io/Portfolio)
---

## About this project

This project was created as part of an Advanced Graphics and Real-Time Rendering Module assignement completed during the course of the Computer Games Programming degree I completed at Staffordshire University. <br>
<br>
This project is a showcase of multiple terrain generation techniques, from static terrain generation by using a pre-existing heightmap, to different algorithms that procedurally generate terrain, such as the diamond square, fault line and hill/circle algorithms.<br>
<br>
The static terrain generation example loads in a heightmap from a raw file, then stores the data of the heightmap in a vector of vertices and drawing them, creating static terrain.<br>
<br>
The procedural terrain generation examples are created using three different algorithms.<br>
The first algorithm used, Diamond-Square creates a heightmap by setting the corners of the map to preset initial values and then performing a diamond step and square step repeatedly until every value within the heightmap contains a value.<br>
<br>
The second procedural terrain generation algorithm used was the fault line algorithm, which involves creating a random line, which would divide the heightmap in half, then displace one half upwards and the other half downwards.<br>
This algorithm can be iterated through multiple times to create more diverse terrain heights.<br>
<br>
The third and final algorithm is the hill/circle algorithm, which involves drawing a circle with a defined size on the height map. <br>
The points of the map within the circle displace upwards relative to the position of the point within the circle, with points at the centre of the circle displacing more than those on the edge of the circle.<br> 
This algorithm, like with fault line can be iterated through multiple times to create more diverse terrain heights.
---
## Github Repository
[Terrain Generation Project] (https://github.com/ThomasGriffiths12/Terrain-Generation-Project)
