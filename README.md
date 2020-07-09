# Rowan University's Cybersecurity Club 2020 Discord CTF

## CTF Creator: [Tapan Soni](https://github.com/TapanSoni)

## Table Of Contents
1. [Challenge 1 - Day 1: Monday](#challenge-1---day-1-monday)
2. [Challenge 2 - Day 2: Tuesday](#challenge-2---day-2-tuesday)
3. [Challenge 3 - Day 3: Wednesday](#challenge-3---day-3-wednesday)
4. [Challenge 4 - Day 4: Thursday](#challenge-4---day-4-thursday)
5. [Challenge 5 - Day 5: Friday](#challenge-5---day-5-friday)
6. [Conclusion](#conclusion)

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

[Back to the top](#rowan-universitys-cybersecurity-club-2020-discord-ctf)

## Challenge 2 - Day 2: Tuesday

### Initially given synopsis

I found this weird user when I was browsing reddit -> u/sdfjkloeifpoiwkef - They were posting a lot of pictures. I don't know if the pictures mean anything. I couldn't see anything out of the ordinary.

### Initially given files

None.

### Solution

When you search for ```u/sdfjkloeifpoiwkef``` on Reddit, you will see their profile. There are a bunch of images that are posted on the profile by the user. They are there to throw you off.

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
This is a picture of a cork bottle. The cork is usually used to cap off
wine bottles but in this case, they made bottles out of corks.




*What is this*??
43 44 43 54 46 7b 73 68 61 32 35 36 7d
```

The encoded phrase at the bottom is the flag. It is in hexadecimal and needs to be converted to its character equivalent.

I used this converter to convert hex numbers to ASCII characters - https://www.rapidtables.com/convert/number/hex-to-ascii.html


### Code

```Day 2's code: CDCTF{sha256}```

[Back to the top](#rowan-universitys-cybersecurity-club-2020-discord-ctf)

## Challenge 3 - Day 3: Wednesday

### Initially given synopsis

I've hidden today's code in the server somewhere. Look everywhere and at everything.

### Initially given files

None.

### Solution

In the ```general-ctf``` channel, when you scroll up a little bit, you will see a message by Tapan Soni saying ```Day 3 -> CDCTF{This is not the code - you need to find the code hidden throughout the server}```

This is the first clue. Well, a message, not really a clue.

|Fragment #| Code fragment| Location|
|-|-|-|
|1/4|c|In the ```general-sparx``` channel description under the ```SPARX``` category|
|2/4|h|In the ```project-managers``` channel description under the ```RFID``` category|
|3/4|r|In the ```announcements``` channel under the ```PUBLIC DOMAIN``` category. Look at the emoji reactions of the recent announcements|
|4/4|(|Set as Tapan Soni's status|

### Code

```Day 3's code: CDCTF{chr(}```

[Back to the top](#rowan-universitys-cybersecurity-club-2020-discord-ctf)

## Challenge 4 - Day 4: Thursday

### Initilly given synopsis

REMEMBER - THIS IS JUST PSEUDO CODE - YOU HAVE TO THINK ABOUT THE ACTUAL CODE.

```python
# Some pseudo code - might be helpful in solving today's challenge
# Written by Tapan Soni
# 6/25/2020

# I remember using the Scapy library to convert the Wireshark packet dump into an *****
# What does [-8:] mean? Some kind of reverse mapping shortcut or something?
# Notice the indentations - They might hint towards something
s = ""
a = []

for p in wiresharkPacketDump:
    # What kind of packet is p?
    # Should probably know my TCP/IP headers
    # What should I check for first in p - what comes first?

        # What should I check for second in p - maybe some kind of layer?

            # This part is easy - just plug in the codes from days 1-3 and you have the code
            # And make sure to code it correctly
            # Remember where a [DAY 1 CODE] appears! - Might help with the above pseudo code
            if [DAY 1 CODE] in p:
                s = bin([DAY 2 CODE](srcIP + dstIP + srcPort + dstPort + seqNum + data))[-8:]
                a.append([DAY 3 CODE](int(s, 2)))

    # This is an important part
    # I went on a rant about this part a while back in the #general channel of the Discord
    # It has something to do with a function in a library in Python
    # Should probably do something about it here

#################### END FOR LOOP ####################

for k in a:
    print(a, end = "")
```

### Initially given files

[Wireshark Packet Dump](Files/day4.pcapng)

### Solution

```python
# Rowan Cybersecurity Club Discord CTF - Day 4 Code
# Written by Tapan Soni
# THIS IS MY VERSION OF THE SOLUTION - YOUR SOLUTION MAY (PROBABLY WILL) DEFER
# 6/25/2020

# Import Scapy and hashlib
# Scapy for reading in the packets from the PCAP file and working with packet values
# Hashlib for the SHA256 hashing algorithm
from scapy.all import *
import hashlib

# Initialize the SHA256 hashing algorithm
# [DAY 2 CODE]
# sha256
h = hashlib.sha256()

# Read in the packets from the PCAP file
packets = rdpcap("day4.pcapng")

# a -> Array to hold the decoded letters in the final flag - character array
# s -> Holds the 8-bit binary string that will be turned into a character - string
a = []
s = ""

# srcIP -> Source IP address of the packet - string
# dstIP -> Destination IP address of the packet - string
# srcPort -> Source port number of the packet - int
# dstPort -> Destination port number of the packet - int
# seqNum -> Sequence number of the packet - int
# data -> Data of the packet - bytes
srcIP = ""
dstIP = ""
srcPort = 0
dstPort = 0
seqNum = 0
data = b""

# Check every packet in the packet array
for packet in packets:
    
    # Check if the packet is an IPv4 packet
    if IP in packet:
        
        # Check if a TCP layer exists
        # If the TCP layer exists - then TCP flags can be set
        if TCP in packet:

            # Check if the TCP PSH (push) flag is set (enabled)
            # [DAY 1 CODE]
            # if (pushflagpacket) in p -> Meaning if the push flag is set (enabled)
            if (packet[TCP].flags == 8):
                
                # Get the srcIP, dstIP, srcPort, dstPort, seqNum, and data
                srcIP = packet[IP].src
                dstIP = packet[IP].dst
                srcPort = packet[TCP].sport
                dstPort = packet[TCP].dport
                seqNum = packet[TCP].seq
                data = packet[Raw].load
                
                # Concatenate the data into one giant string - everything in bytes
                dataToHash = srcIP.encode() + dstIP.encode() + str(srcPort).encode() + \
                    str(dstPort).encode() + str(seqNum).encode() + data
                
                # Hash the data
                h.update(dataToHash)
                
                # Get the hexadecimal digest -> convert to a binary hash
                hexDigest = h.hexdigest()
                binDigest = bin(int(hexDigest, 16))[2:]
                
                # Get the last 8 bits (1 byte) of the binary hash
                last8Bits = binDigest[-8:]
                
                # Convert the 8 bits to a character and add it to the array to print later
                # letter = [DAY 3 CODE]int(last8Bits, 2)
                # letter = chr(int(last8Bits, 2))
                letter = chr(int(last8Bits, 2))
                a.append(letter)

    # Delete the hash object and create a new one for every iteration
    # BECAUSE -> the .update() function concatenates the input paramater 
    # to whatever the previous parameter was. For example -> If I call
    # h.update("Hello") 10 times, I'm going to get a different hash everytime.
    
    # Not really a problem if on both the server & client side it is done that
    # way, but for large messages, the buffer can blow up. NOT GOOD!
    # And it's bad practice - calling h.update("Hello") 9 times shouldn't give
    # me a different hash than the first time I called it.
    
    # To solve that problem -> Delete and create a new hashlib.sha256() object h.
    # This "bug" took me about 15 hours to debug and figure out what was going on
    # Didn't expect the update() function to work like this
    del h
    h = hashlib.sha256()

# Print out the array to see the final flag
# end = "" just keeps it all on one line - easier to read
print()
for k in a:
    print(k, end = "")

print()
```

The output of this Python program is the code for day 4.

### Code

```Day 4's code: cdctf[y917tnof]```

[Back to the top](#rowan-universitys-cybersecurity-club-2020-discord-ctf)

## Challenge 5 - Day 5: Friday

### Initially given synopsis

This might be helpful - https://tinyurl.com/ [DAY 4 CODE]

### Initially given files

None.

### Solution

When you go to the tinyurl link, it redirects you to a Google Form.

In the Google Form there is an image of Emperor Palpatine with a bunch of stuff on his face.

You're going to have make sure that your screen brightness is all the way up and you're not using a blue light filter.

In the bottom left of the image - in that dark spot to the right of the blue markings, there is a URL.

The URL is ```elvis.rowan.edu/~sonit9/```.

I tried my best to make it as visible as possible while keeping it hidden.

|Image in the Google Form|
|-|
|![palpatine.png](Files/palpatine.png)|

|Link location|
|-|
|![elvis_link_location.png](Files/elvis_link_location.png)|

|URL|
|-|
|![elvis_link.png](Files/elvis_link.png)|

When you go to the link ```elvis.rowan.edu/~sonit9``` you'll have to navigate through a series of html pages to get to progress.

There are 6 HTML pages to get through.

#### Right click is disabled on the HTML pages using simple Javascript. In cases where the user can disable Javascript using plugins like NoScript, I've taken measures to obfuscate the necessary HTML and Javascript code to prevent reverse-engineering. To the best of my abilities of course - I didn't have all year to make this.

#### index.html

The first one is a bunch of links telling the user to "Click me" or "Or me" etc.

You need to click on the correct link.

To go to the second HTML page - hover over each link and click on the link whos URL corresponds to ```https://tinyurl.com/ybtebyjb```. It's the 15th link.

|Link location for index.html|
|-|
|![indexhtml.png](Files/indexhtml.png)|

#### 2-pOjHrN5Jix.html

This is the second HTML page. It's designed to annoy the player and confuse them.

Just scroll all the way to the bottom of the page and in the center of the page on the bottom is a tiny link leading to the third HTML page.

Click on it to move on.

|Link location for 2-pOjHrN5Jix.html|
|-|
|![2html.png](Files/2html.png)|

#### 3-8MKRdsKyLb.html

This is the third HTML page. It contains many Lorem Ipsum paragraphs.

Scroll through and each of the red bold words is a link. Look for the one that says ```saggatis``` - about three quarters of the way down. It leads to the next page.

Again, these pages are designed to annoy you.

|Link location for 3-8MKRdsKyLb.html|
|-|
|![3html.png](Files/3html.png)|

#### 4-lTvgOncj6A.html

This is the fourth HTML page. It includes a game I stole from https://www.w3schools.com/graphics/game_intro.asp and modified it.

The goal of the game is to reach a certain score. The score is randomly choosen from a range of 1000 and 3500. The speed of the square is also randomly chosen.

Just play the game and you will automatically be taken to the next HTML page.

One trick (bug) is just keep smashing that jump button and the square will actually jump all the way off of the screen and go over all the bars. Keep doing that until you hit the random score.

|Passing 4-lTvgOncj6A.html|
|-|
|![4html.png](Files/4html.png)|

#### 5-0CKLGQydWA.html

This is the fifth HTML page. This one is cool.

You have to "guess" the correct RGB values of the color and reflect the values on the corresponding RGB buttons. 

The hint is "10".

Click the image 10 times to reveal the RGB values and then just press the RGB buttons that many times to correspond to the values shown. You will automatically be taken to the next page.

|5-0CKLGQydWA.html before|
|-|
|![5htmlbefore.png](Files/5htmlbefore.png)|

|5-0CKLGQydWA.html after|
|-|
|![5htmlafter.png](Files/5htmlafter.png)|

#### 6-dIoLExY9wl.html

This is the sixth and final HTML page. There is an awesome gif on this page and a whole bunch of white space below.

If you highlight that white space you'll see a Google Drive link.

The Google Drive link is ```https://drive.google.com/drive/folders/1ciLB9Ci4M4Y-d0IFD40e4IygjuP7-2XP?usp=sharing```.

|6-dIoLExY9wl.html link location|
|-|
|![6html.png](Files/6html.png)|

When you follow the Google Drive link, you'll see a Google Drive folder with 2 files in it - ```10000.zip``` and ```README.doc```

10000.zip is a zip file that has been zipped 10000 times. I did say in the README that I might have used different compressions (tar, bzip, gzip, etc.) but that was to mess with people. 

I only used zip file compressions 10000 times.

The easiest way is to write a simple bash script that decompresses the file for you:

```bash
#!/bin/bash

# Written by Tapan Soni
# 6/25/2020
# THIS IS MY VERSION OF THE SOLUTION - YOUR SOLUTION MAY (PROBABLY WILL) DEFER

# Takes in 2 params
# 1) File to unzip
# 2) # of times to unzip

# Make sure to make the bash file executable by using chmod

# Sample usage -> ./ucth.sh 100.zip 100

for ((i=$2;i>0;i--))
do
	unzip "$((i)).zip"
done
```

Just for fun but this is the bash script I used to compress the ```flag.txt``` file 10000 times:

```bash
#!/bin/bash

# Written by Tapan Soni
# 6/25/2020
# THIS IS MY VERSION OF THE SOLUTION - YOUR SOLUTION MAY (PROBABLY WILL) DEFER

# Takes in 2 params
# 1) file to zip,
# 2) # of times to zip

# Make sure to make the bash file executable by using chmod

# Sample usage -> ./cth.sh flag.txt 100

# Initial compression
zip 1.zip $1

for ((i=1;i<$2;i++))
do
	zip "$((i+1)).zip" "$i.zip"
done
```

And that's it. Once you decompress the file 10000 times (which will take a couple of minutes), you will see a flag.txt file which contains the final flag.

### Code

```Day 5's code: CDCTF{trianglebagels}```

[Back to the top](#rowan-universitys-cybersecurity-club-2020-discord-ctf)

## Conclusion

```
Day 1's code: CDCTF{pushflagpackets}
Day 2's code: CDCTF{sha256}
Day 3's code: CDCTF{chr(}
Day 4's code: cdctf[y917tnof]
Day 5's code: CDCTF{trianglebagels}
```

I had a lot of fun creating the challenges for this CTF, especialy the HTML pages.
Day 4's challenge was inspired by my thesis on Moving Target Network Steganography. It is a very simple version of my proof of concept simulation. I had to take a lot into account when creating the code for that challenge because I didn't want to make it so difficult where no one could program it. But I didn't want to give away all the secrets either -- I wanted the students to think about why and how the program works the way it does. That update() function for the hashlib library was a pain to figure out - I never expected the function to work that way.

The HTML pages were really fun to work on - I wanted to come up with little games almost where each page was a game that the students had to pass to get to the final prize. 10000.zip was actually taken from a previous CTF challenge I made up which was inspired by the Over The Wire CTF. The CTF challenge I previously made was 12 compressions using bzip, tar, gzip, and zip. That challenge was also hosted on a VM with a GUI so students were able to just right click and decompress the file. This time, I wanted to make that impossible even with a GUI. So, I increased the compressions to 10K so the students would have to automate it somehow. The bash script is so small and easy to write - takes about 30 mins to write and test and then just run it until the flag.txt file is extracted. Easy.

I also really liked the idea of a cumulative CTF where parts from previous challenges (days) would combine together to form a bigger challenge (day 4). This is in stark contrast to CTF competitions where each challenge is independent of the other challenges. I also hate it when CTF competitions ask you to download multiple files for every challenge. I tried to keep that to a minimum.

But all in all, I really had fun making this CTF and I think this was something that was needed for the club and the students. The whole COVID-19 situtation has made 2020 miserable and I think people wanted something fun to work on with others.

I hope you had fun playing this CTF.

[Back to the top](#rowan-universitys-cybersecurity-club-2020-discord-ctf)
