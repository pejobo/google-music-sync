GoogleMusicSync: 
==================================================
A simple Python script to sync your local MP3 library to Google Play Music.
Uses the excellent Google Music API script by Simon Weber and eyeD3 for MP3 tag reading.

To run it, you'll need the pre-reqs:

-  pip install gmusicapi
-  pip install eyeD3
-  apt-get install avconf (for match & scan)

(Tested against gmusicapi 3.1.0-dev and eyeD3 0.7.4)
  
Then download googlemusicsync.py (e.g. wget with raw file link)

And finally make it executable:

-  sudo chmod 0755 googlemusicsync.py

The script accepts parameters:
./googlemusicsync.py -p LOCAL_PATH -s -u username -l login

Where

-  p is the local path that you wish to scan
-  s sync the changes (if omitted no sync is performed)
-  f force-upload (do not check against titles already uploaded)
-  u username, e.g. foo@mail.com
-  l login-password (this is currently needed for getting the list of songs from google)


Last two params could also be read from the same file as gmusicfs (<userhome>/.gmusicfs).
For upload the OAuth functionality of gmusicapi is utilized.

Please note at the moment that this script is simply one way, any files that 
are on your local machine that are not on Google Play Music will be synced.

Also there is no matching on client side as performed, every song not found in the songlist at google
is uploaded to google! This will take its time, depending on your upload performance.
