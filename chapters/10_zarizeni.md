# SSTV Equipment

## Transceiver

SSTV images can be received via a standard communication transceiver (or
receiver) that covers the HF amateur bands and supports SSB modulation or a VHF
transceiver with FM. There is no need for further modifications, although the
IF filter should not be narrower than 2.5\,kHz, a width of 3\,kHz is
recommended. The SSTV signal is taken from the audio output or headphone jack
that is plugged into the SSTV decoding device.

For transmission, a common HF or VHF transceiver with an SSTV
signal connected to the microphone jack should be used. The band in which you are
determines the usage of LSB or USB, which is the same as in voice transmission.

No transmitter modifications are necessary. But when operating SSB, it is
important to realize that the broadcast of very loud speech can be achieved
at approximately $^{3}/_{4}$ of output power, so the load of the
output amplifier is fairly low and there is no danger of overheating. But SSTV
signals transmitted via a voice channel create a 100% load due to the
presence of an auxiliary carrier.

Keep the limits set by the manufacturer for SSB operations. The usual
maximal keying with full load is about 20 minutes for professional equipment.
Modern transceivers switch on cooling during heavy load and it is not
suitable to switch off TRX immediately after the end of QSO, but wait a
few minutes for the equipment to cool down.

SSTV transmission is not dangerous, but it is advised to adhere to some safety measures.

## Station equipment for visual communication

- *Computer system* – a sound card or other special hardware interface

and software.

Figure 1: SSTV station equipped for computer operations.

[Image: sstv/obr/stanice_pc]

Currently, the most common SSTV device is a personal computer with a sound card. There
are a number of programs for personal computers with Windows, Mac, GNU/Linux
and DOS. There are also special modems (MFJ, Roy1, AOR TDF370,) or the very
simple Hamcomm modem. Hamcomm is based on a simple comparator circuit and
connected to the RS232 serial port. But it is only usable for old DOS based
software. The most varied software options are for Windows and a sound card.

Additional equipment can be used such as a web camera or a television card with
analog video input.

- *Digital scan-converter* is a stand-alone device that digitizes

received signals and stores them in memory. The decoder converts memory
content to analog signals (PAL or NTSC) for display on a normal TV set or
monitor. The converter can be connected to any color or monochrome camera, which then
transmits live images. Due to digital data processing, most
converters are equipped with a computer interface. This
allows for the addition of texts to images and the upload and storage of images to/from computer.
Tape recorders were historically often used to record SSTV and for storing QSO images.

Figure 2: An SSTV station equipped with a stand-alone SSTV converter.

[Image: sstv/obr/stanice_konv]

- Long persistence CRT monitor and circuits for signal filtering

and vertical and horizontal drives, etc. The usage of these monitors is long
over. Electro-mechanical scanners or sampling cameras were used
as SSTV signal sources in these days.

## Historical tidbits

### SSTV monitor

Long persistence monitors were the most important SSTV equipment
in the seventies. There were other commercial products available, but most
homemade monitors were built by SSTV enthusiasts.

{Monitor *Robot Model 70* and camera *Model 80* from Robot Research Inc.}

[Image: sstv/obr/robot_monitor_a_kamera.jpg]

Products from Robot Research Inc., Wraase Electronics and Venus were very popular.
These products were not produced for just the ham radio market, but were also found
in the image communication over telephone lines markets.

A typical monitor consists of several basic parts, see :
input and limiter circuits, video and sync detectors, scanning circuits,
cathode ray tube drivers and power supply. The long persistence CRTs are made
with special *photoluminescence phosphor*. In simple terms, phosphorescence
is a process in which the energy absorbed by a substance is slowly released
in the form of light. These CRTs were most used in radar displays or
oscilloscopes for the monitoring of slow processes.

The path of frequency modulated signals that contains video and syncs goes
through the limiter, where the signal is limited to constant amplitude and
then flows into image discriminator. There are video detecting circuits for
syncs and video separation here. Then signals from the discriminator are amplified
and drive both the vertical and horizontal scans. The output voltage of these circuits is
the saw-tooth voltage and drives deflection plates of long persistent CRT.

