Name: Bijan A. Hamidi
Date: Sept 23, 2017
Email: bhamidi@csu.fullerton.edu

Description: This is the gouraud shader program that is built from the phong shader file provided. The main difference between the two shader files is that with phong shading the color is calculated per fragment while gouraud shading the color is calculated per vertex then interpolated and then assigned to the fragment.  I had defined "varying vec4 myColor" to interpolate the result from the color calculation in gouraud.vert.glsl through the graphics pipeline to gouraud.frag.glsl.

Other than that minior change, almost all the code from the frag.glsl was moved to vert.glsl. This includes all calculations in the main as well as the compute light function.  Uniform variables from the CPU program where also included in vert.glsl

The result was a teapot that looks very similar to the original one created with phong shading.

My inital approach was to move as little of the code as possible over from frag.glsl.  I had started out with just the lambert calculation, but it had many dependencies from the main in frag.glsl.  I had to rethink my approach and read about the differences between gouraud and phong.  I came across some text that stated that the color attributes had to be interpolated through the graphics pipeline in gouraud and thats when I saw the error in my original approach.  

