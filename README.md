# Rowan University's Cybersecurity Club 2020 Discord CTF

## CTF Creator: [Tapan Soni](https://github.com/TapanSoni)

## Challenge 1 - Day 1: Monday

### Given

##### Synopsis

They say a picture is worth a thousand words. I want to say that this picture is worth about 10, 000 words. This is the iconic and legendary nasa space shuttle seen here Booking it to space. This Particular image is of the Space shuttle on its 27th mission. A couple of fun facts about the space shuttle:

1) over the course of its Tenure, the space shuttle has sent over 3 million pounds of cargo into space!
2) the Entire length of the space shuttle is 183 feet
3) columbia was the first space shuttle to be delivered to the kennedy space center in march of 1979
4) the Guiding computers for the space shuttle were made by ibm
5) the longest that the space shuttle has stayed in orbit during A single mission is 17.5 days during in november of 1996
6) the smallest crew to fly the space suttle was 2 - during the first few missions -- imagine the pressure on the New engines during the first test!
7) the space shuttle is designed to reach Orbits randing from about 185 kilometers to 643 kilometers high!

The space shuttle program has transformed the direction of space travel forever. It has transformed thousands of lives and given us a new direction to venture into when looking up at the STARS.

##### Files

|shuttle.png|
|-----------|
|![shuttle.png](Files/shuttle.png)|

### Solution

By looking at the synopsis you can see certain words capatilized. Words that are unnecessarily capatilized are:

01. Booking
02. Particular
03. Space
04. Tenure
05. Entire
06. Guiding
07. A
08. New
09. Orbits
10. STARS

When you look at the capatilized letters of the words - they spell ```BPSTEGANO``` and ```STARS```

[BPStegano](https://github.com/TapanSoni/BPStegano) is the image steganography tool written by Tapan Soni and his group for his Graduate Cryptography class during the Fall of 2019.

BPStegano uses AES-128 encryption a custom LSB random pixel algorithm hiding to hide raw strings and any type of file inside images.

Download and run BPStegano on the shuttle.png image. The password is ```STARS```.

BPStegano will decode the image and save the contents of the image into a ```HIDDEN_DATA``` folder.

Print out the ```Day1Code.txt``` file to see the code of Day 1.

|Output of BPStegano|
|-----------|
|![d1_bps.png](Files/d1_bps.png)|

|Contents of the HIDDEN_DATA folder|
|-----------|
|![d1code.png](Files/d1code.png)|

### Code

Day 1's code is: CDCTF{pushflagpackets}

## Challenge 2 - Day 2: Tuesday

## Challenge 3 - Day 3: Wednesday

## Challenge 4 - Day 4: Thursday

## Challenge 5 - Day 5: Friday
