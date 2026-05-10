# Computer image processing

This chapter focuses on a preparation of our broadcast contents &ndash;
image and photo editing before the transmission.

There are available many programs for image editing, from complex
editors for bitmap images to simple viewers with few editing functions.
Some SSTV programs have also image editing functions.

The selection of suitable program depends on a user and his needs
and although a control of programs can be slightly different the
procedures described later are so general that it would not be a problem
to achieve results using your favorite editor. The appropriate
editor is generally any program for editing of raster/bitmap images,
such as: GIMP, Paint Shop Pro, Adobe Photoshop, Pixel32, Less
suitable are vector image editors, such as: Corel Draw!, Inkscape, etc.

There are described some basic principles and functions, which
are used in most common programs. Although some functions below
are shown in GIMP, see , it should not be problem for
savvy user to find same functions in his favourite editor.

Later, see , there are specific tutorials only for GIMP.

## Image resizing

The SSTV uses a relative small resolution in comparison with images you can get
from digital cameras, scanners or some internet galleries. So before
transmission the image should be resized to conventional resolution
320&thinsp;×&thinsp;240 pixels. You can achieve this in almost all SSTV programs, but
images sometimes haven't aspect ratio 4&thinsp;:&thinsp;3 or we want use only part of
image. So it is useful to prepare your images before QSO.

The image resizing brings a little risk, see , original
image is test chart on [testchart].

Figure 1: Results of image resizing with two different algorithms.

[Image: ostatni/obr/resize_testchart_bad.png]

There is a result of two image scaling algorithms. The left image was
scaled down by *nearest-neighbor interpolation*, when pixels in
regular columns and rows are removed. But the *linear interpolation* was used for the right image. The difference is visible
on the first sight, the nearest-neighbor method caused distortion and
some details are lost completely, e.g. thin lines are lost and on
originally smooth curves are stair-like lines more evident. The linear
interpolation is more considerate to details, but it depends on
amount of decreasing and sometimes there should arise a *moiré*,
here on the raster of changing white and black stripes.

Almost every image editing software give an option for used scaling method, so
choose linear interpolation (or bilinear or bicubic). A raster image for
interpolation must have at least 16-bit color depth, on indexed images with 256
or less colors it doesn't work, but you can convert them to more colors
temporary and then back.

## Color adjustment

Basic tools for the color adjustment can edit image contrast, brightness, color
saturation and hue. The advanced tools are *curves adjustment* and *image histogram*.

The histogram is a representation of the distributions of colors in an image
(see ). It is bar graph and there is representation of
the tonal variations on the horizontal axis and the vertical axis represents
the number of pixel in the particular tone.

Figure 2: The image histogram for 256 brigtness values.

[Image: ostatni/obr/lenna_bw_256.png]

In digital photography, you can easily review exposure by histogram. If the
image is underexposed the amount of darker pixels lays on left side of graph
(more darker pixels), vice-versa for overexposed images there is high number of
lighter pixels on right side. It is possible to check exposure in the digital
camera menu and take snapshot again, of course unless the image wasn't dark or
light in principle.

The ideal case is if the luminance is wide-spread inside the luminance range.
For low contrast the luminance values are spread only over smaller range of
luminace. The histogram *equalization* can help to adjust contrast of
image &ndash; luminace is spread over all range. For the result of histogram
equalization see .

Figure 3: Positive influence of histogram equalization on image contrast.

[Image: ostatni/obr/hist_equal.pdf]

In the GIMP the tool for histogram adjustment is in menu *Colors $$ Levels*. In case of low contrast image in
the input levels were set on edges of growing values, but the GIMP can
make also automatic equalization with .

[Image: ostatni/obr/gimp_equal-en.png]

The second important tool is curve adjustment, its the one of most important
tools in professional graphics editors. It provides the complex settings of
color tone, brightness and contrast. The GIMP tool *Adjust Color Curves*
() is in menu *Colors $$ Curves*.
Its functionality is very similar across image editing software.

The work with curves is quite simple. The tool window has on the *x* axis
displayed input luminance values and on the *y* axis output values, which
are presented as gray-scale. The curve self is the function $y=f(x)$ and
it transforms input values to output and by its shaping the user sets
the parameters of the transformation.

At the beginning the transformation function is $y=x$ and therefore the output
level is equal to input. When you touch the curve by cursor a control point
appears on the curve. You can move this point in every direction and if the
option *Preview* is switched on, then the results will be shown immediately.
It is possible to add more control points for continuous transformation or you
can set any curve shape with discontinuous transformation.

What you can do with it? The results of transformations and the used curves
is in . You can spread input values by histogram and
improve contrast &ndash; A.

Another use is to darken or lighten the image, but there is many more options
how to do this then a simple setting of levels. With the curve you can focus
on a range of colors, can edit only midrange portion of color scale and keep
black and light pixels, if you hold curve in the middle and move the control
point upwards and if you move the point more to the left or right you can
change brightness of darker or lighter tones. In B are
lighter tones made more brighter and the lower end of curve is moved to the
right, so darker pixel are more darker and the image is more contrasted. For
image darkening move the point downwards, it's in C,
also there is moved the right edge of the curve so lighter pixel are more
brighter now.

