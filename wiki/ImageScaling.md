1.  labels Featured

# Image Scaling

|| Table of Contents: || ||<wiki:toc max_depth="2" />||

In computer graphics, image scaling is the process of resizing a digital
image. Scaling is a non-trivial process that involves a trade-off
between efficiency, smoothness and sharpness. With bitmap graphics, as
the size of an image is reduced or enlarged, the pixels which comprise
the image become increasingly visible, making the image appear "soft" if
pixels are averaged, or jagged if not. With vector graphics the
trade-off may be in processing power for re-rendering the image, which
may be noticeable as slow re-rendering with still graphics, or slower
frame rate and frame skipping in computer animation.

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

Pixel art scaling algorithm is one kind of image scaling algorithm that
was designed specially for upscaling low res image multiple times. Since
a typical application of this technology is improving the appearance of
fourth-generation and earlier video games on arcade and console
emulators, many are designed to run in real time for sufficiently small
input images at 60 frames per second. Many work only on specific scale
factors: 2× is the most common, with 3× and 4× also present.
