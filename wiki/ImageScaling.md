1.  labels Featured,Supplement

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

  - Eagle\* works as follows: for every in pixel we will generate 4 out
    pixels. First, set all 4 to the colour of the in pixel we are
    currently scaling (as nearest-neighbor). Next look at the pixels up
    and to the left; if they are the same colour as each other, set the
    top left pixel to that colour. Continue doing the same for all four
    pixels, and then move to the next one.

Assume an input matrix of 3×3 pixels where the center most pixel is the
pixel to be scaled, and an output matrix of 2×2 pixels (i.e., the scaled
pixel)

### 2×SaI

2×SaI, short for 2× Scale and Interpolation engine, was inspired by
Eagle. It was designed by Derek Liauw Kie Fa, also known as Kreed,
primarily for use in console and computer emulators, and it has remained
fairly popular in this niche. Many of the most popular emulators,
including ZSNES and Visual Boy Advance, offer this scaling algorithm as
a feature.

Since Kreed released the source code under the GNU General Public
License, it is freely available to anyone wishing to utilize it in a
project released under that license. Developers wishing to use it in a
non-GPL project would be required to rewrite the algorithm without using
any of Kreed's existing code.

### Super 2×SaI and Super Eagle

Several slightly different versions of the scaling algorithm are
available, and these are often referred to as Super 2×SaI and Super
Eagle. Super Eagle, which is also written by Kreed, is similar to the
2×SaI engine, but does more blending. Super 2×SaI, which is also
written by Kreed, is a filter that smooths the graphics, but it blends
more than the Super Eagle engine.

### Hqx

  - Hqx\* is an algorithm developed by Maxim Stepin. The hqx family
    consist of hq2x, hq3x, and hq4x for scale factors of 2:1, 3:1, and
    4:1 respectively. Each algorithm works by comparing the colour value
    of each pixel to those of its eight immediate neighbours, marking
    the neighbours as close or distant, and using a pregenerated lookup
    table to find the proper proportion of input pixels' values for each
    of the 4, 9 or 16 corresponding output pixels. The hq3x family will
    perfectly smooth any diagonal line whose slope is ±0.5, ±1, or ±2
    and which is not anti-aliased in the input; one with any other slope
    will alternate between two slopes in the output. It will also smooth
    very tight curves. Unlike 2xSaI, it anti-aliases the output.

hqnx was initially created for the Super Nintendo emulator ZSNES. The
author of bsnes has released a space-efficient implementation of hq2x to
the public domain.

### xBR

  - xBR\* is a pixel art scaling algorithm that scales by rules. It was
    developed by Hyllian in 2011 mainly as scaling filters for video
    game emulators. He introduce his algorithm for the first time in a
    forum at byuu.org, a Nintendo emulator project. Like Hqx, xBR
    algorithm family also consist of 2xBR, 3xBR, and 4xBR for scale
    factors of 2:1, 3:1, and 4:1 respectively.

This algorithm works by detecting edges and interpolating pixels along
those edges. It assumpted edges as pixel regions in the image where
pixels are very distinct among them along some direction (high color
frequency) and very similar perpendicular to that direction (low color
frequency).

xBR comes with two variants, one which blending image colors for
smoothing the results and other which not blending image colors (xBR (No
Blend)) so that the results looks a bit jaggies. However The advantages
of xBR (No Blend) are it maintains image sharpness, because it doesn't
produce additional colors, so that the number of unique colors between
the original and the results remain same. Thus the xBR (No Blend) can be
used recursively for scaling image multiple times without loss of
sharpness although only 3xBR \[NoBlend\] that can gives optimal results
while 2xBR (No Blend) and 4xBR (No Blend) will produce stair effect for
45 degree of lines.
