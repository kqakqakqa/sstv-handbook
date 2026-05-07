## Experimental modes

During the years of the SSTV boom many modes were created, but
never gained popularity. Many of them are totally forgotten,
like WinPix GVA, Proscan J-120, WA7WOD system or ScanMate,
although some of them have a few interesting features which we
are about to delve into.

### MSCAN TV

The modes TV-1 and TV-2 were one of many experiments in the SSTV
transmission field. An interesting feature is the use of *interlaced* transmission. They do not use the same half-frame
interlacing like normal television does. But the whole image is
divided into four quarter-frames. These frames are transmitted
gradually in the direction from top to bottom, so you can get a
first preview of the image after the first quarter of
transmission time, but only in low resolution. Thanks to
interlacing, the resolution increases gradually during
transmission up to 320$$256.

It is possible to receive these modes with conventional
equipment without interlacing support, because of their line
speed are the same as for Wraase SC-180 (TV-1) and Martin M1
(TV-2) modes. But in this condition, the image will contain four
bars with all quarter-frames.

Figure 1: MSCAN TV image interlacing.

[Image: sstv/obr/mscan_60.png]

### Kenwood FAST FM

This mode is built in the mobile SSTV converter *Visual Comunicator VC-H1* from Kenwood (see
). This
unit support some normal modes and the "FAST FM" mode.

The FAST FM mode sends video signals in the 2800\,Hz (black) to
4400\,Hz (white) band. The vertical synchronization and VIS code
format are similar to Robot's standard, it has a value of 90
but uses odd parity (the number of logical ones must be odd).
After the VIS code there is a digital header and then an image
with a resolution of 320$$240.

The duration of one scan-line is 53.6\,ms, so the total
transmission time for an image is 13.5 seconds. The mode uses
YCrCb color coding in the 4\,:\,2\,:\,0 format. The brightness
signal occupies 35.4\,ms of scan-line, and than there is a pulse
of 3600\,Hz that lasts 0.41\,ms and then color signals are sent.
Each even scan-line contains $R-Y$ and odd line $R-Y$. The
scan-line is ended by 0.41\,ms pulse again. The transmission of
a whole image is ended by a one-second pulse of 1900\,Hz.

Due to fast transmission, the used bandwidth of FAST FM is in
1.0 to 6.2\,kHz range, so it cannot be used in the SSB voice
channel, but only in FM channels on VHF. The image quality is
comparable to the Robot 36 Color mode.

These modes were created by Makoto Mori, JE3HHT, the author of
MMSSTV software. Some of these modes became quite popular, because
of the success of MMSSTV. The author created modes with both standard and
high resolutions. They use YCrCb colors and extended VIS code. Some
modes use a narrower band for syncs and video signals.

Figure 2: The comparison of modes in real conditions on the 3.7MHz band.

[Image: sstv/obr/test_m1.jpg]

The change he made to the traditional VIS specification extends the code
by 8 extra bits, so a 16-bit code is sent instead. The first 8 bits (LSB)
are the same for each mode with a value of 35 (0x23) that identifies the system.
While the remaining bits (MSB) distinguish a particular mode. Odd parity is used as a simple check.

Figure 3: The 16-bit VIS code of MP115 mode with a 0x2923 value.

[Image: sstv/obr/vis_mp115-en.pdf]

VIS used in narrowband modes has very little in common with the
original standard. Initially, during vertical synchronization *N-VIS* pulses of 1900Hz and 2300Hz in 100\,ms are sent, followed by
a start bit of 1900\,Hz (see ).

All code bits have a duration of 22\,ms (modulation speed is 45.45\,Bd). Logic one has
1900\,Hz and logic zero 2100\,Hz. The code word length is 24 bits and
it is divided into four groups of 6 bits, bits are sent in the following
order:

Each group has the following meaning:

- Group 1 (15–10) = 010101

- Group 2 (25–20) = N-VIS

