# Formats of slow-scan TV transmission

## Black and white SSTV systems

The earlier modes of SSTV transmission were displayed on long
persistent monitors with radar CRT. The duration of transmission
for each image frame took 7.2 to 8 seconds, and when the last
line was received the first line was still visible. It was
possible to see the whole picture in a darkened room.

Both 7.2s and 8s modes were used in the same period. The 7.2\,s
frame speed mode, was used in Europe while the 8\,s were used
in America. The synchronization of signals is derived from the
electrical mains – 50 or 60\,Hz. If an image was synchronized
at 60\,Hz and received on 50\,Hz equipment, it was still
readable, but the image was a little distorted. For
long-distance QSOs, it was possible to change the oscillator to
achieve European or American synchronization.

The disadvantages of 8s SSTV are low image resolution and a loss
of synchronization due to signal interference. The loss of
synchronization could lead to the loss of a few lines or the
whole image.

The differences between modern SSTV modes and this old system
are many, but one parameter remains the same. Almost all new
systems use 1200\,Hz frequency for sync pulses and the frequency
band from 1500\,Hz (black) to 2300\,Hz (white) for video
signals. Also, the old 8s mode is still supported by many SSTV
programs for transmission. It is important to note that the 8s
mode has the shortest transfer time and should be used in
special conditions.

### Modes for digital converters

There are many modes for B&W image transmission which differ in
transfer time and resolution. Wrase and Robot modes are
implemented in modern converters; the transfer is extended to
256 lines and the transmission time is also prolonged to
achieve better horizontal resolution.

Historically common modes are the 16-second mode with 128 lines,
the 32-second mode with 256 lines and the 64-second mode with
256 lines; which provides maximal image quality. All these modes
are related to the original 8s mode and also have an image
aspect ratio of 1:1. The number of lines, columns or both were
simply multiplied twice. This design was used in Wraase's B&W
converters.

While Wraase's modes were derived from the European 7.2s mode,
Robot Research developed an original system for their
converters. Robot's modes aren't simply derived by "doubling"
parameters but are derived from line speed. While the American
60\,Hz/8s standard has a transfer speed of 900.0\,lpm, Robot's
line speeds for new modes were set at 600.0\,lpm so that 120
lines were transferred in 12s and 240 lines in 24s. The mode
with the best resolution has a line speed of 400,0\,lpm and a
total transmission time of 36 seconds.

The Robot SSTV system reserves the first 16 or 8 lines (for a
240 or 120 line image) for gradation grayscale. The scale can be
used to tune the signal more precisely.

Although Robot Research cooperated with Copthorne MacDonald,
they ignored the trend in amateur construction of digital
converters with doubled modes. Nevertheless, the Robot converter
*Robot 300* became quite popular despite the high price tag
of over $800 in the mid-seventies.

During the '70s and '80s, the ham radio market was not the only
outlet for SSTV converters, but companies found opportunities in
the telecommunication market and sold SSTV monitors and cameras
as devices for image transmission over telephone lines.

,aligncharacter=yes,align=middle] Mode Resolution Aspect Sync. Scan line Line speed ratio (ms) (ms) (lpm) 7.2s (50 Hz) 120$$120 1:1 5.0 55.0 1000.0 8s (60 Hz) 120$$120 1:1 5.0 60.0 900.0 Wraase SC-1 8 128$$128 1:1 5.0 55.0 1000.0 Wraase SC-1 16 256$$128 1:1 5.0 115.0 500.0 Wraase SC-1 16 Q 128$$256 1:1 5.0 55.0 1000.0 Wraase SC-1 32 256$$256 1:1 5.0 115.0 500.0 64\,s mode 256$$256 1:1 5.0 115.0 250.0 Robot B&W 8 160$$120 4:3 10.0 56.0 900.0 Robot B&W 12 160$$120 4:3 7.0 93.0 600.0 Robot B&W 24 320$$240 4:3 12.0 93.0 600.0 Robot B&W 36 320$$240 4:3 12.0 138.0 400.0 AVT 125 320$$400 4:3 — 312.5 192.000 FAX 480 512$$480 1:1 5.12 262.144 224.497 SP-17 BW 128$$256 4:3 5.0 62.0 895.520 }

### BW transmission with computer software

An example of B&W mode implemented with computers is the
AVT 125 BW mode of the *Amiga Video Transceiver* system and
it is suitable for good quality image transfer in circa 2
minutes. The mode has a vertical resolution of 200 lines because
the Amiga computer resolution was 320$$200. The AVT system
is different from the previous B&W modes because it has no line
sync like WEFAX. The transmission is based on a fully
synchronous communication and the exact timing of corresponding
stations. This special feature is described in more detail in

There is also the FAX480 mode for the high-resolution
transmission, with 512$$480 image resolution described
further in .

Early B&W modes Wraase and Robot, need to be synchronized with
both line and vertical synchronization. The line speed describes
the free-run speed, but in reality, it can be deviated up to
$$ 5\,%.

Modern modes like FAX480 and AVT 125 BW need accurate precision
of line speed, because just a little deviation of values in
tenths causes image slant and distortion.

The advantage of longer transmission is improved image quality.
The disadvantage is that a lot of time is needed for the
transfer, which could be better utilized for the transmission of
color images.

Figure 1: Comparison of Robot system's BW modes.

[Image: sstv/obr/rob8bw.png]
