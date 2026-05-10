For digital SSTV and RDFT or HamDRM system is used tuning indicator, which
displays spectrum of SSB channel. The image showed by indicator is created
using discrete Fourier transformation. The indicator displays new samples on
top and the old samples disappear at the bottom and the whole spectrogram is
moving down so the indicator was nicknamed *waterfall*.

In the and you can see
station and software identification and also messages about reception
confirmation, request for repeat or more complex pictures also.

The principle of "waterfall images" is based on Fourier transformation
and the fact, that the signal can be compiled from a huge number of harmonic
waves. If the proper harmonic are compiled, so the resulting carrier wave
has frequency spectrum, that will look like desired image.

Figure 1: The principle of waterfall image display.

[Image: dsstv/obr/smajlik.pdf]

The utility `PicFall.exe` can be used for generating sound file
from picture. You can find it on website of DIGTRX author. The input
file is a bitmap in BMP format and output is WAV audio file.