Figure 4: Block scheme of SSTV monitor.

[Image: sstv/obr/monitor]

After the separation of sync, the image signal goes to the image
intensifier and detector. After filtration, the signal is fed to the cathode ray
tube grids and modulates the electron beam. Subsequently the image is displayed on the
screen. The disadvantage of this process is that the image is seen clearest during the
reception and then the brightness fades. To be able to view the image after the
8 seconds transfer a well darkened room was necessary.

### Scanning devices

The image scanning methods used in early SSTV transmission can be
classified into electronic and electro-mechanical methods. Purely electronic systems used
cameras with a sensor element like vidicon, plumbicon or other camera
tubes.

In SSTV cameras, the vertical scan frequency was adjusted from 50\,Hz to 16.6\,Hz (i.e.
horizontal scanning frequency for 7.2s SSTV or 15\,Hz for 60Hz standard). Then
a whole camera or just a deflection unit only was rotated 90$^{}$. The TV camera
scans the image line by line, providing the sampling circuit with input. The sampling
circuits reads short samples from each line during each camera scanning beam cycle.
All the samples from scan-lines of the FSTV camera create one scan-line of slow-scan TV
picture. In the next scanning beam cycle, the sampling position moves to the left and
creates the next scan-line. The cycle is repeated until the whole picture is
sampled.

The next type of image scanner often used was a scanner with a photomultiplier for
the scanning of transparent or non-transparent originals *(FSS – Flying Spot Scanner)*. The light through transparent originals falls on the
photomultiplier, whose output is a voltage that is proportional to the transparency of
the original. This creates an amplitude modulated video signal, which can be
converted to the frequency modulated signal of SSTV.

The electromechanical scanner was used for non-transparent originals, which
were scanned from a rotating roller. The mechanical part was assembled from
a roller with the mounted original, a screw-thread for sliding and a drive unit with
a synchronous motor. The second part consisted of a lens, a light bulb, a photo
transistor and sensor circuit for the generation of the SSTV signal.

## Early FSTV/SSTV converters

SSTV/FSTV converters usually sample and digitize incoming SSTV signals
and store them in memory. Simultaneously, the memory content is read
and converted to an analog signal, which controls the fast-scan TV modulator.

The received SSTV signal is limited to the constant amplitude in input circuits and
then continues into an analog/digital converter. Digital data is processed by
the converter's microprocessor firmware. Its task is to digitize every scan-line of
the image and store it in memory. The memory capacity is equivalent to the resolution
and number of colors.

The memory is continuously read in the FSTV scanning frequency and data goes
into a digital/analog converter. The output analog signal is displayed on normal
television. The SSTV image is stored in memory until it is overwritten by
the newly received image. The reverse process of digitization of an FSTV image and its
transmission by SSTV is similar.

One of the first SSTV converters was the Robot 300 model. This converter
contains 69 transistors, 41 integrated circuits, 41 diodes and its heart
is a silicon memory tube. The function of this tube was the same as a cathode ray
tube or vidicon. The electron beam electromagnetically diffracted and focus
was directed into the scanning electrode, which consisted of a dielectric memory
layer used for analog image recording.

The modern concept of converters began with Robot 400C and its successors
450C and especially 1200C, which became available in 1986. In these
years everyone, who was serious about SSTV had to own one! A camera and
a monitor were necessary.

Figure 5: Block scheme of stand-alone SSTV/FSTV converter.

[Image: sstv/obr/1200blokc]

Robot 1200C was modified with optional EPROMs and a timing circuit, so it can be
used for operations in various SSTV modes. Its production ended in 1992, but
during the nineties there were clones available on the market – FH-21P in Germany,
SUPERSCAN 2001 in the United Kingdom, LM-9000C and Ribbit 1200C. These machines can still
be used for SSTV operations and many old-school operators own them. They are
also sometimes available in Ebay auctions.

