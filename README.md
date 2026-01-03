This script was written by me, Kushmushin!
This is mainly to be used if you have an older computer that can't run OBS.
I can't run OBS, but I wanted to stream from my old computer.
So this is optimized for an old CPU running a light linux distro.
My personal recommendation is Debian, running Plasma KDE. Light distro, or lighter.
This is a setup for one webcam, one microphone, and a bluescreen.
In a future update I'll add a function for no bluescreen.
Very no frills, but super cost effective.

What you get:
Streaming for Twitch, Kick, and Youtube.
Desktop recording with your cam in the corner.
Multiple Youtube Shorts recording options. (desktop, desktop w/wo sound, 40/60 cam/desktop)
Security in mind - No keys revealed in the terminal/script. (Tucked away in their own file.)

The process:
Open your terminal.
Run 'campipe', view your webcam and make adjustments.
Enter 'pip (service)' (service is either twitch, kick, or youtube)
The terminal displays the platform in groovy text, and you're streaming. Easy!
Ctrl C to quit.

All I ask is this...
Follow me on Youtube, Twitch, and Kick. All under Kushmushin.
All I want in return is a like, a subscribe, and a follow. 
I'm just a poor gamer, my Dude! Help a brother get a new computer setup!


#----------SETUP----------



#---Step One: Setup a file for stream keys

In '$HOME/.config' directory, create a stream_keys.env
In that file drop the following into it.

#Keep your keys here.
export YOUTUBE_KEY="youryoutubekey"
export TWITCH_KEY="yourtwitchkey"
export KICK_KEY="yourkickkey"

export TWITCH_RTMP="twitchrtmpurl"
export YOUTUBE_RTMP="youtubertmpurl"
export KICK_RTMP="kickrtmpurl"
#

To add user security, enter:
'chmod 600 ~/.config/stream_keys.env'



#---Step Two: Add the file to your bashrc

Add the following to your .bashrc file in your $HOME dir. The spot for it is near the bottom.

#My bash_streaming is hidden with the period. Add or remove where applicable. I keep all my bash files hidden.
if [ -f ~/.bash_streaming ]; then
    . ~/.bash_streaming
fi
#



#---Step Three: Add the StreamLight bash file

Create a .bash_streaming file in your $HOME beside your .bashrc
Copy and paste from github. Boom, your done.
Now you just have to customize the file a bit.

I suggest these steps:
1. Adjust for your cam resolution, and desktop resolution.
	Choose at which corner you want your cam, etc.
	I recommend using the 'desktop_pip' function to record your setup and do testing.
	But if you have no followers, just try streaming directly to the service for testing.
	Its up to you.
2. If using a bluescreen, select a bg image. Image should be exactly to size. But whatever.
3. Find your microphone ans system audio sources.
	I'm using pulse, so I enter
	'pactl list short sources' to find my source names. Use the names.
	I also use pavucontrol, its pulse audio control, to boost my microphone on the input, not the recording.
4. 'apt install figlet && lolcat' just for flair. Or erase them where you see them.
5. Adjust the adelay. Anywhere from 0000-2000, depending on your cpu. If your cpu is old, its probably not going to be perfect.
	Start at 2000, and if your lips move before you hear yourself, lower the number.



#---FINAL NOTES:
  This is basically bare bones OSB of my own making.
  I'm trying to keep quality up, yet sacrifices are made for professional purposes.
  I have five inputs 0-4. Just be aware of the flow.
  I use mpg123 for bg music. Super low cpu usage.
  And I try to use ffplay for any mp4 that need playing in the bg. Keep that cpu low.
  This is a work in progress.
