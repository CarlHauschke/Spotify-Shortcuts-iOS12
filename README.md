## Introduction
I was working on a few Shortcuts which allow control of Spotify with the help of Siri snd Shortcuts. It allows you to play the playlist you played last right from Siri e.g. you could ask Siri "Play Spotify" and the Shortcut will play whatever you last played in your Spotify account or to add the currently playing track to your Favorites. 

All this relies on the Spotify Web API as you can't work with the Spotify app directly. This means that there will most likely be times where the Shortcuts behave unexpectedly or play a track/playlist that was played several minutes ago and the client has not yet synced back to the Spotify backend.
An internet connection is required for the Shortcuts to work.


## Installation
For the installation install [this setup Shortcut](https://s.carl.al/2Oxczkq). 

The installation Shortcut will guide through the authentication with Spotify and the installation of the other Shortcuts.
Every time you execute the installation Shortcut it lets you choose one Shortcut to set up.

INSTALLSHORTCUTVIDEO


## Setting up the Siri command
To set up a Siri shortcut you have to tap on the settings icon within the Shortcut and tap the "Add to Siri" button. Choose a phrase to trigger the shortcut and that's it.

SIRISETUPVIDEO


## Play the playlist/track/album which was last played from your Spotify account
When this Shortcut is triggered it will play your most recently played playlist, track or album.

Spotify Radios and the Daily Mixes will only play the track that was last played within the Daily Mix/Radio. The Spotify WebAPI should report the URL of the Daily Mix/Radio but doesn't.

Please note that there is a workaround for playing a playlist in place which is a result of Spotify having no way of allowing the automatic playback upon receiving a playlist URI. The only thing that Spotify will autoplay when receiving a URI is a Song. This means that the Shortcut will first get the name of your most recently played track (inside the playlist that was played) and will send this URI to Spotify which Spotify will then automatically play. The Shortcut will then transfer the playback over to the playlist in the background. Especially on slow internet connections this transfer sometimes does not work. If the transfer does not work you can either ask Siri to show you your last playlist (requires another Shortcut) and start it manually or look for the playlist yourself and play it. If someone finds a solution to this I'm more than happy to implement it.

VIDEOGOESHERE


## Show your most recently played object in Spotify (doesn't autoplay it)
When this Shortcut is triggered it will open your most recently played object in Spotify. It will show your most recently played track, playlist or album.

Spotify Radios and the Daily Mixes will only redirect you to the track that was last played within the Daily Mix/Radio. The Spotify WebAPI should report the URL of the Daily Mix/Radio but doesn't. 

VIDEOGOESHERE


## Add currently playing song to favorites
This Shortcut adds the song that spotify currently plays to your saved songs

VIDEOGOESHERE

## Skip track
This Shortcut yust skips to the next song, nothing else.

VIDEOGOESHERE

## More Shortcuts are coming...
If you have any ideas for other ways Siri could be used to control Spotify let me know and I'll do my best to bake that idea into a Shortcut. Keep in mind though that it's not possible to let Siri hand over a variable to Shortcut e.g. asking Siri to "Play Bella Ciao" and have Siri hand over "Bella Ciao" to the Shortcut to search for that track does not work.


### When you want to say goodbye to the convenience of controlling Spotify with Siri
When the time comes and you don't feel like you want to use the Shortcuts anymore or don't feel comfortable with the safety of your Spotify data you can revoke the access for the Shortcuts right from your [Spotify account page](https://s.carl.al/2L4vXYj) under the Apps tab where it will be listed as "Spotify Shortcut". After that you won't be able to use the Shortcuts anymore and would have to generate a new refresh token.