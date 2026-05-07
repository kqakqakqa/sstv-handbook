## Data compression

The image with resolution 320$$240 with a color depth of 16 million
colors ($256^3$) takes 230,400\,Bytes (320$$240$$3) without
compression. This file would be transmitted fortyone minutes by RDFT with speed
92 Bytes per second! This time is really scary in comparison with analog SSTV.
It is really necessary to reduce the file size and reduce the time required for
transmission.

The *data compression* is widely used in such cases, where
the data capacity of communication channels or storage media
and memory is limited.

The compression is the process where the physical data block size is
reduces to a certain level. Input data is compressed using the
compression algorithm and then stored on media or transmitted via
communication channel. The data are decompressed in its original form,
when a media is read or a signal received.

One of the important parameters of compression algorithms is *lossy*. While the programs or text must by stored in perfect form,
but in case of sound, images or animations we can settle with the
omission of certain details, then we're talking about lossy
compression method.

When Clause E. Shannon was engaged in applied mathematic of communication
theory during 1940s, he started with definition of informational value of
message content. The message which is repeated often is less informative than
the message, which occurs sporadically. So, the often repeated message is more
likely than the unique. The probability in mathematic is expressed by real
numbers in range from 0 (for a completely unlikely events) to 1 (for the
phenomena that occur surely). Shannon defined the amount of information
$I(x_i)$ for the message $x_i$ with the probability of occurrence $p(x_i)$ as
follows:

```


```

The graph of negative logarithm see on –
if the message content is less likely that its information value is
higher.

Figure 1: The relation between information content $I(x_i)$ and its probability $p(x_i)$.

[Image: dsstv/obr/entropie-1.pdf]

*Information entropy* $H$ is defined as *average rate of information value $I(x_i)$*:

```

\mathrm{[bit]}

```

We show the entropy meaning in example. We need to transfer messages
$a_1, a_2, a_8$ and probability of their occurrence is same:
$p_i=1/8=0{,}125$. The entropy of source is

```


```

The observed entropy determines how the message content can be encoded for data
transmission. The length of message in bits is greater then or equal to the
entropy, without loss of information. So the message can be encoded as word of
3bit length: 000, 001, 010, Maximum entropy is reached when the
probability of occurrence of each message is the same.

But the messages have often different probabilities in many cases. In this
example we need to transfer messages $a_1, a_2, a_7$. Their
probabilities are
$p(a_1)=0.235$,
$p(a_2)=0.206$,
$p(a_3)=0.176$,
$p(a_4)=0.147$,
$p(a_5)=0.118$,
$p(a_6)=0.059$,
$p(a_7)=0.029$,
$p(a_8)=0.029$.
Entropy of source is

```

\eqalign{ H & = -\displaystyle\sum_{i=1}^7 p(a_i)\log_2{p(a_i)} = \cr ~ & = - \big(0.235\cdot{}(-2.09)+ 0.206\cdot{}(-2.28)+ 0.176\cdot{}(-2.50)+ 0.147\cdot{}(-2.76)+ \cr & 0.118\cdot{}(-3.08)+ 0.059\cdot{}(-4.08)+ 0.029\cdot{}(-5.08)+ 0.029\cdot{}(-5.08) \big)\,\mathrm{bits} \cr H & \approx -2.712\,\mathrm{bits} \cr }

```

We see, that the entropy of source is lower and because data bits are not
divisible, it is necessary to encode the message again to the words of length
3. But suspect that such an encoding is no longer optimal. There is the idea to
encode frequently occurring words as the message of the shorter length. This
idea was well-counseled by David A. Huffman, the Shannon's student.

### Huffman coding

We can show an example of Huffman coding construction. The
message we are going to encode if following:

`THE SHELLS SHE SELLS ARE SEASHELLS`

This message contains 8 symbols (S, E, L, " ", H, A, T, R). The message can
be expressed with code words of 3bit length. Its whole length is $3 34 =
102$\,bits.

For Huffman coding we need to determine number of each symbol
and their probabilities.

{ S E L H A T R 8$$ 7$$ 6$$ 5$$ 4$$ 2$$ 1$$ 1$$ 0.235 0.206 0.176 0.147 0.118 0.059 0.029 0.029 }

There is used *binary tree*, it is a data structure often used
in programming. The symbols are sorted by their frequency and then
each symbol represents a tree leaf, and its weight is given by
symbol occurrence. In first step join two leafs with the lowest
weight, in our case { T} and { R} and create a node. The node
weight is sum of weights { T} and { R}. In the next step join
leafs or nodes with the lowest weight and proceed as long as there
is only one node (the root of binary tree).

