# RadioRequests project

## Brief description
Automated radio audio-video stream that fetches and plays songs that followers are requesting.

## Project full description
The idea behind this is pretty simple. As we used to call by phone to radio to request a song for a playback 
(or - send SMS or text message by other means in more recent times), it would be very interactive and cool to
allow listeners of the radio drop a comment of special kind and that would call a parser, that will try to
search for a song, download it, and schedule for playback.

## Functions list
* Copyright: The platform for this should be NOCOPYRIGHT audio-video-stream solution similar to dlive.tv (otherwise it will be blocked)
* Search: RadioRequests should allow searching in several large databases for track files, then fetch & download them.
* Source Rankings: Ideally, sources should have "points" and users (who are requesting the track) should been able to vote for the track quality after track has started playing
* Request limit: RadioRequests should have a some sort of DB (textfile will be OK) with user nicknames that already ordered the tracks to prevent them from ordering again in the nearest TIMEOUT (30, 60 minutes etc.)
* Tracklength limit: check if track is longer than 7 minutes, decline adding to the playlist (exception: if user donated)
* Donator's bonus 1: You could order more tracks after you donate (in some way) to the channel
* Donator's bonus 2: You can obtain access to the track files that you requested and/or whole track database
* Donator's bonus 3: Allows to play tracks of length up to ...14... minutes
* Follower's bonuses: You could have +1 more track order per day if you're follower
* Track-ban list: Radio might need a blacklist that will block several tracks for requests due to quality, unsuitable style or moral policy
* Two playlists: current (including user's requests) and permanent (including only "normal" radio tracks)
* Popular track: if track is requested by some # of users (let's say, 3, 5 or 10), add it to permanent playback list rather than current
* Bot feedback: after playback is scheduled, a bot would reply to chat "Thank you @useranme_who_requested, your track "Artist - Track" was added to the playlist and it will be played after ...7... tracks from now on

The idea for this project appeared after I found a lot of people are requesting tracks on Music channels in DLive.tv service.

## Comment structure example
```
RR, please play "Artist - Songname" song.
```
This comment can be parser for "RR, please play" and then we take everything in quotes. After, we separate the Artist from trackname by searching for dash "-" and after this, we can use the data to search in some good sources for WAV, OGG, FLAC, MP3 or whatever we can find.

## Platform development options
As just a draft idea, we can spin a Linux server (on a desktop, laptop or actual server) with the following software:
* Comment parser: written in PHP or Javascript that updates comments on a regular basis in search for artist & track names
* When a new comment found, parsed and verified OK, parser calls a hook to "downloader"
* Downloader: same again PHP or JS program that: 1) checks if user is OK, 2) takes artist name and track title and searches in several databases (ideally in parallel), if track exists, downloads it to local folder and adds (its PATH) to scheduled list
* User list file: contains user names, statuses (normal user/follower/donator/banned user), number of requested tracks (valid request), number of found & added tracks, timestamp of last request of the track (used when he is re-requesting the track)
* Optionally - log file, that has time, user and track names
* Scheduled list is just a TEXT playlist (directory/file format) for cvlc, mpv, mplayer or any other CLI based player
* Additionally to above, server spins:
** the player itself (in "loop-shuffle" mode so when playlist comes to and end it re-shuffles it and starts over)
** virtual Xserver for OBS stream
** OBS (OpenBroadCast studio) combining some interactive stuff like output from player + user chat + donations info + webcam stream + projectM (music animation visualizer) and streaming resuling image to DLive or similar
** ProjectM for music animation

Optionally, radio could have also have a "normal" radio stream option (without a video stream)

This project would require developing of comment parser & files downloader, or finding someone's good software for this task.
Other components are MOSTLY ready to use as-is or with little settings.

## Sources for the tracks
What comes to my mind (please update this file if you know better or additional ones):
* Youtube-dl to download videos and convert them to audios (`youtube-dl "ytsearch1:metallica - nothing else"`) - this option will give HUGE database of tracks but of medium to medium-low quality OR we can even use source youtube videos
* Telegram bots that search for music and return files (this will usually provide better files than youtube, but the database will be smaller)
* Open track databases, something similar to jamendo (this DB is even smaller, but can provide highest quality files as well as these tracks can be legally played and broadcasted)

Please feel free to add your track source if you know some (as this project will probably start as a hobby project and there won't be any huge money invested in the start, please provide free-as-in-freedom or free-as-in-beer sources).

## Author
Mentioning author of the project idea - @sxiii would be really nice.

## License
Preferably the GPLv3 or similar.

## Links
* Website: N/A
* Github: N/A
