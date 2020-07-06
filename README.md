# Rowan University's Cybersecurity Club 2020 Discord CTF

## CTF Creator: [Tapan Soni](https://github.com/TapanSoni)

## Challenge 1 - Day 1: Monday

### Initially given synopsis

They say a picture is worth a thousand words. I want to say that this picture is worth about 10, 000 words. This is the iconic and legendary nasa space shuttle seen here Booking it to space. This Particular image is of the Space shuttle on its 27th mission. A couple of fun facts about the space shuttle:

1) over the course of its Tenure, the space shuttle has sent over 3 million pounds of cargo into space!
2) the Entire length of the space shuttle is 183 feet
3) columbia was the first space shuttle to be delivered to the kennedy space center in march of 1979
4) the Guiding computers for the space shuttle were made by ibm
5) the longest that the space shuttle has stayed in orbit during A single mission is 17.5 days during in november of 1996
6) the smallest crew to fly the space suttle was 2 - during the first few missions -- imagine the pressure on the New engines during the first test!
7) the space shuttle is designed to reach Orbits randing from about 185 kilometers to 643 kilometers high!

The space shuttle program has transformed the direction of space travel forever. It has transformed thousands of lives and given us a new direction to venture into when looking up at the STARS.

### Initially given files

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

Download and run BPStegano on the shuttle.png image. The password is ```STARS ```.

BPStegano will decode the image and save the contents of the image into a ```HIDDEN_DATA``` folder.

Print out the ```Day1Code.txt``` file to see the code of Day 1.

|Output of BPStegano|
|-----------|
|![d1_bps.png](Files/d1_bps.png)|

|Contents of the HIDDEN_DATA folder|
|-----------|
|![d1code.png](Files/d1code.png)|

### Code

```Day 1's code: CDCTF{pushflagpackets}```

## Challenge 2 -> Day 2: Tuesday

### Initially given synopsis

I found this weird user when I was browsing reddit -> u/sdfjkloeifpoiwkef - They were posting a lot of pictures. I don't know if the pictures mean anything. I couldn't see anything out of the ordinary.

### Initially given files


### Solution

When you search for u/sdfjkloeifpoiwkef on Reddit, you will see their profile. There are a bunch of images that are posted on the profile by the user. They are there to throw you off.

Look at the user description box under the profile image and you will see a link there. The link is ```https://gofile.io/d/MgWhQ5``` -- it is a GoFile link to an image.

|Location of the GoFile link|
|-----------|
|![](Files/d2_link_loc.png)|

|Image at the GoFile link|
|-----------|
|![corkbottle.jpg](Files/corkbottle.jpg)|

Now, if you try and perform steganalysis on the image, nothing is going to come of it.
The code of the day is hidden in the EXIF data of the image. 

Well, I guess rummaging through EXIF data is a form of steganalysis.

Anyways (on Windows), right click on the image > Properties > Details > Comments

Open the comments section.

This is the content of the comments section:

```
This is a picture of a cork bottle. The cork is usually used to cap off wine bottles but in this case, they made bottles out of corks.




*What is this*??
43 44 43 54 46 7b 73 68 61 32 35 36 7d
```

The encoded phrase at the bottom is the flag. It is in hexadecimal and needs to be converted to its character equivalent.

I used this converter to convert hex numbers to ASCII characters - https://www.rapidtables.com/convert/number/hex-to-ascii.html


### Code

```Day 2's code: CDCTF{sha256}```

## Challenge 3 - Day 3: Wednesday

## Challenge 4 - Day 4: Thursday

## Challenge 5 - Day 5: Friday