For changing contrast use the curve in D, there are
two control points. The curve with "S" shape makes dark tones darker
and light tones brighter.

In addition to basic editing the curve can be used for a variety of effects,
see . The shape is little crazy and result image
lost real tones. Notice, that there is inversion of dark tones in left
part of the curve.

The curve and histogram adjustment is possible to do for image luminance and
for each color component too, so it is possible to change color perception
of an image.

[Image: ostatni/obr/lenna_krivky.pdf]

## Filters

Images can be further improved using various filters. They can serve
different purposes, mainly for smoothing and noise reduction, increasing
sharpness, edge detection, unsharp masking, etc.

Digital image itself is a discrete two-dimensional (2D) signal, which is
characterized by its frequency spectrum, whose components similar to the 1D
signal can be determined using the discrete Fourier transform. So it's possible
to modify image by using low or high pass filters or highlight certain
components to affect the final look.

For specific case, we can return to
([imgresol]), there is described how the SSTV transmission is affected
by bandwidth. The limited bandwidth caused the distortion of fine grid in
resolution test pattern (). Fine grid and sharp
gradients in the image represent a high frequency components and limited
bandwidth acted as a bandpass filter, which suppressed the higher frequencies.
Also, an image noise is represented by high frequency components and the
low-pass filter can be used for its reduction. Vice-versa, a high-pass filter
is designed to highlight the edges and sharpening.

### Convolution matrix

As one of the methods of linear filters is used the higher mathematic
procedure &ndash; *discrete convolution*. A way the image is processed
is given by *convolution kernel*, which is given by matrix, typically
with dimensions $33$ or $55$, but also others.

Figure 6: Computation of discrete convolution.

[Image: ostatni/obr/konvoluce-en.pdf]

The kernel moves pixel by pixel along lines and columns of the source image and
computes pixel values, see . It moves from first pixel
on the position 0,0, then 0,1, etc. For each pixel is from neighborhood pixels
(their numerical luminance values) multiplied by kernel values, added together
and resulting value is stored in target image on same position as source.
Then the matrix moves to next pixel and computation is repeated.

The target image changes in way defined by values of convolution kernel,
e.g. matrix $<sub>2</sub>$ in use pixel and
its neighborhood of $33$ size and computes weighted mean from
these nine pixel with kernel:

```

\startmathmatrix \NC 1 \NC{} 2 \NC{} 1 \NR
\NC 2 \NC{} 4 \NC{} 2 \NR
\NC 1 \NC{} 2 \NC{} 1 \NR
\stopmathmatrix
\right), \qquad
\eqalign{ \frac{1}{16}( 1 \cdot 50 + 2 \cdot 75 + 1 \cdot 74 + \cr + 2 \cdot 47 + 4 \cdot 76 + 2 \cdot 75 + \cr + 1 \cdot 51 + 2 \cdot 76 + 1 \cdot 74) }
= 69

```

The result is an image smoothing and noise reduction. Other matrices are used
to increase sharpness, edge detection or to create a relief.

In the GIMP the filter is in menu *Filters $$ Generic $$ Convolution Matrix*. The important parameters are also
*divisor*, which adjusts the values in the matrix and *offse* is used
to adjust the colors. See , how to set matrix values
and parameters. Furthermore you can choose the color channels and behaviour of
calculation on border pixels, it is also possible to determine the divisor and
offset automatically.

Figure 7: Convolution matrix parameters in GIMP.

[Image: ostatni/obr/conv_gimp.pdf]

### Noise reduction

Thanks to noise reduction it is possible to improve partially received SSTV or
WEFAX images by smoothing. It can be done several ways. Since SSTV transmission
takes a relatively long time the noise levels are often uneven, affected by
random interference and transmission conditions, so you can by tool *Selection* mark affected areas, where apply the filter.

#### Spatial average filtering

The simplest way to reduce noise is *average filter* with
convolution kernel $<sub>1</sub>$.

```

\frac{1}{9}\left(
\startmathmatrix \NC 1 \NC{} 1 \NC{} 1 \NR
\NC 1 \NC{} 1 \NC{} 1 \NR
\NC 1 \NC{} 1 \NC{} 1 \NR
\stopmathmatrix\right)

```

The next useful matrices for averaging are $<sub>2</sub>$ and $<sub>3</sub>$,
they aren't using neighbor pixel with same weight, but near pixels have
greater coefficients then farther. The values of the coefficients are
based on binomial series.

