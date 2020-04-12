# Image Quilting for Texture Synthesis and Transfer

Image quilting is a technique of generating new images 
by stitching together patches of existing images.

It has applications of 

1) Texture synthesis, generating arbitrarily large textures from small real-world samples and 

2) texture transfer, re-rendering an image in the style of another.

## Algorithm

The algorithm itself is basically:

1) Pick a block pixel size and one random block to go in the top left of the synthesized image

2) Synthesize blocks in the resulting image in raster order, left to right, top to bottom.

3) Search for a block in the original sample texture that has the minimum overlap error with what was already synthesized.

4) Paste the new block onto the result along the minimum error cut.
