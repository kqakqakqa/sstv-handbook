## Line speed

One of the most important parameters that is suitable for SSTV
mode selection is the total time required to transfer an image.

Due to present transmission speeds, SSTV is becoming similar to
radio facsimile. Therefore, the mode parameters are not defined
by horizontal and vertical scan rates, but in the number of
lines transferred in one minute – *lines per minute (lpm)*.

Line speed depends on the selected mode and varies in the range
from 57\,lpm (Scottie DX), for high-quality transmission of
colour image (320$$240) in nearly five minutes, up to
1000\,lpm for BW image (128$$128) in just 8 seconds. SSTV
modes and their properties are described below.

## Black & white transmission

For a black and white (BW) monochromatic image broadcast, only
one signal is needed. It represents brightness/luminance $Y$ of
each image element.

The frequency ranges from 1,500\,Hz (black) to 2,300\,Hz (white)
transmit image information. Each frequency in this range
represents specific brightness – the level of gray.

Human vision can distinguish brightness in a wide range, but can
only adapt to the geometric mean value of actual brightness.
Around this value, about 100 to 110 grayscale levels can be
differentiated.

Based on this fact; an ideal transmission could be regarded as
128 gray levels. At this figure, the average observer would not
normally see transitions between adjacent grades.

Figure 1: The scan line of BW image.

[Image: sstv/obr/cbmody.pdf]

If we want to transmit images in 128 gray levels, this is the
distance of signal levels 800\,Hz\,/\,128\,=\,6.25\,Hz. The
lowest frequency is for black and the highest is for white, the
remaining 126 gray levels lay in the linear range between these
two frequencies.

An issue with the transfer of more gray levels, for example 256
levels, is that it puts increased demand on the demodulator. The
demodulator must be able to compensate for the frequency shift
between the transmitter and the receiver. In this case, the
distance between the two levels of brightness is 3.125\,Hz and
it is necessary to have a relatively large distance from the
interference on the communication path, to assure a pure
transfer of all grayscale.

Normally, we can settle for a less bright resolution where it
is possible to choose the transfer of only 64 levels. This
requires less of the demodulator because it only needs to
distinguish between 12.5\,Hz steps.

True reproduction of colour images in grayscale is another
issue. Human vision cannot perceive the bright intensity of all
three colour components at the same time. When we watch three
lights (red, green and blue) of the same intensity, the human
perception considers the green light the brightest. Red and blue
are not as bright in our perception.

But a BW television camera only scans the level of intensity,
and therefore the resulting image would look like all the
colours are the same. They will be characterized by the same
gray-level depending on their intensity. Due to this fact, a
valid grayscale image $Y$ created from basic colour components
$R$, $G$ and $B$ (red, green and blue) is defined as:

```


```

Note that the biggest factor 0.59 is just for the green, so
nearly 60\,% of colours that we can see depend on the green
component and only 40\,% is of the remaining colour
components! This is used for simplicity in colour scan
converters for BW images. In past years, BW images were not
transmitted as true grayscale images, but the brightness signal
was derived from the green component of the image. The
difference in brightness between a true BW image and the green
component of the same image is insignificant in most cases.

Figure 2: Decomposition of colour image to basic components.

[Image: sstv/obr/slozky/ara-r.jpg]

## Colour transmission

### Additive colour model

Every colour can be decomposed into three primary colours –
red, green and blue. The additive colour model produces other
colours by combining these three primary colours.

During image transmission, the image is decomposed into these
independent colour components on the transmitting side. Then
they are gradually transferred, and on the receiving side, the
components are re-composed into a colour image.

Figure 3: Decomposition of colour image into RGB signals.

[Image: sstv/obr/modelrgb]

If it is possible to detect about 64 frequency levels in the
800\,Hz video channel, then each colour component contains 64
brightness levels. And the resulting colour image then contains
$64 64 64=256144$ colours. If a demodulator can
distinguish 256 levels, it is possible to transfer over 16
millions $=256^3$ colours. Colour SSTV transmission can meet the
most demanding requirements of colour depth.