Now, go from the root toward leafs by the edges and each edge label by 0 or 1,
if the edge goes up or down (in tree terminology to left or right subtree). The
constructed tree with labeled edges see on . To find
the code of each symbol pass all ways from the root towards the leaves. The
path going along the edges of 0, 0 ends in { S}, the path going along 1, 1,
1, 0 ends in { A}.

Figure 2: The results of Huffman encoding.

[Image: dsstv/obr/huffman-en.pdf]

We see, that more frequent symbols with high probability of occurrence
have shorter code than sporadic symbols. Our message after encoding:

The message length was reduced from 102 to 93\,bits. For decoding the binary
tree can be used again. We will start in the root and
go along edges 1, 1, 1, 1, 0 until we arrive to lead, here symbol { T}, then
we return to the root and go along 1, 1, 0 and we arrive to leaf { H}. By
this way we continue until the whole message is decoded. Because Huffman coding
is has unique *prefixes* for each code, and this prefixes is not start of
another codeword the decoding can not do mistake.

Other compression algorithms using dictionary methods. These methods are based
on fact that some words in the input file occur more frequently. Repeating
words are stored in the dictionary. These words are replaced with their
corresponding code words in output file. Among the representatives of this type
of compression belongs *LZW (Lempel-Ziv-Welch)* as used in the ZIP
compression or GIF or a variant of the TIFF formats.

### Lossless data compression

Many applications needs for their requirements that data aren't impaired if
they are compressed. E.g. for binary programs and data. Lossless
compression has its justification in the field of computer graphics and image
storage too. Lossy compression fits on "nature images" and photographs, but
when it is used on a computer-generated graphics such as diagrams and charts,
the image distortion is more noticeable on sharp edges and color gradients,
even at low compress ratio (see .).

Many compression algorithms were developed for lossless compression. A simple
algorithm is for example *Run Length Encoding (RLE)*. This algorithm stores
repeated bytes as their value and number. E.g. `AB AB AB CD EF EF EF EF EF`
is stored as `03 AB 01 CD 05 EF`, so instead of 9 bytes should be only 6
stored.

Other types of algorithms are based on statistical methods. Before or during
the compression process the algorithm determines the relative representations
of elements of the file, and those repeated frequently are expressed as a
short code word. Such algorithm is the Huffman coding described above. Also,
Morse code is one of those codes, frequently recurring characters such as E (.)
A (.–), I (..) have assigned shorter codes and the less frequent, such as H
(....), J (.–\,–\,–), F (..–.) longer codes.

#### Portable Network Graphics

The PNG is appropriate graphics format with lossless compression. PNG was
created to replace the outdated GIF format. PNG is not limited to a palette of
256 colors like GIF and allows to set a continuous level of transparency
*(alpha-channel)* compared to GIF, which has the option to choose only two
levels (yes or no transparency). If you want to save the lossless image just
choose PNG.

The algorithm used in PNG is called *deflate*. This method is enhanced in
some ways, the image lines are firstly processed by filter, which tries to find
a similar neighborhood for each pixel. After processing there is a large number
of data with zero value or a value close to zero (for same or similar values),
so compression algorithms finds in data areas with same value so it can shrinks
the length of the resulting file.

### Lossy compression

The principle of lossy compression takes advantage of the processing equipment,
in the case of the human eye it is unable to process certain information, so
it actually would be an extra piece of information omitted.

A widely used method for lossy image compression format is *JPEG (Joint Photographic Experts Group)*. The JPEG is the standard established by the ISO
and ITU, released in 1992 (later upgraded in 1997). A successor is upgraded
format *JPEG2000*. It was developed by JPEG committee since 1995, was
released in December 2000 and further revised in 2003, but it is not so
widespread as its predecessor.

#### JPEG compression

JPEG usually does not use RGB color coding but use YCrCb, see
different sensitivity. The storage of YCrCb colors, mostly in the ration
4\,:\,2\,:\,0 reduces size of file, but itself is not enough. The image
is further transformed, see schema in .

In first step the image is divided on square block of $8 8$ pixels and
these 64 points is transformed from spatial domain ($x$, $y$) to frequency
($i$, $j$) by discrete cosine transform. Just for completeness, as follows:

```

[Image: dsstv/obr/jpeg_demonstrace-en.pdf]

```
