## Ham radio satellites and space broadcast

For SSTV operations can be used a linear relay installed on some of the amateur
radio satellites. Amateur satellites orbiting the Earth for elliptical orbits.
*Linear relays (transponder)* performs retransmission of the wider
frequency range, typically 50 to 250\,kHz. So the satellite then transmits all
the signals (CW, SSB, ) received on the band (not like the FM ground FM
repeater to allow operations to only one user). If you have station equipped
for satellite communication you can try also SSTV.

You can also monitor experimental SSTV transmission from International Space
Station and receive SSTV signals with your 2m FM transceiver, see

Space communications provides few problems. The first of these is *Doppler effect*, named after the famous Austrian physicist, which reflects changes in
wavelength of the signal between the observer and the signal source on a moving
object. In practice this means that if the satellite is closer to your position
the signal appears to have a shorter wavelength and the receiver must tune to
higher frequencies, when the satellite is moving away it's exactly the
opposite.

Other problem is variance of signal quality due to satellite rotation, that
causes a leakage signal. The antenna with circular polarization should be used
for these purposes.

Frequency bands of linear relays are shown . These
frequencies describe satellite relay operating modes. It is fixed by satellite design on chosen by control center. The designator like U/V describes
uplink 435–438\,MHz (U) and downlink 144–146\,MHz (V). E. g. *Fuji-OSCAR\,29 (FO-29)* operates in mode V/U, the uplink is in the
range of 146,000 to 145,900\,kHz CW/LSB and downlink 435.800 to 435.900\,kHz
CW/USB. Note that relay inverts signal frequency (LSB to USB). Other satellites
carry on board the single-channel FM transmitter, such as the popular AO-27
with uplink 145,850\,kHz FM and downlink 436,795\,kHz FM.

It is required to monitor own SSTV signals on downlink, when working on linear
relays. Some sound cards support full duplex operation, so the computer can
also send and receive in same time. Then the operator changes the transmit
frequency so that receiving frequency appears to be same, just follow the
position of the syncs on spectroscope. This way compensates the Doppler effect.

During years there were many satellites used for SSTV operations, like FO-29,
VUSat OSCAR 52 (beacon 145,936\,kHz), AO-51, SO-50, etc. But satellite lifetime
is limited, in time board batteries getting weaker and ground control center
switching off transponder and waits for their recharge from solar panels. You
can find actual informations and satellite statuses on website of Amateur
Satellite Corporation, i.\,e. AMSAT.

Days of the orbital station Mir are already numbered, but as a reminder there
is description of the experiences with SSTV transmission, which took place
in Manned Amateur Radio Experiment (MAREX) in late 1998 and 1999.

The project anticipated broadcast on the frequency 437.975\,MHz, but due to
some problems with antenna systems we have to make do with only the occasional
broadcast on the two meters band.

Transmit frequency was 145,985\,MHz FM $$\,Dopplers's frequency shift.
The packet radio AX.25 BBS R0MIR-1 was normally operating on this channel.

Station at low orbit passed 5 times a day over Europe at
approximately 1.5 hours intervals.

The Robot 36 Color mode was chosen for SSTV transmission. The pictures
were sent in 2 minutes interval, so during one orbit you could copy transmission
for 10 minutes and receive about 5 pictures. Each picture was introduced
by morse code –.././/.–./–\,–\,–\,–\,–/–\,–/../.–. `DE R0MIR`
and then transmitted.

Figure 1: SSTV picture form station R0MIR.

[Image: sstv/obr/sstv_mir.jpg]

I found, that there was about $$5\,kHz frequency change caused by
Doppler's effect. So during orbit it is good to tune receiver, it's
ideal to use transceiver with continuous FM tuning (I use FT-767).
When Mir approached the horizont and it was coming near the tunning
frequency was 145,990\,MHz and when it was fly away the frequency
is lower, i.\.e. 145,980\,MHz. Some transceivers measure discrimination
of FM signal, so it is very easy to tune on carrier frequency.

Designers of SSTV station chose Robot 36 Color mode, it's not resistant
to noise, so when there is great shift from center carrier frequency the
signal used to be noisy and picture quality is distorted. The frequency
of AFSK signal transmitted throught FM channel doesn't change, so the
color distortion, known from SSB transmission, doesn't appear.

The antenna of my station for Mir monitoring was 3 element yagi with vertical
polarization (normally used for ground repeaters). I directed it to azimuth,
where Mir was nearest to my site. Later I tried to direct rotator during orbit,
the azimuth and time I had computed and it was possible also to direct yagi by
signal strength displayed on transceiver S-metr.

### SuitSat

In early 2006 (originally planned to release about 3 months earlier) were from
the International Space Station (ISS) launched the satellite in an unusual
project *ARISS (Amateur Radio on the International Space Station)*. The
satellite was named *SuitSat* (the code name is the AMSAT-OSCAR-54
[AO-54]). And its name describes the full implementation of the satellite,
because on-board equipment was built into expired Russian space suit (type Orlan).

The transnsceiver Kenwood TH-K2 was tuned to frequency 145,990\,MHz and its
power source was realized from the batteries, so its lifetime was limited to a
few weeks.

The satellite was programmed to broadcast a voice message, prepared SSTV image
(in Robot 36 Color) and telemetry data that contained information such as
measured temperature and radiation. The entire broadcast session lasts
approximately 9 minutes.

After few hours after SuitSat’s release, ham radio operators reported only weak
signals and was monitored only couple of days. Probably due to low temperature
the on-board batteries lost capacity.

The SuitSat AO-54 should starts the series of similar experiments, like
project Arissat-1.

Figure 2: SuitSat built into the spacesuit (NASA, source cat. no. ISS012E15666).

[Image: ostatni/obr/iss012e15666.jpg]

The successor of popular ham radio projects on Mir is the project *ARISS*.
The targets are to build SSTV beacon/repeater, packet radio BBS and
world-wide propagation of ham radio hobby.

The SSTV equipment on ISS consist of *SpaceCam\,1* software (from ChromaPix
authors). It runs on normal PC, support video digitizer and it can works as
repeater or transmits slide-show pictures from station cameras. The SpaceCam
transmit pictures every 120 seconds in Robot Color 36 mode and every picture is
started with morse identification (R0ISS, NA1SS).

The following frequencies are currently used:

- Voice Uplink: 144.490\,MHz for Regions 2 and 3 (The Americas, and the Pacific)

- Voice Uplink: 145.200\,MHz for Region 1 (Europe, Central Asia and Africa)

- Packet Uplink: 145.990\,MHz (Worldwide)

- Crossband FM repeater downlink: 145.800\,MHz (Worldwide)

- Crossband FM repeater uplink: 437.800\,MHz (Worldwide)

- Worldwide SSTV downlink: 145.800\,MHz

For latest ARISS news and status check the website:
