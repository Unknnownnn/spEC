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

![image](https://github.com/user-attachments/assets/2258b78a-1c5d-4d4b-9727-af0098087dc8)

2) The .7z file is password protected.
3) Using a steganography decoder doesn’t reveal anything from the
image.
4) Using a spectrograph decoder on the.wav reveals this:
We can open the audio file in a program such as Audacity.

![image](https://github.com/user-attachments/assets/f50778f9-ed5d-47c0-9be1-0db1713ae393)

When using Audacity, use the spectrogram option as shown below.


![image](https://github.com/user-attachments/assets/d17e2ef1-03d5-43d6-8801-ade76850b57b)


5) The message: “FORMAT: YYYY:MM:DD HH:MM:SS” is revealed from
the file.
6) This may mean that the creation date of the image is the password of
the .7z file.
7) Using exiftool on the image reveals:


![image](https://github.com/user-attachments/assets/a354b90b-8904-47e2-8c48-6cfbed9c26ce)


8) Trying the File Modification Date/Time as the password for the .7z file
unlocks the file.
9) This reveals a .png file.
10) Running this file through a steganography decoder reveals some
binary text.

![image](https://github.com/user-attachments/assets/3570ed11-dddc-411f-9c62-8900ff63f75b)


11) Converting this binary text to human readable form gives a randomly
generated looking string. Since it ends with ‘=’, we can assume it may
be a base64 encrypted text.

13) Decoding the base64 reveals our flag

![image](https://github.com/user-attachments/assets/9d0b8979-50e3-4ff4-86a8-05c9dcb8d89e)


## $${\color{red}Flag:}$$
## $${\color{lightgreen}hacker(kopafjb8734hoc0qd)}$$
