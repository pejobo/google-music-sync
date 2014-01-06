GoogleMusicSync: 
==================================================
A simple Python script to sync your local MP3 library to Google Play Music.
Uses the excellent Google Music API script by Simon Weber and eyeD3 for MP3 tag reading.

To run it, you'll need the pre-reqs:

-  pip install gmusicapi
-  pip install eyeD3

(Tested against gmusicapi 3.1.0-dev and eyeD3 0.7.4)
  
Then download googlemusicsync.py (e.g. wget with raw file link)

And finally make it executable:

-  sudo chmod 0755 googlemusicsync.py

The script accepts parameters:
./googlemusicsync.py -p LOCAL_PATH -s 'true/false' -u username -l login

Where
- p is the local path that you wish to scan
- s should the changes be synced, or just report the differences
- u username, e.g. foo@mail.com
- l password (this is currently needed for getting the list of songs from google)

Last to params could also be read from the same file as gmusicfs (<userhome>/.gmusicfs).
For upload the OAuth functionality of gmusicapi is utilized.

(TODO: Mode for upload without matching)

Please note at the moment that this script is simply one way, any files that 
are on your local machine that are not on Google Play Music will be synced.

Also there is no matching on client side as performed, every song not found in the songlist at google
is uploaded to google! This will take its time, depending on your upload performance.