- Group 3 (35–30) = 010101 `xor` N-VIS

For example, MP73-N has N-VIS = 000010 (0x02) and the whole code word is:

101101\,010101\,000010\,010111.

Figure 4: Vertical synchronization and scan-line of the MP110-N narrowband mode.

[Image: sstv/obr/mp110-n-en.pdf]

MP modes use the same principle as PD modes. The sync takes
9.0\,ms followed by a short 1500\,Hz gap of 1.0\,ms, then odd
scan-line $Y$ brightness is sent followed by the $R-Y$ and $B-Y$
chrominance signals. The chrominance signals are the average of
two neighborhood scan-lines. The scan-line is ended by the even
$Y$ luminance signal. This sequence is repeated 128$$.

MP modes also have narrowband variants (MPxx-N) and their video
signals occupy frequencies from 2044 to 2300\,Hz.

The MR and ML modes use YCrCb color coding in 4\,:\,2\,:\,2
format, same as the Robot 72 Color mode. Horizontal syncs are
the same as in MP modes. The scan-line begins with luminance
$Y$, then 0.1\,ms gap is sent followed by $R-Y$, a gap, and
$B-Y$, the line then ends with a 0.1ms gap. These gaps should
have the same frequency as the last pixel of the previous color
component. The MLxx group has a high resolution of
640$$496.

The MC-N modes are narrowband, but they use RGB color coding.
Horizontal pulses last 8.0\,ms and are followed by a 0.5\,ms gap
of 2044\,Hz. The order of color components is red – green – blue.

{ Mode Transfer Resolution VIS Color Scan-line (ms) Speed name time 16-bit sequence Sync Y R–Y B–Y (lpm) MP115 115\,s 320$$256 0x2923 YCrCb 9.0 223.0 223.0 223.0 133.037694 MP140 140\,s 320$$256 0x2a23 YCrCb 9.0 270.0 270.0 270.0 110.091743 MP175 175\,s 320$$256 0x2c23 YCrCb 9.0 340.0 340.0 340.0 87.591241 MR73 73\,s 320$$256 0x4523 YCrCb 9.0 138.0 69.0 69.0 419.140761 MR90 90\,s 320$$256 0x4623 YCrCb 9.0 171.0 85.5 85.5 340.618791 MR115 115\,s 320$$256 0x4923 YCrCb 9.0 220.0 110.0 110.0 266.489007 MR140 140\,s 320$$256 0x4a23 YCrCb 9.0 269.0 134.5 134.5 218.858289 MR175 175\,s 320$$256 0x4c23 YCrCb 9.0 337.0 168.5 168.5 175.361683 ML180 180\,s 640$$496 0x8523 YCrCb 9.0 176.5 88.25 88.25 330.305533 ML240 240\,s 640$$496 0x8623 YCrCb 9.0 236.5 118.25 118.25 248.292986 ML280 280\,s 640$$496 0x8923 YCrCb 9.0 277.5 138.75 138.75 212.276667 ML320 320\,s 640$$496 0x8a23 YCrCb 9.0 317.5 158.75 158.75 185.960019 Mode Transfer Resolution N-VIS Color Scan-line (ms) Speed name time sequence Sync Y R–Y B–Y (lpm) MP73-N 73\,s 320$$256 0x02 YCrCb 9.0 140.0 140.0 140.0 210.526316 MP110-N 115\,s 320$$256 0x04 YCrCb 9.0 212.0 212.0 212.0 139.860140 MP140-N 140\,s 320$$256 0x05 YCrCb 9.0 270.0 270.0 270.0 110.091743 SyncRGB MC110-N 110\,s 320$$256 0x14 R–G–B 8.0 143.0 143.0 143.0 137.142857 MC140-N 140\,s 320$$256 0x15 R–G–B 8.0 180.0 180.0 180.0 109.389243 MC180-N 180\,s 320$$256 0x16 R–G–B 8.0 232.0 232.0 232.0 85.166785 }

