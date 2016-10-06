# notipy
A tool for sending email alerts from python code.


This script was created to notify (hence, notipy :) me when a job was completed (and possible send exit status/results)


Compatible with both python2 and python3


# Instructions
Create file  `sendDetails1.txt` containing the following contents (see template sendDetails.txt as an example)
```
email:nbauto791@gmail.com
password:<redacted>
server:smtp.gmail.com
port:587
```
To run:
```
import notipy
notipy.sendMail("to@address.com", "This is a message")
```
