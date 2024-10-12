# <p align="center"> spEC </p>
## <p align="center"> Reverse Engineering </p>

## $${\color{red}Overview:}$$
We are given a .zip file called “spEC.zip”. We need get the answer in
hacker{XXXX}.

## $${\color{red}Theory:}$$
Audio can hide hidden messages through a spectrogram. The waveforms of
audio files can be converted to spectrograms to display hidden images or text.
We can decode these hidden messages using programs such as Audacity or
specific webpages. Similarly, Image files may also hide such data using
spectrographs. Also text may be encrypted using multiple algorithms to hide
data.


## $${\color{red}Solution:}$$
1) A .zip file is provided to the player with 3 files within it: 1 .wav audio
file, 1 poster.png & divergence.7z.
2) The .7z file is password protected.
3) Using a steganography decoder doesn’t reveal anything from the
image.
4) Using a spectrograph decoder on the.wav reveals this:
We can open the audio file in a program such as Audacity.
When using Audacity, use the spectrogram option as shown below.
5) The message: “FORMAT: YYYY:MM:DD HH:MM:SS” is revealed from
the file.
6) This may mean that the creation date of the image is the password of
the .7z file.
7) Using exiftool on the image reveals:
8) Trying the File Modification Date/Time as the password for the .7z file
unlocks the file.
9) This reveals a .png file.
10) Running this file through a steganography decoder reveals some
binary text.
11) Converting this binary text to human readable form gives a randomly
generated looking string. Since it ends with ‘=’, we can assume it may
be a base64 encrypted text.
12) Decoding the base64 reveals our flag


## $${\color{red}Flag:}$$
## $${\color{lightgreen}hacker(kopafjb8734hoc0qd)}$$
