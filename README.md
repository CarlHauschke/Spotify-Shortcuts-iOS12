## Introduction
As most of you probably know workflow already lets you create custom voice commands for Siri in the iOS 12 Developer/Public Beta. 

I was working on a few workflows which allow for some rudimentary control of Spotify. It allows you to play the playlist you played last right from Siri e.g. you could ask Siri "Play Spotify" and the workflow will play whatever you last played in your Spotify account. The other workflow I came up with is to just show the last last playlist/song/album/radio was last played in Spotify. 

All this relies on the Spotify Web API as you can't work with the Spotify app directly. This means that there will most likely be times where the workflow behaves unexpectedly or plays a track/playlist that was played several minutes ago and the client has not yet synced back to the Spotify backend.
An internet connection is required for the Workflows to work.


## Setup
To set up any of the Workflows you first need to get a so called refresh token which needs to be derived from an authorization token. The refresh token is used to generate new access tokens every time you use one of the Workflows. 

Why not use the authorization token or access token directly? Easy, both of them will expire within one hour after they have been issued by Spotify. The refresh token won't expire and can be used to ask Spotify for new access tokens.

To get the refresh token you need to install [this workflow](https://s.carl.al/2No3hX6) and run it.

It will ask you to authenticate with Spotify and then generates a refresh token which it copies to your devices clipboard. When you install any of the Workflows that actually interact with Spotify the Workflow app will ask you for the code while installing the Workflow so generate the refresh token in advance.

GETREFRESHTOKENVIDEO

With the refresh token in the clipboard you can now download the Workflows listed below to control Spotify. During the installation they will ask you for the refresh token and in some cases for some additional information.

INSTALLVIDEO

To set up a Siri shortcut you have to use the Workflow at least once from within the Workflow app for Siri to recognize the Workflow and present you with the Shortcut setup inside of the Settings app.

After launching the Workflow manually and verifying that it works go into the Settings app > Siri & Search > More Shortcuts and find the name of the Workflow you want to add a Siri shortcut for. Tap the + button and hit the record button on the next screen an tell Siri what trigger you want to use to start the Workflow.

SIRISETUPVIDEO


## Play the playlist/track/album which was last played from your Spotify account
When this Workflow is triggered it will play your most recently played playlist, track or album.

Spotify Radios and the Daily Mixes will only play the track that was last played within the Daily Mix/Radio. The Spotify WebAPI should report the URL of the Daily Mix/Radio but doesn't.

Please note that there is a workaround for playing a playlist in place which is a result of Spotify having no way of allowing the automatic playback upon receiving a playlist URI. The only thing that Spotify will autoplay when receiving a URI is a Song. This means that the workflow will first get the name of your most recently played track (inside the playlist that was played) and will send this URI to Spotify which Spotify will then automatically play. The Workflow will then transfer the playback over to the playlist in the background. Especially on slow internet connections this transfer sometimes does not work. If the transfer does not work you can either ask Siri to show you your last playlist (requires another Workflow) and start it manually or look for the playlist yourself and play it. If someone finds a solution to this I'm more than happy to implement it.

VIDEOGOESHERE

Get it [here](https://s.carl.al/2K2cT7Q)!


## Show your most recently played object in Spotify (doesn't autoplay it)
When this Workflow is triggered it will open your most recently played object in Spotify. It will show your most recently played track, playlist or album.

Spotify Radios and the Daily Mixes will only redirect you to the track that was last played within the Daily Mix/Radio. The Spotify WebAPI should report the URL of the Daily Mix/Radio but doesn't. 

VIDEOGOESHERE

Get it [here](https://s.carl.al/2K4BJ6P)!


## More Workflows are coming...
If you have any ideas for other ways Siri could be used to control Spotify let me know and I'll do my best to bake that idea into a Workflow. Keep in mind though that it's not possible to let Siri hand over a variable to Workflow e.g. asking Siri to "Play Bella Ciao" and have Siri hand over "Bella Ciao" to the workflow to search for that track does not work.


### When you want to say goodbye to the convenience of controlling Spotify with Siri
When the time comes and you don't feel like you want to use the Workflows anymore or don't feel comfortable with the safety of your Spotify data you can revoke the access for the Workflows right from your [Spotify account page](https://s.carl.al/2L4vXYj) under the Apps tab where it will be listed as "Spotify Workflow". After that you won't be able to use the Workflows anymore and would have to generate a new refresh token.