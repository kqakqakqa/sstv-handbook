## Color SSTV modes

You might find it incredible that the first color transfer was
made before the era of digital converters using long persistence
monitors. Each color image channel was obtained using color
filters, which were subsequently held in front of the camera. A
sample result could be that the first channel transferred was
blue, then green and the last red. Slightly more difficult was
the processing on the receiver side. This was because each color
channel had to be photographed from the monitor screen and then
the resultant color picture was combined from all three
components. It was a very laborious process, but it was put into
practice a few times!

Further experiments with color SSTV transmission were based on
frame sequential transfer. Three complete images were
transferred in 8s mode and each contained one color channel,
together they formed one color image. During the broadcast, a
color original was progressively scanned with a BW camera
through each of the color filters. Received images had to be
stored in a digital converter in three different memories. When
simultaneously displayed on a color monitor they created a
full-color image. This is the reason why BW modes of Robot and
Wraase families have three different VIS codes for BW transfer.
The codes are sent for adjustment of color components for
frame-sequential transmission. Individual images were usually
sent in the order of red – green – blue. But the order of the
channels could be changed under the agreement of corresponding
stations, or some images could be broadcast repeatedly. With
such a method, it is possible to transfer only static scenes. If
an object moves during manual scanning of an image, the color
components do not correspond and the resulting image has colored
ghosts.

The transfer was not always reliable; due to interference and
fade-outs, the image component had to be sent several times. And
in practice, it was sometimes problematic to complete all color
channels. To improve color transmission the *line sequential* transfer was developed. The principle is that it
transmits a single image and each scan-line carries all three
color components. Receiving equipment can already display
color images during transmission. This method where the color
image is transferred in one frame is referred to as *SFC – Single Frame color*.

More properties of SSTV systems will be introduced in following
sections, with all their pros and cons and details of mode formats
described in detail.

### Wraase SC-1

This line sequential system was first among newly developed
SFC systems. Wraase SC-1 comes from the workshop of famous SSTV
engineer Volker Wraase, DL2RZ. The system was most likely created by
modifying existing equipment to operate in 8s
mode or for frame-sequential transmission.

Each scan-line begins with 6.0ms sync, then a green component
follows and then the blue and red components. Separate sync
of 6.0\,ms length precedes each color component.

Wraase SC-1 has a major deficiency. If the receiver loses sync
during interference, then the display system loses the ability
to synchronize colors. Because all lines are sent in the same
way, the color components cannot be recognized and the
probability that the system reverts to correct color sync is
equal to one-third. In practice, the system works, but when the
noise level is too high, the received image contains few color
bands as the converter loses and restores synchronization. For
this reason, an additional sync pulse was added to subsequent
productions of the SC-1 converter. It consists of a truncated
5ms sync before the red line, which is immediately followed by a
short pulse of 2300\,Hz frequency lasting 1-2 ms. It allows the
converter to regain synchronization after the noise subsides.
Additional synchronization occurs as a thin red stripe in the
left edge of the image.

All SC-1 modes have an image aspect ratio of 1\,:\,1. The
original SC-1 mode is the 24s mode with 128 lines, so the image
quality is not better than the 8s mode, but the colors improve
the picture.

The system was soon upgraded for modes with the longer
transmission. First, the number of lines was doubled to 256 and
the transfer extended to 48 seconds. The last SC-1 96s mode has
a better horizontal resolution for good image quality.

The professional converter Wraase Electronics SC-1 was most
popular in Germany, but its market share was lower in comparison
to the Robot converters produced in the same period.

Wraase SC-1 24 Color 24 s 128$$128 G–B–R 6.0 54.0 54.0 54.0 333.3 Wraase SC-1 48Q Color 48 s 256$$128 G–B–R 6.0 108.0 108.0 108.0 175.4 Wraase SC-1 48 Color 48 s 128$$256 G–B–R 6.0 54.0 54.0 54.0 333.3 Wraase SC-1 96 Color 96 s 256$$256 G–B–R 6.0 108.0 108.0 108.0 175.4 }

### Robot color system

The *Robot* modes are named according to the converters
in which they were implemented. They are scan-converters Robot 400C,
450C and 1200C. They were produced in San Diego by Robot Research Inc.

They do not use RGB color coding as SC-1, but YCrCb. Scan-lines
consist of a luminance signal $Y$ followed by differential
chrominance signals $R-Y$ and $B-Y$. Due to this, the color
modes are compatible with their B&W variants. So a 12s color
mode can be displayed by 8s monitors, etc.

