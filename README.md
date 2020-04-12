# Image Quilting for Texture Synthesis and Transfer

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

## Algorithm

The algorithm itself is basically:

1) Pick a block pixel size and one random block to go in the top left of the synthesized image

2) Synthesize blocks in the resulting image in raster order, left to right, top to bottom.

3) Search for a block in the original sample texture that has the minimum overlap error with what was already synthesized.

4) Paste the new block onto the result along the minimum error cut.
