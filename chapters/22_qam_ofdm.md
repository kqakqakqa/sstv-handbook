*Quadrature amplitude modulation (QAM)* uses amplitude and
phase modulation together. HamDRM for each subcarrier (OFDM
cells) can use several modulation schemes, which differ
in number of modulation states – QAM-4, QAM-16 and QAM-64.

The number of modulation states QAM-$m$ is divided into $$
states for phase keying and $$ amplitude levels. Thanks to
multistate modulation it is not required so huge bandwidth, on the
other hand, a growing number of states of modulation makes the signal
less resistant to interference.

Figure 1: The QAM modulator.

[Image: dsstv/obr/qam_modulator.pdf]

An modulation state is created from combination of amplitude and
phase, which can define a bit word of length $l$. For QAM-4 is
the word length $l = _2 m = _2 4 = 2$, for QAM-16 is $l=4$
and for QAM-64 it is 6. The modulation changes between these states:

```


```

E.g. for QAM-16 levels are $-3, -1, 1, 3$.

The signal, which can be presented like

```


```

has 16 combinations of amplitudes $A_k$ and phases $_k$.

The block diagram of QAM modulator see in
data sequence $N = \{$0, 13, 5, 2, 10, 7, 6, 5, 1, 15$}$. The result
is . The information words with 4bit length
are divided on two parts in mapping circuit and first 2bit combination
is coded in *pulse amplitude modulation (PAM)* into one of four
levels. The way how to code input bit quaternion $\{i_0, i_1, q_0, q_1}$ is defined by *constellation diagram*,
=00$ and this corresponds to $I=3, Q=3$, the next value 13, in binary
1101 corresponds $i_0i_1 = 11$ output $I=-3$ and for $q_0q_1 =01$
output $Q=-1$, etc.

The results of PAM are pulses with given amplitudes and they are
filtered with low-pass filter for the bandwidth reduction and for
in phase path $I$ and similarly for quadrature path $Q$. The $I$ and
$Q$ are input signals for modulators with carrier frequency $f$. This
way there is a phase of 90$^$ between them. Output signal is
made by joining of both paths together:

```


```

Figure 2: The constellation diagram for QAM-16 with bit order $\{i_0, i_1, q_0, q_1\

[Image: dsstv/obr/qam-16.pdf]

Figure 3: The example of QAM-16 modulation for input data sequence.

[Image: dsstv/obr/qam_example/qam_input.pdf]

### Orthogonal frequency-division multiplexing — OFDM

OFDM is a representative of the modulation scheme with multiple
carriers *MCM (Multicarrier Modulation)*. Thanks to its properties
the OFDM found application in many modern technologies, i.e. ADSL,
WiFi (IEEE 802.11a/g) networks, WiMAX and standards for digital
broadcast and terrestrial digital television DVB-T, etc.

OFDM has very good spectral performance and it is resistant to
pulse interference, because transfered information is dispersed in
wide frequency spectrum, so interference disturb only few nearby
symbols. It's also resistant to inter-symbol interference, fade outs
caused by multipath spreading and has low sensitivity to errors
in time synchronization.

Figure 4: The frequency spectrum of orthogonal carrier waves.

[Image: dsstv/obr/ofdm-en.pdf]

The OFDM generates a huge number of subcarrier waves and in case of
HamDRM there are for best performance *only* 57 subcarriers. Many
other applications like digital video broadcast or wideband data
communication uses hundreds or thousands of subcarriers! These
subcarriers have very small distances, even those, that the overlap
the range of others. An example of OFDM spectrum is
in , as spectrum of each subcarrier is considered
the spectrum of rectangular signal, which is expressed by $(x)/x$
function.

The subcarriers has exact distances, so maximal level of spectrum
of each subcarrier is null in maximal levels of other subcarriers,
so they are mutually *orthogonal*.

#### OFDM transfer

The modulator block diagram is in . Input
data stream comes to serial-parallel converter and it is cyclically
distributed to a larger number of parallel components. The parallel
component transmitted simultaneously creates a complete OFDM symbol.
Components are also modulated to the orthogonal system of $N$
subcarriers, the frequencies are distributed to ensure their
orthogonality. Subcarrier waves in our case use modulation QAM-4,
QAM-16 or QAM-64, but for some other applications there are used
multiphase BPSK or QPSK.

A signal processor provides modulation of huge number of subcarriers,
in our case it is software, which implements algorithms for inverse
discrete Fourier transform (DFT$^{-1}$). Because DFT algorithm has
big computing complexity there is used its faster variant *FFT (Fast Fourier Transform)*. The inverse FFT (FFT$^{-1}$) transform
input data from frequency domain to time domain. The process on a receiver
side vice-versa use direct FFT to obtain individual subcarriers.

Two data stream are outputs of FFT$^{-1}$, which are converted with
digital/analog converters on two analog signals. Then these signals are
modulated to main carrier and there is a phase of 90$^$ between
them. The { Re} signal presents amplitude component and { Im}
signal phase component. Both joined together creates transmitted OFDM
signal.

Figure 5: The OFDM modulator use fast Fourier transform (FFT$^{-1

[Image: dsstv/obr/ofdm_modulator.pdf]

Everything on reception side goes in opposite way. The received signal
is amplified and converted to lower frequency. Then signals { Re}
and { Im} go through low-pass filters to analog/digital converters
and data from them is processed by DSP with direct FFT and divided
into individual subcarriers. The output data are compiled in
parallel-serial converter.
