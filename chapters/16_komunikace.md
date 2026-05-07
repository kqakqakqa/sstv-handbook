## Digital communication basics

Before I describe the transmission systems we look at some important
concepts of data communication. What interests us most is the speed
which is possible to transmit information – we distinguish between
the speed of transmission and modulation:

$} – express the number of changes $a$ of
carrier signal per second. It is measured in unit *Baud (Bd)*
or *Symbols per second (S/s)*. Symbol rate does not say anything
about how much information transmitted on signal carrier.

```


```

$}
– indicates the amount of information
transferred per second. It is expressed in *bits per second (bps)*. Bit rate says nothing about how fast the signal carrier
changes.

```


```

where $m$ is the number of modulation states.

We know from previous chapters that an important feature of
communication channel is a limited bandwidth $B$. Relation between
symbol rate and bandwidth shows *Nyquist rate:*

```


```

Ideally, the symbol rate should be twice the bandwidth. Substituting the
formula for the symbol rate, we get:

```


```

Let's look on the relationship between symbol rate and bit rate,
because these two term are often use interchangeably. E.g. packet
radio on VHF has bit rate 1200\,bps and the used modulation is AFSK (Audio
Frequency-Shift Keying). Frequencies carrying information are two –
2200\,Hz for mark (log. 1) and 1200\,Hz for space (log. 0). We know
$v_p = 1200$\,bps, $m=2$, so symbol rate is equal to bit rate:

```

1\,200\,\hbox{Bd}.

```

A packet radio is based on ITU-T V.23 specification for telephone
modems, where bandwidth is limited to about 4\,kHz. Modern dial-up
modems, but have a much higher bit rates, up to 56\,kbps and the
bandwidth remains 4\,kHz. How is that possible?

It's possible through the used advanced modulation, which has more modulation
states $m$ then two. For example, modems based on V.32 specification can use bit
rate up to 9,600\,bps. There is used *QAM (Quadrature Amplitude Modulation)*, which in case of QAM-16 has 16 states per one modulation symbol.
The symbol rate in this case is:

```

2\,400\,\hbox{Bd}.

```

One could think that it's possible to reach any speed because of
improved modulation and more states. Unfortunately not, because
there are stark physical limits. Maximal channel capacity $C$ (bit
rate) in bps is given by *Shannon's law*, which depends on
bandwidth $B$ (Hz) and channel parameters signal/noise ratio $S/N$ (dB):

```


```

As we can see the maximum bit rate speed is not affected by the
used technology, but the bandwidth $B$ and signal/noise ratio (SNR),
which cannot be changed. SNR is given in decibels (dB) and describes
the ratio of a signal power to a noise power of a processed bandwidth.
