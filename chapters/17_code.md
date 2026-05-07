## Error detection and correction

The error detection codes are used as a check of error-free transmission. The
idea is based on some extra data (redundancy) added to a message. The
redundancy is generated from some input data on a transmission side *(FEC – Forward Error Correction)* and on a reception side it is possible to
check if the data was transferred without error. An used code may have also
ability for an error correction, so data affected during transmission can be
repaired on reception side without retransmission. There are several error
detection codes, e.g. even parity described in .

The codes have several parameters. First is the bit length of information $k$,
which we want to encode and the length of codeword $n$. The difference $r=n-k$
is the length of redundancy data. Redundancy does not transfer any information,
but it is only used for error detection and possibly correction. The ratio of
the number of information symbols to the number of all symbols

```


```

expresses *information ratio*. In practice, we require that redundancy is
minimized.

The ability of the code, how many errors should be detected or corrected is
given by *Hamming distance*. It is determined as the number of different
symbols of two different codewords. The most important is minimal Hamming
distance $d$ of all arbitrary codewords. E.g. Hamming distance of 0101000 and 0111001 is $d=2$. The errors during transmission
cause replacement of one symbol to another and Hamming distance indicates how
many replacements may occur to change the codeword to another valid codeword.
Is is advantageous to have a Hamming distance of codewords larger as possible.
So if you want code that reveals just one error bit, the minimum distance must
be $d=2$. Block code with minimal distance $d$ *detects* all $t$-multiple
errors for $td$ there should
be created a new valid word, so the error cannot be detected. The code can
correct errors for larger $d$, if for error word is found a valid codeword with
smaller Hamming distance between error and valid word. The block code *corrects* all $t$-multiple error when

```


```

These findings can be demonstrated on a simple case of 2-bit code secured
with even parity. Two-bit code can have a total of 4 words of information,
and a redundant bit will be added, so that the number of log. ones in
the codeword will be even.

,offset=1mm+.5pt] Information word Parity Codeword 00 0 000 01 1 011 10 1 101 11 0 110 }

The resulting code words have 3 bits and there are $2^3=8$ different bit words
(code words are bold):

,offset=1mm+.5pt] 000 001 010 011 100 101110 111 }

The minimum distance $d$ of our parity code is equal to 2, so the code is able
to detect just one error. When word 011 is sent and 010 is received we know
that there is an error. If there are two errors and 011 changes to 000, then
there is a word that belongs to a set of codewords and error isn't detected.

In the following sections are described some commonly used error-detection
and correction codes.

### Cyclic redundancy check

The *CRC* is commonly used code. The *systematic cyclic code*,
adds a fixed-length check *(checksum)* value to message. The checksum
is used for error detection.

CRC calculation is performed on block or section of data is stored
in memory, the $k$-bit sequence is represented as a polynomial $G(x)$. This is polynomial is divided by generating polynomial $P(x)$ in arithmetic modulo 2.
The result is polynomial $Q(x)$ and the remainder after dividing $R(x)$.
The remainder $R(x)$ is added to input data and transmitted in message.

On the reception side the division with $P(x)$ is computed again and new
remainder $R'(x)$ is compared with transferred remainder $R(x)$. If both values
are the same transfer went without error, if not at least one bit was
transferred incorrectly.

### Hamming code

In the area of data communications (e.g. TV teletext) is sometimes used *Hamming code*, which can detect up to two errors and in the case of a one
error it is able to determine at what point of codeword error occurred and it
can fix received bits.

Basically, it uses for its purposes even parity. While the parity bits are in
the final codeword positioned at the serial number is equal to the square of 2
(1., 2., 4., 8.,). Under the control bit position is then selected
certain sequence of information words, which is used to determine the value of
control bit.

### Reed-Solomon code

Hamming code works well in environments where errors occur randomly and their
incidence is low (e.g. in computer memory, which can detect a erroneous bit to
100 million). But even if that failure causes a greater number of adjacent bits
are corrupted *(burst error)*, the Hamming code is useless. In the field of
radio transmission, where the signal is often affected by atmospheric
disturbances, fade outs and interference, then errors occur in clusters.
This means that close to the incorrect symbol are other symbols incorrect too.
For burst error correction is applied *Reed-Solomon code (RS)*.

RS codes are the most widely used codes for detection and error correction.
They are characterized by having the largest possible minimum distance, and
compared to the previous code will not correct the individual bits, but all
symbols. RS code have found application in the number of areas – is used by
NASA for space communications, protects data on CD-ROMs and DVDs and is
also used for terrestrial transmission of HDTV or in the data modems for the
cable television networks.

Like the CRC the RS code is systematic. For its generation are used the
algebraic calculations of Galois field.

Parameters of the RS($n$,\,$k$) are defined as follows:

- $k$ – number of s-bit symbols in data block,

- $n$ – number of bits in codeword.

RS($n$,\,$k$) is able to correct $$ errors in $k$ information
symbols. Often used code is RS(255,\,223), it uses 223 8-bit symbols for
creation of 255 symbols of codeword. There is 32 symbols dedicated for error
correction. RS(255,\,223) is able to repair up to 16 erroneous 8-bit symbols.
