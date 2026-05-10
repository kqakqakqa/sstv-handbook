# Formats of slow-scan TV transmission

## Black and white SSTV systems

The earlier modes of SSTV transmission were displayed on long
persistent monitors with radar CRT. The duration of transmission
for each image frame took 7.2 to 8 seconds, and when the last
line was received the first line was still visible. It was
possible to see the whole picture in a darkened room.

Both 7.2&thinsp;s and 8&thinsp;s modes were used in the same period. The 7.2&thinsp;s
frame speed mode, was used in Europe while the 8&thinsp;s were used
in America. The synchronization of signals is derived from the
electrical mains &ndash; 50 or 60&thinsp;Hz. If an image was synchronized
at 60&thinsp;Hz and received on 50&thinsp;Hz equipment, it was still
readable, but the image was a little distorted. For
long-distance QSOs, it was possible to change the oscillator to
achieve European or American synchronization.

The disadvantages of 8&thinsp;s SSTV are low image resolution and a loss
of synchronization due to signal interference. The loss of
synchronization could lead to the loss of a few lines or the
whole image.

The differences between modern SSTV modes and this old system
are many, but one parameter remains the same. Almost all new
systems use 1200&thinsp;Hz frequency for sync pulses and the frequency
band from 1500&thinsp;Hz (black) to 2300&thinsp;Hz (white) for video
signals. Also, the old 8&thinsp;s mode is still supported by many SSTV
programs for transmission. It is important to note that the 8&thinsp;s
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
are related to the original 8&thinsp;s mode and also have an image
aspect ratio of 1&thinsp;:&thinsp;1. The number of lines, columns or both were
simply multiplied twice. This design was used in Wraase's B&W
converters.

While Wraase's modes were derived from the European 7.2&thinsp;s mode,
Robot Research developed an original system for their
converters. Robot's modes aren't simply derived by "doubling"
parameters but are derived from line speed. While the American
60&thinsp;Hz/8&thinsp;s standard has a transfer speed of 900.0&thinsp;lpm, Robot's
line speeds for new modes were set at 600.0&thinsp;lpm so that 120
lines were transferred in 12&thinsp;s and 240 lines in 24&thinsp;s. The mode
with the best resolution has a line speed of 400.0&thinsp;lpm and a
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

<div class="figure-combo">
  <table style="">
    <thead>
      <tr>
        <th rowspan="2">Mode</th>
        <th rowspan="2">Resolution</th>
        <th>Aspect</th>
        <th>Sync.</th>
        <th>Scan line</th>
        <th>Line speed</th>
      </tr>
      <tr>
        <th>ratio</th>
        <th>(ms)</th>
        <th>(ms)</th>
        <th>(lpm)</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>7.2&thinsp;s (50 Hz)</td>
        <td>120&thinsp;×&thinsp;120</td>
        <td>1&thinsp;:&thinsp;1</td>
        <td>5.0</td>
        <td>55.0</td>
        <td>1000.0</td>
      </tr>
      <tr>
        <td>8&thinsp;s (60 Hz)</td>
        <td>120&thinsp;×&thinsp;120</td>
        <td>1&thinsp;:&thinsp;1</td>
        <td>5.0</td>
        <td>60.0</td>
        <td>900.0</td>
      </tr>
      <tr>
        <td>Wraase SC-1 8</td>
        <td>128&thinsp;×&thinsp;128</td>
        <td>1&thinsp;:&thinsp;1</td>
        <td>5.0</td>
        <td>55.0</td>
        <td>1000.0</td>
      </tr>
      <tr>
        <td>Wraase SC-1 16</td>
        <td>256&thinsp;×&thinsp;128</td>
        <td>1&thinsp;:&thinsp;1</td>
        <td>5.0</td>
        <td>115.0</td>
        <td>500.0</td>
      </tr>
      <tr>
        <td>Wraase SC-1 16 Q</td>
        <td>128&thinsp;×&thinsp;256</td>
        <td>1&thinsp;:&thinsp;1</td>
        <td>5.0</td>
        <td>55.0</td>
        <td>1000.0</td>
      </tr>
      <tr>
        <td>Wraase SC-1 32</td>
        <td>256&thinsp;×&thinsp;256</td>
        <td>1&thinsp;:&thinsp;1</td>
        <td>5.0</td>
        <td>115.0</td>
        <td>500.0</td>
      </tr>
      <tr>
        <td>64 s mode</td>
        <td>256&thinsp;×&thinsp;256</td>
        <td>1&thinsp;:&thinsp;1</td>
        <td>5.0</td>
        <td>115.0</td>
        <td>250.0</td>
      </tr>
      <tr>
        <td>Robot B&W 8</td>
        <td>160&thinsp;×&thinsp;120</td>
        <td>4&thinsp;:&thinsp;3</td>
        <td>10.0</td>
        <td>56.0</td>
        <td>900.0</td>
      </tr>
      <tr>
        <td>Robot B&W 12</td>
        <td>160&thinsp;×&thinsp;120</td>
        <td>4&thinsp;:&thinsp;3</td>
        <td>7.0</td>
        <td>93.0</td>
        <td>600.0</td>
      </tr>
      <tr>
        <td>Robot B&W 24</td>
        <td>320&thinsp;×&thinsp;240</td>
        <td>4&thinsp;:&thinsp;3</td>
        <td>12.0</td>
        <td>93.0</td>
        <td>600.0</td>
      </tr>
      <tr>
        <td>Robot B&W 36</td>
        <td>320&thinsp;×&thinsp;240</td>
        <td>4&thinsp;:&thinsp;3</td>
        <td>12.0</td>
        <td>138.0</td>
        <td>400.0</td>
      </tr>
      <tr>
        <td>AVT 125</td>
        <td>320&thinsp;×&thinsp;400</td>
        <td>4&thinsp;:&thinsp;3</td>
        <td>&ndash;</td>
        <td>312.5</td>
        <td>192.000</td>
      </tr>
      <tr>
        <td>FAX 480</td>
        <td>512&thinsp;×&thinsp;480</td>
        <td>1&thinsp;:&thinsp;1</td>
        <td>5.12</td>
        <td>262.144</td>
        <td>224.497</td>
      </tr>
      <tr>
        <td>SP-17 BW</td>
        <td>128&thinsp;×&thinsp;256</td>
        <td>4&thinsp;:&thinsp;3</td>
        <td>5.0</td>
        <td>62.0</td>
        <td>895.520</td>
      </tr>
    </tbody>
  </table>
  <div><b>Table 4.1:</b> Parameters of black and white SSTV modes.</div>