## SUPERSCAN 2001

The production of SUPERSCAN started shortly after the end of Robot 1200C production.
Its designer Jad Bashour had worked with Martin Emmerson. SUPERSCAN
is actually a much improved 1200C and includes improved modifications to the original 1200C.
The price of this unit was about £\,750 and with additional
modules the price could exceed £\,1000.

Figure 6: The front panel of SUPERSCAN 2001

[Image: sstv/obr/ss_front_a.jpg]

Main features of SUPERSCAN 2001:

- System upgrade is simply achieved by an EPROM upgrade. Its last version 1.6 supports these modes:

- Wraase SC-1: 24, 48Q, 48, 96;

- Robot Color 12, 24, 36, 72;

- Wraase SC-2: 30, 60, 120, 180;

- AVT 24, 90, 94, 188, plus QRM, Narrow variants.

- B&W modes:

- Wraase SC-1 8, 16, 16Q, 32;

- AVT BW 125.

- Radio fax reception:

- Contains four memory banks and stores images in a resolution 256$$240 with 18bit color depth (262,144 colors).

- TV PAL decoder with delay lines for perfect image digitization.

- High speed parallel interface for computer connection.

- RGB video output.

- Control by computer mouse available (firmware 1.3).

- Text addition.

- Backup of CMOS memories for texts and configuration.

- High stability oscillator for free-run reception.

## Tasco TSC-70P

A modern type of converter is the TSC-70P (TSC-70N works with NTSC norm). This
converter includes a DSP for better reception of weak signals. It
supports all conveniences such as the automatic detection of VIS code and
free-run reception.

Figure 7: Japan converter Tasco TSC-70P.

[Image: sstv/obr/tsc-70p.png]

Supported modes:

- Scottie S1, S2;

- Robot Color 36, 72;

- AVT 90, 94 (Narrow regime, only in TSC-70N available).

Image processing is done in a real-time digitizer, and images are stored
in memory with a resolution of 416$$256 with 2 million colors. With
an optional EM-70 module, the video memory capacity can be doubled.

Tasco TSC-70P working with PAL video signal, you need to have a television
with video inputs or a color TV monitor. Control equipment is made
via an infrared remote control (WR-70) or via a RS232 serial interface.
Using EB-232VP software, images can be moved at 115 kbit/s speed
between the converter and the computer.

The desktop PC can be equipped with an optional ISA card EB-70P that triples
the speed of data exchange. For greater convenience the converter can
be controlled by a computer program i.e. HIRES-70P or WINTSC.

The converter weighs 450\,g (60\,g remote control) with dimensions of 140\,mm
(width) $$ 140\,mm (length) $$ 25\,mm (height) and it is powered
by DC 11–15\,V with a consumption smaller than 250\,mA. It is specifically
designed for mobile or portable operations and can be used with miniature
television, such as EV-5xx from CASIO, with small LCD display 7\,cm, it weighs
about 195\,g.

The VC-H1 was produced by Kenwood. It is a device intended for mobile SSTV
operations. The dimensions are similar to hand-held transceivers –
7$$3.5$$17\,cm. The unit has a built-in CCD Camera, 1.8" LCD color
monitor and a microphone. Its memory allows the storage of an uncompressed image in the
image buffer and 10 JPEG compressed images. The JPEG memory has a battery backup,
so it is possible store images when the unit is switched off.

The converter has an RS232 interface for computer connection (115\,kbit/s).
The input and output for external video signals is only NTSC.

VC-H1 is powered by four AA batteries or external DC supply with 6.0\,V. The
maximum consumption is 650\,mA when digitizing an image, otherwise the
consumption is 450\,mA when the LCD is on or 100\,mA in stand-by mode with the
LCD off.

Figure 8: Mobile SSTV converter VC-H1.

[Image: sstv/obr/vch.png]

Supported modes:

- Scottie S1, S2;

- Robot Color 36, 72;

- AVT 90, 94;

- FAST FM.
