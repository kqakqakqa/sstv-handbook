## DSSTV software selection

There is several programs available supporting HamDRM and RDFT.

Software RDFT HamDRM Web page DIGTRX 3.11 DigiACE V1.9 DigPAL EasyPAL HamPAL RDFT RXAMADRM (Linux) SSTV-PAL Multimode WinDRM

## Making QSO

Digital SSTV is not spread too far. There are few station found
sporadically on the 14MHz band. But there is also working party of
German stations on the 3.7MHz band around the frequency 3.733\,kHz
almost daily in the evening. Stations use only HamDRM system.
Listening to their signals is a good opportunity to try DSSTV
reception and get some practice with it, also try to make contact.
After that, you already know how there is used special modulation
schematic and error-correcting coding it is important to see if it at
all works and how. Will be there SSTV digitalization boom?

Some opponents of digital video broadcast claim, that in conditions where we
can receive noisy, but still usable analog TV signal, the digital TV cannot be
received at all. And same argument can say opponents of digital-SSTV. When
there are good conditions, it is possible only to tune on channel, images are
received automatically and operator should not do anything. When interference
gets stronger and signal weaker there can help more data instances or bad
segment report and additional repetition of bad segments. But when we only
guess HamDRM signal drowned in high noisy level the reception is impossible.

The DSSTV traffic can be found on band near the centre of SSTV activity. Also
hamspirit rules should be observed and we should be considerate to
another traffic on the band. Sometimes it takes a little tact to explain
to uninformed station, that the strange rattling sound is the digital signal
from your QSO partner.

A CQ call can be done by sending picture on free frequency. HamDRM during
transmission broadcast station id, so is you don't receive complete data you
can see what station is transmitting. After the end of transmission you can
call the station by voice.

For reception confirmation or short message transfer there is used waterfall
messages – messages displayed in tuning indicator. Principle of these messages
is described in next and example of some message see in .

Figure 1: The confirmation of successful reception displayed in tuning indicator

[Image: dsstv/obr/digtrx_potvrzovani.png]

The reports are same as for the phone operation in the RS (readability and
strength) code. The V (View) value representing image quality of digital
transmission is losing its importance. Readability is measured on a scale of 1
to 5, so level 5 stands for for a perfect error-free transfer, level 4 is 4
still acceptable, with occasional failure segments and potentially it's needed
to increase the number of instances. Report the worst level 1 if can not
receive any digital data.

Contrary to popular SSTV operations when stations restrict only to the exchange
of images, the phone mode is much more used in case of DSSTV.

The choice of images is not limited to the usual $320240$ resolution,
but there can be used any resolution. The limiting factor is only time of
transmission, e.g. in the DIGTRX software the broadcast time is already known,
so you can play around with the compression level, resolution, or number of
colors and achieve a reasonable compromise.

Also, the transmitted data file format can be any. Listen on the band and you
will make sure that JPEG2000 is often used, but also animated GIFs, or text
files with ASCII art.
