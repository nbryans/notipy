<img src=https://github.com/nbryans/notipy/blob/master/Logo/notipyLogo.png width=300px align=left>
<!---# notipy-->
A module for quickly sending email alerts and statuses from python programs


This script was created to notify me when a job was completed (and sometimes include an exit status and relevant results)


Notipy is compatible with both python2 and python3

<br />

# Instructions

### On First Run
*(Optional)* If building from source, run `python setup.py sdist` and move *.zip to desired location

Extract Notipy-1.0 from the zip
```
cd Notipy-1.0
python setup.py install
```
In a `python` session
```
import notipymail.notipy as notipy
notipy.updateSendDetails("yourEmail@server.com", "yourPassword", "smtp.yourServer.com", "587")
```
This will create file  `senddetails.dat` containing the following contents:
```
email:nbauto791@gmail.com
password:<redacted>
server:smtp.gmail.com
port:587
```
Optionally, you can create this file manually.

### Sending Emails with Notipy:
```
import notipymail.notipy as notipy
notipy.sendMail("to@address.com", "This is a message")
```

# Notes
Use `notipy.sendMailAsync(..)` to send mail in the background asynchronously.

Send status are logged in `notipy.log`. The log file can be changed in the `#Constants` section of `notipy.py`

To query the log through python, use `notipy.queryLog(5)` where `5` specifies the number of log entries (most recent to least) to retrieve. This operation may be slow for large logs.

In `sendMail` and `sendMailAsync`, there is an optional third parameter where you can specify a subject. *i.e.* `notipy.sendMail("to@address.com", "This is the message", "Custom Subject")`. The default subject is "Notipy Automail"

<!---
Logo created using modified images originally distributed by Pixabay.com
https://pixabay.com/en/cartoon-snake-yellow-1293047/
https://pixabay.com/en/email-letter-contact-message-mail-309678/
-->
