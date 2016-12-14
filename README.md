<img src=https://github.com/nbryans/notipy/blob/master/Logo/notipyLogo.png width=300px align=left>
<!---# notipy-->
A module for quickly sending email alerts and statuses from python programs


This script was created to notify (hence, notipy :) me when a job was completed (and include an exit status and results, if desired)


Notipy is compatible with both python2 and python3

<br />
# Instructions

### On First Run
```
import notipy
notipy.updateSendDetails("yourEmail@server.com", "yourPassword", "smtp.yourServer.com", "587")
```
This will create file  `sendDetails1.txt` containing the following contents:
```
email:nbauto791@gmail.com
password:<redacted>
server:smtp.gmail.com
port:587
```
Optionally, you can `cp sendDetails.txt sendDetails1.txt` and fill out manually.

###Sending Emails with Notipy:
```
import notipylib.notipy as notipy
notipy.sendMail("to@address.com", "This is a message")
```

# Notes
`sendDetails1.txt` is included in `.gitignore` to keep your email details off GitHub.

Use `notipy.sendMailAsync(..)` to send mail in the background asynchronously.

Send statuses are logged in `notipy.log`. The file to write the log to to can be changed in the `#Constants` section of `notipy.py`

To query the log through python, use `notipy.queryLog(5)` where the argument specifies the number of most recent log entries to retrieve. This operation may be slow for large logs.

In `sendMail` and `sendMailAsync`, there is an optional third parameter where you can specify a subject. *i.e.* `notipy.sendMail("to@address.com", "This is the message", "Custom Subject")`. The default subject is "Notipy Automail"

<!---
Logo created using modified images originally distributed by Pixabay.com
https://pixabay.com/en/cartoon-snake-yellow-1293047/
https://pixabay.com/en/email-letter-contact-message-mail-309678/
-->