Some colour SSTV systems also use a property of human vision,
which is a different sensitivity to the primary colour
components. In this case; the image scan-lines are not divided
into three equal parts for each colour component. Because the
eye is most sensitive to green, the largest part of the line
takes just this part and the remainder is filled with red and
blue parts. For example, the ratio is 4\,:\,2\,:\,2 for
$G$\,:\,$R$\,:\,$B$.

The additive colour model is a method of transmission that takes
more time to transmit, but it provides a transfer of true
colours.

The second type of colour transmission is called *YCrCb*. In
fact, it is a similar system as is used in colour fast-scan
television, where each colour component $R$, $G$ and $B$ , are
transformed to *luminance* and *chrominance* (colour
information) signals. Unlike RGB, the transmission time of an
image is shorter. This colour coding is used for BW and colour
compatibility in television broadcasts. In which colour
broadcasts can also be received by a BW television.

Figure 4: Decomposition of colour image into YCrCb signals.

[Image: sstv/obr/modelyuv]

The image scan-line contains colours transformed into two
components – luminance and chrominance. The chrominance signal
is composed of two differential colour signals $R-Y$ and $B-Y$.
Signal $Y$ is called *luminance* and contains the signal
corresponding to brightness produced by the equation $Y= 0.30R +
0.59G +0.10B$. The $Y$ is for chrominance signals subtracted
from the red and blue components.

On the receiving side, the individual colour components are
restored: $R = (R-Y) + Y$ and $B = (B-Y) + Y$.

We need a third green component the $G$, which is derived from
$R-Y$ and $B-Y$ from the expression $G=Y-0.51(R-Y)-0.19(B-Y)$.
Hereby we get complete colour signals.

There are two formats of YCrCb colour transmission used in SSTV.
The first format 4\,:\,2\,:\,2 transmits both chrominance
signals (within half the time in comparison with $Y$) in one
line. The second format 4\,:\,2\,:\,0 contains only one chroma
signal. Odd scan-lines could include for instance $R-Y$, and the
even scan-lines could be $B-Y$. The chrominance signal is then
given by the average of two consequent scan-lines of the
original image.

The advantage of this type of transfer to RGB is significantly
shorter transmission time. In comparison to RGB transmission,
YCrCb takes approximately half the time yet guarantees almost
the same image quality.

Its disadvantage compared with the RGB model, is a loss of image
information which is higher when the 4\,:\,2\,:\,0 format is
used. Also, precise transceiver tuning is needed, otherwise the
colour information will be distorted. This is the reason why the
YCrCb encoding is used less frequently. According to the
positive or negative deviation from the carrier, the image is
strongly hued to pink or green, see .

Figure 5: Color distortion of YCrCb when the station is improperly tuned.

[Image: sstv/obr/yuv_error.pdf]

The transmission for colour FSTV uses YCrCb and also uses
special methods and modulation (in PAL, SECAM) to eliminate this
colour distortion, which can occur on the transmission path.
Unfortunately, this feature does not exist in SSTV and so the
result of selective fading can cause colour ghosts in the image.

SSTV systems using YCrCb transmission are less resistant to
interference than their RGB counterparts, see

Figure 6: Color distortion of RGB when the station is improperly tuned.

[Image: sstv/obr/rgb_error.pdf]

The RGB model is distorted by a low contrast or increased
brightness when there is significant deviation of $ 200$\,Hz
from the transmitter carrier and thus provides better colours
than YCrCb.

## Synchronization

There are two types of synchronization – *synchronous* and
*asynchronous*.

Older SSTV systems use asynchronous transmission. This means
that each information frame, in our case a scan-line, will be
received after the detection of horizontal sync.

This system detects vertical (image) and horizontal (scan-line)
syncs and only after proper detection will it display the
received lines. The asynchronous transmission has a huge
disadvantage. When interference happens close to the 1200\,Hz
frequency, an SSTV device can lose several scan-lines if
interference remains.

In this respect, all new SSTV systems are improved and use
synchronous transmission. These systems use *free-run* scan.
It is not necessary to receive vertical sync and it is possible
to begin reception from any scan-line. After the initial
synchronization, it is not required to detect horizontal sync.
Thanks to this, synchronous systems are much more resistant to
interference. Scan-line syncs are still transmitted and then
reception could start any time during transmission.