From a total of 8 modes, 4 are intended for color transmission.
Half of the color modes use YCrCb in a 4:2:0 format. The
scan-line contains only one chrominance signal, and colors are
obtained from the average of two adjacent lines in the original
image. The other two modes use the 4:2:2 format and send all
color information in one scan-line.

The original Robot system uses asynchronous transfer. To receive
the image, it is needed to detect the vertical sync (VIS code).
And for proper reception of the image, the sync pulse must be
detected. This process is a major disadvantage.

Figure 1: Two scan-lines of Robot 36 Color when color bars are sent.

[Image: sstv/obr/scan_r36-en.pdf]

The scan-line is composed of the starting sync, followed by a
short 3.0ms gap of 1500\,Hz and then the image part with
luminance and chrominance. The chrominance differential signals
begin with additional sync pulses. The 1500Hz sync is before
$R-Y$ and the second 2300Hz is before $B-Y$. Due to the
additional sync with a different sync frequency, it is possible
to re-synchronize 4\,:\,2\,:\,0 formats after an interruption.
The chrominance syncs are separated from the scan-line with
1500Hz gap that lasts 1.5\,ms.

Figure 2: The scan-line of Robot 72 Color when the color bars are sent.

[Image: sstv/obr/scan_r72-en.pdf]

The main disadvantage of the Robot modes lies in color-coding
because the receiver must be perfectly tuned to the SSTV signal.
Otherwise, the image hue is distorted when the deviation is
greater than $50$\,Hz. For this reason, Robot Research
introduced the transmission of a gray gradation scale at the
beginning of image transfer and the receiver device can
auto-tune for a video signal.

The whole frame has 256 or 128 lines, of which the first 16 or 8
lines are reserved just for gradation scale. Some converters and
PC software add some basic station info, such as call sign, and
this part of the frame is called "header".

The memory storage capacity of the Robot 1200C converter allows
it to store an image with a resolution 256$$240 pixels or
four images with 128$$120, and they are displayed in a
4\,:\,3 aspect ratio.

The fastest mode of the Robot family and the fastest color SSTV
mode is the 12s mode. It contains 120 lines transmitted in the
4:2:0 format. Another mode is 24s with a 256$$120
resolution and 4:2:2 color format. The other two modes allow
the transfer of images in 256$$240 resolution, either in
less quality for 36 seconds in a 4:2:0 format or in better
quality in 4\,:\,2\,:\,2 format for 72 seconds.

Figure 3: Comparison of Robot color modes.

[Image: sstv/obr/rob12col.png]

Although the Robot modes were pushed away by modern synchronous
modes that are more resistant to interference, the 24s and 36s
modes are faster than modes with RGB color coding and have
better resolution than RGB modes with the same transmission
time. You can find their benefits on VHF with FM transmission
because it eliminates the need for precise tuning.

Robot 36 Color was used in MAREX, SAREX
and ARISS programs for SSTV transmission from orbital stations
Mir, ISS and space shuttle missions. It is a pretty good
compromise between image quality and transfer time, because
space stations on low earth orbit can be received within just 10
minutes during their orbit.

] Resolution Color Compatible name time format B&W mode Robot 12 Color 12\,s 160$$120 4\,:\,2\,\,:0 Robot B&W 8 Robot 24 Color 24\,s 320$$120 4\,:\,2\,\,:2 Robot B&W 12 Robot 36 Color 36\,s 320$$240 4\,:\,2\,\,:0 Robot B&W 24 Robot 72 Color 72\,s 320$$240 4\,:\,2\,\,:2 Robot B&W 36 Mode Color Sync pulses of Scan-line Speed name sequence line color color Y R$-$Y B$-$Y (lpm) Robot 12 Color YCrCb 7.0 3.0 — 60 30 600.0 Robot 24 Color YCrCb 12.0 6.0 6.0 88 44 44 300.0 Robot 36 Color YCrCb 10.5 4.5 — 90 45 400.0 Robot 72 Color YCrCb 12.0 6.0 6.0 138 69 69 200.0 }

### The Martin synchronous system

The creator of this popular system is Martin Emmerson, G3OQD. He
originally named it "New Modes", but to avoid confusion
between other newly emerging SSTV modes, the community
universally named modes after their creators. The Martin was
created to overcome SFC problems in systems like SC-1 due to two
main changes.

The first change was that instead of three separate syncs before
each color component, there is just single sync sent before
each scan-line. The horizontal sync lasts 4.862\,ms. After the
horizontal sync, the green component is sent, then blue and last
is the red component. Between each color component, there are
short gaps of 1500\,Hz lasting 0.572\,ms. Just like in the SC-1,
the sequence green – blue – red was chosen. Regardless of the
order in which components are sent, the image quality will not
change. But it is important that the receiving device identifies
which component is being currently received.

