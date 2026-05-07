## High resolution transmission

High-quality images consume a lot of memory but memory was very
expensive in early computer systems. High-resolution images were
a real luxury, but over the years memory has gotten cheaper,
therefore modern SSTV systems now have modes for high
resolution broadcast too.

The synchronous mode was the first high-resolution mode. It was
first implemented in the ViewPort VGA interface and software for
IBM PCs in 1993. The old VGA cards with 256\,kB of memory can
hold an image with a resolution 640$$480 with only 16
colors. This provides only grayscale images, so this mode is
used for only B&W transmission.

The image resolution of FAX480 is 512$$480 and the
transmission time is 138 seconds. In the early days of high
resolution transmission, the only way to transmit hi-res images
was facsimile mode (see
).
So the creator Ralph Taggart, WB8DQT called it FAX480, but
compared with classic facsimile there are not many similarities.

The synchronization of the FAX480 is derived from the reference
frequency of 4.0 MHz, and a time unit is
$4\,/2048=1953.125$\,Hz.

Vertical sync is resolved as follows. In the first five seconds
a rectangular frequency modulation of 244\,Hz between the black
(1500\,Hz) and white (2300\,Hz) levels is transmitted. This
creates the APT .} signal.

The tone 1500\,Hz is transmitted for 4 time units
($4=2.048$\,ms) and 2300\,Hz for 2.048\,ms
too. This gives a frequency of an ATP tone also 244\,Hz
($1/[2.048+2.048]=244$ Hz). This sequence is then repeated
exactly 1,220$$. Originally the system did not use the VIS
code, but the code 85 was later added.

Originally, vertical sync is followed by a phasing interval of
20 white lines. Each begins with 5.12 ms sync 1200\,Hz (10-time
units), but this interval is omitted in some implementations.

Now it's time to transfer the image itself. It is composed of 480 lines. Each
line begins, unlike the facsimile, with 1200Hz sync with a length of 5.12\,ms
and then continues a scan-line with 512 pixels. The duration of the scan-line is
$512(1/1953.125)=262.144$\,ms.

According to the creator, the horizontal resolution of 512 points was selected just because
the FAX480 operating software had a control menu to the left of the screen.

### Pasokon TV

These synchronous modes were released with *Pasokon TV*
interface from John Langer, WB5OSZ. These modes retain essential
SSTV parameters. They also used color-coding to transmit the
individual color components in the order of red – green – blue
with the format 1\,:\,1\,:\,1.

There are three modes in the Pasokon system. They have different
transmission times: 3, 5 or 7 minutes, so the image quality
differs.

Each mode has a default timing for scan-lines:

- Pasokon P5 3200\,Hz

- Pasokon P7 2400\,Hz

The scan-line starts with a sync pulse of 20 time units, then
there is a 5 unit black gap followed by the red component. It
has 640 units, so there is one unit for each pixel. There are 5
unit black gaps between color components and at the end of the
scan-line before the sync of the next line. These gaps should
help improve the detection of syncs.

Pasokon P7 has the best image quality and longest transmission
time which takes nearly seven minutes. If we split such an image
into four equal parts, the image quality of one of them would
correspond to that produced by the Martin M1 or Scottie S1
modes. The upper 16 lines are used for gray scale and the
remaining 480 for your the image itself.

There are also two other modes with 480+16 lines. The P5 has a
transfer time of almost 5 minutes with lower image quality and
the P3 runs fastest at three minutes with a horizontal
resolution about half of a P7.

A potential disadvantage of these modes is quite a long transfer
time, which makes it difficult to use on highly variable
short-waves. For those who do not mind the long transmission
times, it can be used for exchanging pictures on VHF.

Pasokon P3 203\,s 320$$496 R–G–B 5.208 133.333 133.333 133.333 146.56488550 Pasokon P5 305\,s 640$$496 R–G–B 7.813 200.000 200.000 200.000 97.70992366 Pasokon P7 406\,s 640$$496 R–G–B 10.417 266.667 266.667 266.667 73.28244275 }

### PD modes

PD modes are the result of a cooperation between Paul Turner
G4IJE and Don Rotier K0HEO. The mode was first introduced in May
1996 and it was developed to improve image quality and
especially to reduce transfer times in comparison with Pasokon
TV.

For speeding up the transmission, YCrCb color coding is used in
the 4\,:\,2\,:\,0 format. If you divide the total time between
two syncs by four, the result is the actual time for each color
component. The scan-line begins with 20.0ms sync, then there is
a 2,080\,ms gap of black, and the first luminance signal $Y_1$.
It is followed by chrominance signals $R-Y$ and $B-Y$ without
any gap. Then there is a second luminance $Y_2$. The exact
timing of modes is:

- PD-50 – 286\,$$s/pixel

- PD-90 – 532\,$$s/pixel

- PD-120 – 190\,$$s/pixel

- PD-160 – 382\,$$s/pixel

- PD-180 – 286\,$$s/pixel

- PD-240 – 382\,$$s/pixel

- PD-290 – 286\,$$s/pixel

YCrCb color coding needs accurate signal tuning to prevent
color distortion. Thanks to wide horizontal sync, it is possible
to detect frequency deviation and compensate color distortion.
There is also the gray scale on the top of the image for tuning
detection.

The main advantage is reduced transmission time compared with
RGB modes. The PD-290 mode supports a resolution of
800$$600 and its transfer time is nearly five minutes,
although at the cost of little color loss. Some modes have
resolutions of 640$$480, while PD-160 has 512$$384.
The fastest two-minute PD-120 has a worse image quality, but in
many cases, it is still sufficient. Besides the five modes with
high-resolution, the system includes two with standard
resolution. PD-90 uses 320$$240 and has a better image
quality than Martin M1 or Scottie S1, because it is based on a
longer transmission time per pixel. The last mode is the very
fast PD-50, which provides a similar resolution as Scottie S2.

$}{$R-Y$}{$B-Y$} PD-50 50 s 320$$240 Y-C 20.0 91.520 91.520 91.520 309.150866 PD-90 90 s 320$$240 Y-C 20.0 170.240 170.240 170.240 170.687301 PD-120 126 s 640$$480 Y-C 20.0 121.600 121.600 121.600 235.997483 PD-160 161 s 512$$384 Y-C 20.0 195.854 195.854 195.854 149.176545 PD-180 187 s 640$$480 Y-C 20.0 183.040 183.040 183.040 159.100552 PD-240 248 s 640$$480 Y-C 20.0 244.480 244.480 244.480 120.000000 PD-290 289 s 800$$600 Y-C 20.0 228.800 228.800 228.800 128.030044 }
