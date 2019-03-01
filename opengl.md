# OpenGL

## Inbox

+ [How OpenGL works: software renderer in 500 lines of code](https://github.com/ssloy/tinyrenderer/wiki)
 - https://news.ycombinator.com/item?id=11264469
+ http://learnopengl.com
 - https://news.ycombinator.com/item?id=9751666
+ http://nullprogram.com/blog/2015/06/06/
+ http://github.com/stackgl/glsl-lighting-walkthrough
+ http://news.ycombinator.com/item?id=9331126 - WebGL Fundamentals
+ http://www.cs.princeton.edu/~dpw/popl/06/Tim-POPL.ppt
+ http://github.com/patriciogonzalezvivo/glslViewer
+ http://news.ycombinator.com/item?id=7730415 - Things that drive me nuts about OpenGL
+ http://code.formconstantdance.org/post/79687709876/building-a-webgl-logo
+ http://news.ycombinator.com/item?id=7744969 - Learning Modern OpenGL
+ http://gamedev.stackexchange.com/questions/1128/what-are-some-good-learning-resources-for-opengl
+ http://blog.db-in.com/all-about-opengl-es-2-x-part-1/
+ http://blog.db-in.com/all-about-opengl-es-2-x-part-2/
+ http://blog.db-in.com/all-about-opengl-es-2-x-part-3/
+ http://maniacdev.com/opengl-es-tutorial-and-guide
+ http://www.dreamincode.net/forums/topic/150805-circle-in-opengl/
+ http://www.glprogramming.com/red/
+ http://androidgroup.googlecode.com/files/Unlocking%20Android.pdf
+ http://mattdesl.svbtle.com/glslify - modular and versioned GLSL
+ http://weworkweplay.com/play/introduction-to-glsl-and-fragment-pixel-shaders
+ http://www.reddit.com/r/gamedev/comments/2eb5d8/copenglsdl_game_engine_tutorials_for_an_absolute
+ http://www.joshbarczak.com/blog/?p=558 - Why Triangles

## Shaders

+ http://github.com/mattdesl/lwjgl-basics/wiki/Shaders
+ [Primer: Shaders](https://notes.underscorediscovery.com/shaders-a-primer/)
 - http://news.ycombinator.com/item?id=7536034 - Primer: Shaders
+ http://patriciogonzalezvivo.com/2015/thebookofshaders
 - http://news.ycombinator.com/item?id=9215582 - The Book of Shaders
 - https://news.ycombinator.com/item?id=11457322
+ https://www.shadertoy.com/
+ http://shaderfrog.com/
+ http://shdr.bkcore.com


## iOS

+ http://www.raywenderlich.com/3664/opengl-es-20-for-iphone-tutorial
+ http://iphone-development-source-codes.blogspot.in/2012/02/resources-for-learning-iphone-opengl-es.html
+ http://iphonedevelopment.blogspot.in/2009/05/opengl-es-from-ground-up-table-of.html

## Android

+ http://www.droidnova.com/android-3d-game-tutorial-part-i,312.html

## WebGL

+ http://medium.com/social-tables-tech/hello-world-webgl-79f430446b5c
+ http://news.ycombinator.com/item?id=8417178 - Shdr - Online GLSL shader editor and validator with live preview

```
Window coordinates
  (0,0) to (320,480)

Normalized Device Coordinates
  0,0 is center
  1,1 is top right
  -1,-1 is bottom left
Actually cube
  -1,-1,-1

Clip Coordinates
  cuts out geometry's not in bounding box

Eye coordinates - 
Have notion of camera
Frustum - 
  0,0 is center

World Coordinates
  arbitrary - no OpenGL meaning

Object Coordinates

ES1Renderer.m
  render method

glOrthof - for 2d
  around 17m in episode 19

glFrustrumf - for 3d

Transformations are applied backwards!!!

Gl_triangle_strips - reuse last 2 vertices
  28min

Clockwise means backward facing
Cclockwise is front facing

#+END_EXAMPLE

#+BEGIN_EXAMPLE
http://open.gl/

https://news.ycombinator.com/item?id=7536034

http://greggman.github.io/webgl-fundamentals/

https://news.ycombinator.com/item?id=8085385

http://greggman.github.io/webgl-fundamentals/webgl/lessons/webgl-how-it-works.html

http://pixelshaders.com
https://github.com/mattdesl/lwjgl-basics/wiki/Shaders
http://renderingpipeline.com/2014/06/whats-the-big-deal-with-apples-metal-api/

http://fgiesen.wordpress.com/2011/07/09/a-trip-through-the-graphics-pipeline-2011-index/

https://curtisautery.appspot.com/5898536285634560

http://iphonedevelopment.blogspot.com/2010/11/opengl-es-20-for-ios-chapter-4.html

http://www.khronos.org/opengles/2_X
http://www.khronos.org/opengles/sdk/docs/reference_cards/OpenGL-ES-2_0-Reference-card.pdf
http://www.sunsetlakesoftware.com/2013/10/21/optimizing-gaussian-blurs-mobile-gpu
https://github.com/jlamarche/iOS-OpenGLES-Stuff/tree/master/GLKit%20Stuff

Sending Data to the Shaders

Shaders do not have access to your application's main memory. Any data that a shader needs to do its job has to be specifically sent over to the GPU from your application code. Sending this data incurs overhead and can be a bottleneck in the rendering pipeline. In order to keep rendering performance up, it's important to only send the data that your shaders need. There are two types of data you can send from your application code to your shaders: attributes and uniforms.

An attribute is data for which you have one distinct value for each vertex being submitted.

Uniforms are the second kind of data that you can pass from your application code to your shaders. Uniforms are available to both vertex and fragment shaders — unlike attributes, which are only available in the vertex shader. The value of a uniform cannot be changed by the shaders, and will have the same value every time a shader runs for a given trip through the pipeline. Uniforms can be pretty much any kind of data you want to pass along for use in your shader.

Varyings are special variables that can be passed from the vertex shader to the fragment shader, but it's cooler than it sounds. There is no set relationship between vertices and fragments. So, how can a value from the vertex shader be used later in the fragment shader? How does it figure out which vertex's value to use? What happens with varyings is that the value set in the vertex shader is automatically interpolated for use in the fragment shader based on the fragment's pixel's relative distance from the vertices that affect it.

Variables are easy to use: you just declare them in both shaders. Then any value you set in the vertex shader will be available, in interpolated form, in the fragment shader.
---

The process of telling OpenGL ES to start rendering is kicked off by one of two function calls: glDrawArrays() orglDrawElements().

---
The OpenGL ES 2.0 spec states that there are 4 basic types of shader variables:

Vertex attributes are the per-vertex values specified in (...).Uniforms are per-program variables that are constant during program execution. Samplers are a special form of uniform used for texturing. Varying variables hold the results of vertex shader execution that are used later in the pipeline.
---

The fragment shader must now start out by setting what precision to use for floats. Why's that? Page 36 of the OpenGL ES Shading Language definition has this to say about the precisions for different variable types:

The vertex language has the following predeclared globally scoped default precision statements:

precision highp float;
precision highp int;
precision lowp sampler2D;
precision lowp samplerCube;

The fragment language has the following predeclared globally scoped default precision statements:

precision mediump int;
precision lowp sampler2D;
precision lowp samplerCube;

Simply put, the fragment shader has no default precision for floats. Even though it behaved well when we used constant values for colors before, attempting to use float variables without a declared precision will cause the shader program to not compile. So we can either use the global float precision declaration, as I have above, or explicitly set the precision of just the v_color variable with something like this:

varying mediump vec3 v_color;


---

In the WebGL model, translation matrices use the following formulae:

Something that might jump out at you is that the matrix is column-major, meaning as values are read into the matrix, they fill it up one column at a time instead of one row at a time. This can cause some confusion, since to buffer data into a matrix shader variable, it starts out in JavaScript as a flat array, typically declared like this:

var matrix = [
    a, b, c, d,
    e, f, g, h,
    i, j, k, l,
    m, n, o, p
];


...in row-major order, diagonally transposed from the OpenGL spec for a matrix. This is such a common pain point that many matrix libraries meant for use with WebGL contain a function to swap array values between column and row major layouts.
```