Figure 4: Scan-line of Martin M1 when color bars are sent.

[Image: sstv/obr/scan_m1-en.pdf]

An important feature of using only one sync before beginning the
color scan-line sequence is that a converter will not replace
the individual color components and degrade the color
information. In time intervals where the line sync is not
transmitted, the gaps are filled with a reference level of black
at 1500\,Hz for 0.572\,ms.

The second improvement has a substantial effect on image
reception. Unlike the Robot or SC-1, the detection of horizontal
syncs is not necessary during the reception. And the broadcast
between stations is fully synchronized. The results of the use
of such a system are sharper images and more contrasted edges.
Although the transmission conditions on the lower HF bands often
do not allow the transfer of the image in 100% quality, old
systems relying on line sync usually lose synchronization in
such conditions.

The Martin system was originally implemented as a modification
of the Robot 1200C converter and it preserves the transmission
of the header gradation scale.

Figure 5: A comparison of systems in real conditions on the 3.7MHz band.

[Image: sstv/obr/srobot.png]

Line syncs and inner scan-line gaps have a similar duration at
all four speeds, but the number of lines and horizontal
resolution for each mode is different. Although the syncs aren't
necessary for transmission, they are still transmitted at the
beginning of each scan-line in order to synchronize the
converter at any time during the reception. It is important
because it consumes a lot of broadcast time and the station does
not have to wait for the start of a new frame, but a receiver
can get synchronization at any time during transmission.

The Martin system allows us to work with four different modes/speeds. The most
popular version is the Martin M1 with 256 lines per frame in two minutes. Other
modes of the Martin system have either half the line or half the horizontal
resolution of the best quality M1. The mode M4 has the lowest quality and 128
lines. Modes Martin M1 and M2 are often used between European stations.

Martin M1 114 s 320$$256 G–B–R 4.862 146.432 146.432 146.432 134.3947532 Martin M2 58 s 160$$256 G–B–R 4.862 73.216 73.216 73.216 264.5525975 Martin M3 57 s 320$$128 G–B–R 4.862 146.432 146.432 146.432 134.3947532 Martin M4 29 s 160$$128 G–B–R 4.862 73.216 73.216 73.216 264.5525975 }

### Scottie

These modes were created by Eddie T. J. Murphy, GM3SBC. He
modified the original firmware of Wraase SC-1. Martin Emmerson
also implemented Scottie modes to Robot 1200C later on.

Scottie has the same improvements as the Martin system does, but
its scan-line composition and scan timing are different.

After vertical synchronization, the sequence of scan-lines is; a
1.5ms short gap of 1500\,Hz, then a green component, a 1.5ms
short gap again, a blue component, then horizontal sync,
another gap and lastly, a red component. This unusual order is
the result of the system adaptation to SC-1, where the
additional sync was used right before the red component. Syncs
are permanently sent for any time synchronization during
the reception.

The Scottie relies on exact timing like the Martin, although the
original version for SC-1 was not fully synchronous and syncs
were still processed by the converter. But in newer systems the
modes are implemented for free-run reception, so the system is
equivalent to the Martin.

The implementation of Scottie in Robot 1200C slightly differs
because the first scan-line includes an additional 9.0ms sync at
the beginning of the scan-line right after vertical
synchronization. All other modes implemented in Robot 1200C have
sync at the beginning of the scan-line but the Scottie has the
sync in the middle of the scan-line which then caused color
distortion. Perhaps some other implementation of Scottie has
this difference too.

The Scottie system also has four conventional modes (and a
special one described later). Two with 256 lines per frame and
two with 128 lines. The difference in timing is not the same as
in the Martin, where the line speed of the faster mode is
exactly twice the speed of the slower mode, so the speed of the
faster mode is lower than twice that of the slower mode.

Image quality in the Scottie and Martin modes is the same.
Theoretically, slightly better quality can be achieved in Martin
M1 than in Scottie S1 due to longer transmission, but the
difference is imperceptible.

The Scottie S1 and S2 are quite popular for North American
stations and can often be heard on high-frequency bands.

#### Scottie DX – special mode for long-distance transfers

This mode of the Scottie family achieves the best possible
results in the transmission of slow-scan television images.
There is one simple reason for this; the transmission takes
about 2.5 times longer than Scottie S1.

There is an extended duration of the scan-line, but the duration
of sync and gaps between color components remained the same.
This improvement is best seen on the receiving side. The longer
transmission time supports better image quality.

