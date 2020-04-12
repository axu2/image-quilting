# Image Quilting for Texture Synthesis and Transfer

![Demo](abstract_screenshot.PNG)

To quote the original paper's abstract at https://people.eecs.berkeley.edu/~efros/research/quilting.html:

>We present a simple image-based method of generating novel visual appearance 
in which a new image is synthesized by stitching
together small patches of existing images. We call this process image quilting.

>First, we use quilting as a fast and very simple texture
synthesis algorithm which produces surprisingly good results for
a wide range of textures.

>Second, we extend the algorithm to perform texture transfer – rendering an object with a texture taken from
a different object. More generally, we demonstrate how an image
can be re-rendered in the style of a different image.

>The method
works directly on the images and does not require 3D information.

In this repository, we will be implementing the paper using Python and NumPy.

## Texture Synthesis

The algorithm starts with an input image and a block size:

![input block](input.png)

We then define a minimum cost path between the overlap of two blocks:

![error](slide.png)

We then build up a synthesized image by tiling small blocks of the input image.

![build](build.png)

(a) Here, we just randomly choose blocks

(b) Here we pick blocks that have the least overlap error

(c) We do everything in (c) but also cut along the minimum error boundary.