```

\frac{1}{16}\left(
\startmathmatrix \NC 1 \NC{} 2 \NC{} 1 \NR
\NC 2 \NC{} 4 \NC{} 2 \NR
\NC 1 \NC{} 2 \NC{} 1 \NR
\stopmathmatrix \right)\qquad
\mathbf{H}<sub>3</sub> =
\frac{1}{256}\left(
\startmathmatrix \NC 1 \NC{} 4 \NC{} 6 \NC{} 4 \NC{} 1 \NR
\NC 4 \NC{} 16 \NC{} 24 \NC{} 16 \NC{} 4 \NR
\NC 6 \NC{} 24 \NC{} 36 \NC{} 24 \NC{} 6 \NR
\NC 4 \NC{} 16 \NC{} 24 \NC{} 16 \NC{} 4 \NR
\NC 1 \NC{} 4 \NC{} 6 \NC{} 4 \NC{} 1 \NR
\stopmathmatrix
\right)

```

The disadvantage of averaging filters is that smoothing
distorts sharp color gradients and due to it thin lines
and other details are distorted.

[Image: ostatni/obr/vosa_noise.png]

Next filters for noise reduction in GIMP are in menu *Filters $$ Blur $$*. E.g. *Gaussian blur* is useful for SSTV noise
reduction, the user can set a radius of a blur. For image preparation can be
used *Selective Gaussian Blur*, it can filter continuous areas and
edges leaves unaffected, but for received images is not suitable.

#### Median filter

The term *median* is the middle value in list of numbers, here luminance
values. The image filter works with pixel neighborhood, e.g. with $33$
size, then sort their values and takes the median, i.e. middle value of the
sequence:

] 21 22 20 21 19 231 19 21 20 Pixels: 21, 22, 20, 21, 19, 231, 19, 21, 20 
 Sorted: 19, 19, 20, 20, $$, 21, 21, 22, 231 
 Average $ 43$; Median = 21 }

We see that if we use the averaging, then significantly skewed value 231, which
can be caused by noise, greatly affects the result. In contrast, the median is
not influenced by extreme deviations. The disadvantage of median filtering is
that it sometimes distorts the thin lines and sharp gradient in the image.

Figure 9: The results of noise reduction with median filter.

[Image: ostatni/obr/baba_noise.png]

In GIMP the median filter is in *Filters $$ Enhance $$ Despeckle*. There are several options for filter
settings. The radius from 1 for $33$ neighborhood to 20 for $4141$
and the black level ($-1$&ndash;255) and white (0&ndash;256). The pixels darker or
brighter than these two levels will be removed, filter passes every level for
the extreme values $-1$ and 256. Moreover, it is still possible to select *adaptive* median, when GIMP tries to determine optimal radius for given image
location automatically (the user parameters are ignored).

### Sharpening

Often happens that images from cameras or scanners have reduced sharp edges. In
this case you can try to use sharpening filters, for edges highlighting. There
are two convolution kernels for sharpening $<sub>4</sub>$ and $<sub>5</sub>$
with an even stronger effect.

```

\left(
\startmathmatrix \NC 0 \NC{} -1 \NC{} 0 \NR
\NC -1 \NC{} 5 \NC{} -1 \NR
\NC 0 \NC{} -1 \NC{} 0 \NR
\stopmathmatrix
\right)\qquad
\mathbf{H}<sub>5</sub> =
\left(
\startmathmatrix \NC -1 \NC{} -1 \NC{} -1 \NR
\NC -1 \NC{} 9 \NC{} -1 \NR
\NC -1 \NC{} -1 \NC{} -1 \NR
\stopmathmatrix
\right)

```

In the GIMP the sharpening filters are in the menu *Filters $$ Enhance $$*. The first one is *Sharpen*, and it has
similar results as kernels above and it is possible to set sharpening level and
from preview select the best results.

Figure 10: Results of image sharpening.

[Image: ostatni/obr/sharp/trx_original.png]

The disadvantage of these filters is that, it also highlights the image noise
and some other unwanted details. It can be seen in
when the filter $<sub>5</sub>$ is used, so there appears teeth on vertical
edges caused by camera interlacing. In this case it's possible to use filter
called *unsharp mask*. The unsharp mask procedure in first step apply
Gaussian blur on image copy and then check the difference between blurred and
original image. When the difference is greater then a user-defined threshold,
then both images are subtracted and the result is added to original image. The
threshold limits the sharpness of output image, so small details of certain
size is not sharpened. Thanks to this the sharpening does not apply to noise
and graininess. The digital unsharp mask is great filter for enhancing
sharpness. Some results are influenced by these three parameters:

the edge lightens or darkens, this setting will affect most the degree of
sharpening.

- *Radius* sets how much pixels around edges will be used. For smaller

radius the filter affect also smaller details, but for greater it may produce
a bright rim around edges.

- *Threshold* controls the minimum brightness change that will be

sharpened. Thanks to threshold it is possible to enhance only stronger edges
and finer leave unchanged.

No wonder, that unsharp mask is considered as king in improving the
image. The only drawback is that if you blow over it, then around edges occurs
distinctive bright rim and the image looks unnaturally.