The improvement relies on the fact that; each pixel can be read
more times during signal sampling and that the loss of a few
samples does not affect the overall quality. It means that each
pixel takes a long time and this gives better noise and phase
distortion immunity. But these qualities are compensated by a
very long image transmission time of about 4.5 minutes. During
this time, two images with the same resolution can be sent with
other RGB modes.

The Scottie DX mode offers high-quality images, but sometimes
the optimal conditions for DX connections do not last long
enough for the transfer of a whole picture.

Scottie S1 110 s 320$$256 G–B–R 9.0 138.240 138.240 138.240 140.1148942 Scottie S2 71 s 160$$256 G–B–R 9.0 88.064 88.064 88.064 216.0667214 Scottie S3 55 s 320$$128 G–B–R 9.0 138.240 138.240 138.240 140.1148942 Scottie S4 36 s 160$$128 G–B–R 9.0 88.064 88.064 88.064 216.0667214 Scottie DX 269 s 320$$256 G–B–R 9.0 345.600 345.600 345.600 57.12653528 }

AVT modes were originally intended for SSTV operations with
Amiga computers. AVT author Ben B. Williams, AA7AS developed a
dedicated interface and software which was produced by AEA
(Advanced Electronic Applications Inc.). Although the creator
claimed that this system was a revolution in SSTV transmission,
these modes did not gain popularity like other modes. The AVT
modes are practically not in use today.

A reason for this could be the fact that the manufacturer wanted
to keep the image scan parameters of the system, secret.
However, by intercepting signals and reverse engineering, the
parameters of the AVT modes were implemented in other devices by
the SSTV community. This was done without the additional
software tools that made the AVT unique.

The AVT system contains four of line sequential RGB modes and
one B&W. The scan-lines have no gaps between color components
and a really unusual thing is that; the modes do not use any
horizontal sync. Another unusual feature is the mandatory
function of vertical synchronization, that is sent as a digital
header before the image transfer begins.

The AVT family contains 5 modes and each of them has the
following four options:

- Default variant is the same as conventional SSTV modes,

but does not have any line syncs.

- *Narrowband variant* uses a shorter band for video

signals from 1700\,Hz for black to 2100\,Hz for white.

- *QRM variant*, that uses picture interlacing just like

in analog television.

- The combination of the QRM and narrowband variant.

The fastest mode is the AVT\,24 with 120 lines and it is
transferred for 31 seconds. The next mode is AVT\,90 with a
resolution of 256$$240 and an image quality slightly worse
than in the Martin M1. ATV\,90 sends each color component in
125.0\,ms, thus the speed is 2048 pixels per second (in binary
notation this gives a nice rounded number). The other two modes
have somewhat atypical resolutions in comparison with other SSTV
modes, but these resolutions are normal system resolutions on
Amiga computers. It is AVT\,94 with 320$$200 and AVT\,188
with the same line speed, but twice the scan-lines –
320$$400. The image is displayed in an aspect ratio of
4\,:\,3{} in both cases.

For some SSTV systems/scan-converters, the detection of vertical
sync is a must. So, the VIS code is repeated three times for
accurate reception. VIS is necessary for image reception when
*no* line sync is sent and later synchronization is not
possible. The original AVT software does not need to
receive VIS but relies more on the digital header.

