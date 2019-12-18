# Advanced Graphics Showcase Project
---
# [HOME](https://thomasgriffiths12.github.io) / [CV](https://thomasgriffiths12.github.io/CV) / [PORTFOLIO](https://thomasgriffiths12.github.io/Portfolio)
---

## About this project:

This project was created as part of an Advanced Graphics and Real-Time Rendering Module assignment completed during the course of the Computer Games Programming degree I completed at Staffordshire University and each of the features detailed below were implemented by myself onto a pre-existing DirectX 11 application framework supplied by the university.<br>
---
## Graphics features implemented and the architecture of the application

### Normal Mapping:
The framework implements normal mapping, which involves using a normal map texture to tweak the lighting of a cube to create the illusion of bumps and dents on an object, without increasing the polygon count.<br>
Normal mapping is implemented by sampling a normal map texture and converting it to world space.<br> 
This bumped normal is then taken and added to any lighting calculations that previously used a normal, such as the computation for the reflection vector, as well as the diffuse intensity.<br>
This method of bump mapping is useful when applied to low polygon meshes as it can add details that can make a mesh look almost as good as a high polygon mesh, without having to render the additional polygons, hence the performance costs are significantly less, without sacrificing detail.<br> 
The normal mapping implemented within the framework looks correct, although the normal mapping self-shadowing might not be perfect.

### Parallax Mapping:
Parallax Mapping is another graphic feature that is implemented within the framework.<br>
Parallax Mapping is an upgrade of normal mapping that uses a height map to displace the texture coordinates by the view angle in tangent space in order to create the illusion of depth on an object.<br>
The calculation done to achieve this effect involves sampling a height map and multiplying it by a scale value, then adding a bias value on top.<br> 
This value is then multiplied with the eye vector and added to the texture coordinates.<br> 
This feature, like normal mapping is useful for simulating depth on a low polygon model, without having to increase the number of polygons to create actual depth in the model.

### Parallax Occlusion Mapping:
Parallax Occlusion Mapping is yet another feature implemented into the framework.<br> 
It is an evolution of Parallax mapping that uses a ray tracer that intersects with a height map and interpolate along the ray, sampling the heightmap with each interpolation.<br> 
The benefits of using Parallax Occlusion over regular Parallax mapping is that the overall parallax effect is significantly more detail and can simulate more complex geometry without adding additional vertices to a mesh.<br> 
The downside to Parallax Occlusion mapping however, is that the performance costs are significantly higher than with parallax mapping and sometimes misses the peaks of the height map.<br>
The parallax occlusion mapping within the framework is functional and looks accurate head-on, however it is not perfect, as the peaks on the cubes texture distorts when viewed from the side.<br> 
It is possible that the issue could be incorrect scale and bias values.

### Special Effects Pipeline:
The Special Effects Pipeline allows for objects and shaders to be rendered as textures, as is the case within the framework, where the cube is fully textured with parallax occlusion mapping and bump mapping, then rendered as a texture and passed into the special effects pipeline shader file, where additional special effects are applied, such as a blur effect, or an effect to turn the render negative.<br> 
The blur and negative effects work as intended, however the special effects pipeline within the framework is basic, so implementation of features such as motion blur or HDR could expand the pipeline further.

### Tessellation:
Tessellation was another feature implemented in the framework.<br> 
Tessellation is the process of breaking a polygon down into smaller segments.<br> 
It involves passing a mesh into a hull shader, which will set up control points, as well as setting the tessellation level.<br> 
The tessellator then creates vertices based on the tessellation factor and passes those vertices to the domain shader, where the positions of the vertex are created using barycentric coordinates and the control points.<br> 
The positions of the tessellated vertices are then passed into the pixel shader, where the normal mapping, parallax occlusion mapping and lighting calculations are done.<br> 
The benefits of using tessellation is that it allows for displacement mapping, which dynamically allows for detail to be added to a mesh via additional vertices, as opposed to the illusion of detail that normal and parallax mapping provide.<br> 
Tessellation however is very intensive in terms of performance costs, due to the additional vertices burden, therefore it should only be used when needed.

### Architecture of the project:
In the framework, each graphical feature is separated into its own project within the solution.<br> 
Each project has an application.cpp and .h file where the functions that initialise the shaders, vertices and indices, as well as where the draw function that renders everything resides.<br> 
The normal mapping, parallax mapping and parallax occlusion mapping projects each contain a shader file, that contains Vertex and Pixel shaders, as well as functions relevant for carrying out the required shader calculations, such as transforming a normal from tangent to world space.<br> 
The special effects pipeline and tessellation projects also contain an extra shader file for the special effects pipeline calculations.<br> 
The tessellation shader file also contains a hull and a domain shader, in order to perform the tessellation calculations.<br> 
The main writing style for the variable names is camelCase, however there are a few pre-existing variables that do not follow that style.

---
## Github Repository
[Advanced Graphics Showcase Project](https://github.com/ThomasGriffiths12/Advanced-Graphics-Showcase)