### Martin HQ

The Martin HQ system from Martin Emmerson's workshop was
released at the end of 1996. These modes were developed for
Robot 1200C, SUPERSCAN 2001 and other compatible converters with
the EPROM version 4.6, or 1.6. Unlike previous Martin modes,
they use YCrCb color coding. The transmission time of
chrominance signals is half of the luminance (format
4\,:\,2\,:\,2). There are 6 signals sent between two doubled
syncs. The first three signals create an odd scan-line:
luminance $Y$, $R-Y$, $B-Y$. And the next three signals contain
even scan-line: luminance $Y$, $Y-R$, $Y-B$. The opposite
"polarity"
distortion when signals are not tuned precisely. The HQ1 mode
has 90 seconds for image transmission and HQ2 has 112 seconds,
both use 256 vertical lines.

I had once QSO on 20m with the station equipped also with the
Superscan 2001 scan-converter and we were able to exchange a few
pictures in HQ1 mode and the quality was outstanding.

In the early 2000s, Martin developed a new SSTV interface for
IBM PCs called *ACE SSTV* and added two additional modes, HQ3 and
HQ4. HQ3 has the same scan line timings and color information as
HQ2 but with 72 scan lines (instead of 128), and HQ4 is
identical to HQ1 but also 72 scan lines. As each scan line
produces two screen lines, the resolution of HQ3/4 is 144
vertical lines.

Unfortunately, the author refused to disclose the exact
specification of the system, so this improved system is not
commonly found. However, during the time of its introduction, an
author of WinPixPro software (Don Rotier, K0HEO)
reverse-engineered HQ1 and HQ2 modes. Christoph Nadig, HB9ZHK
used WinPixPro signals to implement these modes into his
iDigi SSTV software for MacOS and thanks to that we have now
specifications of all four Martin HQ modes.

Scan line is started by two sync pulses with a gap: 6.5\,ms
1200\,Hz, then 4.75\,ms 2100\,Hz, then 6.5\,ms 1200\,Hz, then
4\,ms 1800 Hz (total of 21.75 ms).

Then the video signals are sent in 4:2:2. For HQ1, luminance
$Y$ is sent for 170\,ms, followed by chrominance $Cr$ for
85.75\,ms and $Cb$ for 85.75\,ms. This is followed by a gap of
0.5\,ms 1500\,Hz, then the information of the second screen line
is sent: luminance $Y$ for 170\,ms, followed by chrominance
$$ (inverted $Cr$) for 85.75\,ms and
$$ (inverted $Cb$) for 85.75\,ms, and another gap of 0.22\,ms
1500\,Hz.

HQ2 has the same composition of the scan-line, but the duration
of luminance $Y$ is 212.5\,ms, and chrominance $Cr$ and $Cb$ are
106.5\,ms each and back porch gaps are 0.429\,ms.

}$ Cb/$}$ (lpm) Martin HQ1 320$$256 21.75 170 85.75 85.75 170.09934 Martin HQ2 320$$256 21.75 212.5 106.5 106.5 137.35022 Martin HQ3 320$$144 21.75 212.5 106.5 106.6 137.35022 Martin HQ4 320$$144 21.75 170 85.75 85.75 170.09934 }

Figure 5: Two screen-lines of Martin HQ2 mode, when color bars are sent.

[Image: sstv/obr/HQ2_bars-en.pdf]

### Wraase W1 and W2

Volker Wraase DL2RZ in his later interface SC-4 *SSTV-PC-Scanconverter* brought two new modes: W1 and W2. These
modes are special in using an RGB color model, but with a ratio
of 2\,:\,2\,:\,1, so the blue color component has only half of
the horizontal resolution. Which also helps to reduce the
required transmission time, but it has less color distortion
than previous SC2 modes, which are reducing both red and blue
color components.