After a series of VIS code, there is a digital header (see
is a sequence of 32 frames of 16 bits. Each frame contains only
8 bits of information, but it is sent twice – first in normal
form and second inverted. Normal and inverted parts can be
compared for error detection. Each frame starts with a 1900Hz
pulse while data modulation uses 1600\,Hz for the representation
of logical zeros and 2200\,Hz for logical ones. Narrow-band
variants use 1700\,Hz for zeros and 2100\,Hz for ones. Both
variants use a modulation speed of exactly $2048/20=102.4$\,Bd,
so the data pulse has a length of 9.766\,ms.

Figure 6: The digital synchronization header of AVT\,90 mode (VIS 68, normal variant).

[Image: sstv/obr/AVT90_synchro-en.pdf]

The first three bit of each 8bit word identifies the mode:

- 011 – AVT\,94, AVT\,188, AVT\,125\,BW,

- 101 – AVT\,90.

The last five bits are used as a count down before image
transmission. These five bits are important for an
accurate set of image initiation and synchronization. They vary
between all 32 binary combinations during transmission. At least
one binary code must be properly detected. In the beginning, all
bits are in 0 states with 1 in inverted parts. When the
countdown starts, all five-bit sequences run (e.g. for AVT\,24):

`010 00000 101 11111 010 00001 101 11110 010 00010 101 11101 010 11101 101 00010 010 11110 101 00001 010 11111 101 00000`

When the count down gets to zero, the image scan-lines are sent.
AVT reception depends on the first eight seconds of
synchronization, for some implementations without the ability to
synchronize later. Although the AVT modes are quite reliable,
noise could cause a loss of the whole image. Sometimes it is not
possible to receive a digital header due to interference, even
if the interference later disappears. However, the original AVT
software was capable of image reconstruction in this case.
Because the image data is completely synchronous, the data
simply has to be shifted in memory until the RGB data is aligned
correctly, and then the image comes out perfectly. Again, the
AVT system provided means to hot reconfigure the data after the
reception. So reception without/after sync header worked fine.

The earlier listed options for each mode can improve its
performance. The first is the narrow-band transmission which
uses a 400\,Hz band from 1700\,Hz (black) to 2100\,Hz (white).
With an appropriate filter, the resistance to interference can
be improved with minimal loss of image quality. For instance;
the 400 Hz wide CW filter can be used with a variable IF shift.

The second option is the "QRM mode", where an entire image is
sent interlaced. Within the first half of image transmission
time, half of the scan lines (every odd one) is sent. Then the
scan loops back to the beginning and sends the remaining half of
lines (even lines). The fact that some of the distorted lines of
the first field are interlaced with fine lines received from the
second will improve the overall subjective impression of image
quality. The original AVT software also contains tools for handy
image improvement – it is possible to select distorted lines
and the program will reconstruct them by averaging neighborhood
lines. It is also is possible to shift the second field
horizontally independently of the first field. This allows you
to compensate if there is a significant multi-path delay in
regard to the two fields.

In ATV implementations, the system can work well without these
interactive tools. But in practice, especially on shortwaves
where conditions change quickly; the second field could be
phase-shifted and this causes the notable "toothy" edge of
the picture. The QRM option can be combined with the narrow-band
mode.

AVT\,24 31\,s 128$$120 R–G–B — 62.5 62.5 62.5 960.000 AVT\,90 98\,s 256$$240 R–G–B — 125.0 125.0 125.0 480.000 AVT\,94 102\,s 320$$200 R–G–B — 156.25 156.25 156.25 384.000 AVT\,188 196\,s 320$$400 R–G–B — 156.25 156.25 156.25 384.000 AVT\,125\,BW 133\,s 320$$400 Y — 312.5 192.000 }

### Wraase SC-2

A later version of Wraase modes was first built in the newer
converter SC-2 from Wraase Electronics. Again, it provides
another variant of line sequential systems. The author dropped
the sequence of colors used in the earlier SC-1 converter, so
the colors are now sent in the order: red – green – blue.
Additionally, there is only one horizontal sync at the beginning
of each line, just as in the Scottie and Martin.

Unlike other systems, the RGB system in the SC-2 has one
characteristic that distinguishes it from other conventional
modes. Image transfer is achieved when the transmission time for
the green component is equal to the sum of the transmission time
of the red and blue components, i.e. the ratio 2\,:\,4\,:\,2 of
R\,:\,G\,:\,B components. Between color components, short gaps
are not sent.

As we already know that the human eye is most sensitive to green
by more than 50\,%. The remaining 50\,% in SC-2 is split
evenly between the red and blue components. Red and blue
components are not processed for a differential signal. This
color reduction is not visible on common pictures, but it may
happen that some images (e.g. B&W mosaic) may lose color
information. The system is less precise for color
interpretation in comparison with YCrCb modes but better in
tuning resistance. One disadvantage of color reduction is found
when green shadows appear on the image in stations without
precise clock timing.

This mode is preferable in comparison to YCrCb because bad
tuning will only reduce the contrast or saturation, but the hue
is not distorted. Occasional green shadows remain as a tax for
reduced transmission time.

The Wraase SC-2 family just like all other systems also has four
different modes. The SC-2\,180 offers the best quality for
three-minute transmission, and unlike the previous modes does
not use the RGB ratio 2\,:\,4\,:\,2 and is, therefore, a faster
alternative to the Scottie DX mode. The two-minute SC-2\,120
uses the RGB format 2\,:\,4\,:\,2. The remaining two modes,
SC-2\,30 with 128 and SC-2\,60 with 256 lines have about half of
the resolution found in SC-2\,120.

Wraase SC-2 30 30 256$$128 R–G–B 5.0 58.0 117.0 58.0 249.600 Wraase SC-2 60 60 256$$256 R–G–B 5.0 58.0 117.0 58.0 249.600 Wraase SC-2 120 120 320$$256 R–G–B 5.0 117.0 235.0 117.0 126.175 Wraase SC-2 180 180 512$$256 R–G–B 5.0 235.0 235.0 235.0 84.383 }
