1.  labels Featured

# Image Scaling

|| Table of Contents: || ||<wiki:toc max_depth="3" />||

  - Image scaling\* is the process of resizing a digital image. Scaling
    is a non-trivial process that involves a trade-off between
    efficiency, smoothness and sharpness. As the size of a raster image
    is reduced or enlarged, the pixels which comprise the image become
    increasingly visible, making the image appear "soft" if pixels are
    averaged, or jagged if not. With vector image the trade-off may be
    in processing power for re-rendering the image, which may be
    noticeable as slow re-rendering with still graphics, or slower frame
    rate and frame skipping in computer animation.

Apart from fitting a smaller display area, image size is most commonly
decreased (or subsampled or downsampled) in order to produce thumbnails.
Enlarging an image (upsampling or interpolating) is generally common for
making smaller imagery fit a bigger screen in fullscreen mode, for
example. In “zooming” a bitmap image, it is not possible to discover any
more information in the image than already exists, and image quality
inevitably suffers. However, there are several methods of increasing the
number of pixels that an image contains, which evens out the appearance
of the original pixels.

## Pixel Art Scaling Algorithm

  - Pixel art scaling algorithm\* is one kind of image scaling algorithm
    that was designed specially for upscaling low res image multiple
    times. Since a typical application of this technology is improving
    the appearance of fourth-generation and earlier video games on
    arcade and console emulators, many are designed to run in real time
    for sufficiently small input images at 60 frames per second. Many
    work only on specific scale factors: 2× is the most common, with 3×
    and 4× also present.

### EPX/Scale2×/AdvMAME2×

  - Eric's Pixel Expansion (EPX)\* is an algorithm developed by Eric
    Johnston at Lucas Arts around 1992, when porting the SCUMM engine
    games from the IBM PC (which ran at 320×200×256 colors) to the early
    color Macintosh computers, which ran at more or less double that
    resolution. The algorithm works as follows:

Later implementations of this same algorithm (as AdvMAME2× and Scale2×,
developed around 2001) have a slightly more efficient but functionally
identical implementation:

The AdvMAME4×/Scale4× algorithm is just EPX applied twice to get 4×
resolution.

### Scale3×/AdvMAME3×

  - The AdvMAME3×/Scale3×\* algorithm can be thought of as a
    generalization of EPX to the 3× case. The corner pixels are
    calculated identically to EPX.

### Eagle

Eagle works as follows: for every in pixel we will generate 4 out
pixels. First, set all 4 to the colour of the in pixel we are currently
scaling (as nearest-neighbor). Next look at the pixels up and to the
left; if they are the same colour as each other, set the top left pixel
to that colour. Continue doing the same for all four pixels, and then
move to the next one.

Assume an input matrix of 3×3 pixels where the center most pixel is the
pixel to be scaled, and an output matrix of 2×2 pixels (i.e., the scaled
pixel)