</div>

<div id="figure_sstv_ara" class="figure-combo">

  <div class="figure-item">
    <div class="figure-wrapper">
      <img src="res/sstv/rob8bw.png" />
    </div>
    <div>Robot B&W 8</div>
  </div>

  <div class="figure-item">
    <div class="figure-wrapper">
      <img src="res/sstv/rob12bw.png" />
    </div>
    <div>Robot B&W 12</div>
  </div>

  <div class="figure-item">
    <div class="figure-wrapper">
      <img src="res/sstv/rob24bw.png" />
    </div>
    <div>Robot B&W 24</div>
  </div>

  <div class="figure-item">
    <div class="figure-wrapper">
      <img src="res/sstv/rob36bw.png" />
    </div>
    <div>Robot B&W 36</div>
  </div>

  <div><b>Figure 4.1:</b> Comparison of Robot system's BW modes.</div>

</div>

### BW transmission with computer software

An example of B&W mode implemented with computers is the
AVT 125 BW mode of the *Amiga Video Transceiver* system and
it is suitable for good quality image transfer in circa 2
minutes. The mode has a vertical resolution of 200 lines because
the Amiga computer resolution was 320&thinsp;×&thinsp;200. The AVT system
is different from the previous B&W modes because it has no line
sync like WEFAX. The transmission is based on a fully
synchronous communication and the exact timing of corresponding
stations. This special feature is described in more detail in
[**Amiga Video Transceiver**](#amiga-video-transceiver) about color AVT modes.

There is also the FAX480 mode for the high-resolution
transmission, with 512&thinsp;×&thinsp;480 image resolution described
further in [**FAX480**](#fax480).

Early B&W modes Wraase and Robot, need to be synchronized with
both line and vertical synchronization. The line speed describes
the free-run speed, but in reality, it can be deviated up to
±5&thinsp;%.

Modern modes like FAX480 and AVT 125 BW need accurate precision
of line speed, because just a little deviation of values in
tenths causes image slant and distortion.

The advantage of longer transmission is improved image quality.
The disadvantage is that a lot of time is needed for the
transfer, which could be better utilized for the transmission of
color images.



[](4.2_color-sstv-modes.md ":include")

[](4.3_high-resolution-transmission.md ":include")

[](4.4_experimental-modes.md ":include")