The disadvantage of the free-run scan is in complying with the
very precise line speed of the corresponding parties. The line
speed must be absolutely the same. If the values are
different, there is an unpleasant effect on the picture –
slant. For more information on this subject see
.

Vertical synchronization is used to detect the start of
transmission. The receiving device can automatically begin the
image scan after vertical sync.

The Robot Research company developed a new form of vertical
synchronization called *Vertical Interval Signaling* – VIS.
All modern SSTV systems adopted the VIS and use these longer
syncs and digital headers for automatic SSTV mode recognition.

The VIS contains digital code, the first and last bits are the
start and stop bits with 1200\,Hz frequency. The remaining 8
bits provide mode identification and contain one *parity bit*. Each bit is transmitted in order from the least
significant bit.

Figure 7: Structure of VIS with value 42.

[Image: sstv/obr/viskod.pdf]

*Parity* is used for simple error checking. SSTV use even
parity. This means, that the number of logical ones must be even
in the whole 8bit code. If the number of ones in 7 bits is odd,
then the parity bit is set to one. If the number is even, the
parity bit is zero. Since the information part of code has 7
bits, it takes 128 values.

Each bit is 30\,ms long, so the modulation speed is 33.3\,bauds.
The frequency 1300\,Hz means the state of logical zero and
1100\,Hz logical one. The first half of code (least significant
bits, LSB) specifies the type of mode (BW/colour, resolution).
The second half (most significant bits, MSB) contains
information about the system (Robot, Martin, AVT,). The
last bit is reserved for parity error checking.

] MSBLSBMeaning P 6 5 4 3 2 1 0 0 0 Color composite video 0 1 BW, red component 1 0 BW, green component 1 1 BW, blue component 0 Horiz. resolution 128\,/\,160 pixels 1 Horiz. resolution 256\,/\,320 pixels 0 Vertical resolution 128\,/\,120 lines 1 Vertical resolution 256\,/\,240 lines 0 0 0 Robot 0 0 1 Wraase SC-1 0 1 0 Scottie, Wraase SC-2 0 1 1 Scottie, Wraase SC-2 1 0 0 AVT, Scottie DX 1 0 1 AVT, PD 1 1 0 PD 1 1 1 Pasokon TV X Parity bit }

The meaning of bits is valid for a
system based on the Robot Research standard. As the number of
new modes has expanded, the bit combination has no additional
meaning.

{ Mode decimalhexa.binary Martin M1 44 0x2C 0101100 Martin M2 40 0x28 0101000 Robot 36 colour 8 0x08 0001000 Robot 72 colour 12 0x0C 0001100 Scottie S1 60 0x3C 0111100 Scottie S2 56 0x38 0111000 Scottie DX 76 0x4C 1001100 Wraase SC-2 180 55 0x37 0110111 }

The comprehensive table of all VIS code is on
[chap5::biglist]}{[biglist]}.

Figure 8: The vertical synchronization of Martin M1, the VIS code value is 44.

[Image: sstv/obr/vis_m1.pdf]

There is a vertical synchronization in
(44 decimal). The parity bit is `1`, and first three bits
`010` distinguish the Martin system. The vertical and
horizontal resolution can be determined from the value of the
second nibble – `1` 256 lines and `1` 320 columns, the
last two bits with value `00` mean colour transmission.

### Additional synchronization data

Some SSTV software appends a signal with additional data to the
synchronization, e.g. call sign identification, which can then
be decoded and used as an input for an electronic station log.
Unfortunately, these additional signals have no standardized
format and they are not compatible with other SSTV programs.

Some of them append the data transmission to the first scan-line
image (ChromaPix) or even prior to the broadcast of VIS (WinPix,
MMSSTV).

Some newly developed SSTV systems do not use standard VIS code
with 8 bits and send 16 bits (MP, MR, ML modes) or use odd
parity for error checking. This is because of $2^7$, from which
128 possible combinations of the VIS code is almost exhausted.
Differences in these and other systems will be described in
further chapters.
