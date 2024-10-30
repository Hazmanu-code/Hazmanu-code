# shows artist info for a URN or URL

from spotipy.oauth2 import SpotifyClientCredentials
import spotipy
import sys
import pprint
import webbrowser
import pyautogui
from time import sleep 

client_id = "335065d95aef40bf9fc65bccb1f0abc2"
client_secret = "0c48e48c00804aadba0e59359f79315a"
author = 'Nirvana'
song = "smell like teen spirit"
sp = spotipy.Spotify(client_credentials_manager=SpotifyClientCredentials(client_id, client_secret))
result = sp.search(author)

for i in range(0, len(result["tracks"]["items"])):
 name_song = result["tracks"]["items"][i]['name']
 if song == name_song:
    webbrowser.open(result["tracks"]["items"][i]['uri'])
    sleep(5)
    pyautogui.press("enter")
    
