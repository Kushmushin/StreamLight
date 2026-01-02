Created by Kushmushin.
This is mainly to be used if you have an older computer that can't run OBS.
I can't run OBS, but I wanted to stream from my old computer.
So this is optimized for an old CPU.
No frills. No gimmicks.

These all are tested with my Debian system. I imagine it should work on any linux system.
This is setup for one webcam, one microphone, and your desktop.
Also I use a bluescreen. With a little editing, this will work without one.
Run through the terminal using function calls, (user $ twitch_pip)
Streaming for Twitch, Kick, and Youtube.
Desktop recording with PIP.
Multiple Youtube Shorts recording options.
Security in mind - No keys revealed in the terminal/script.

All I ask is this...
Follow me on Youtube, Twitch, and Kick. All under Kushmushin.
All I want in return is a like, a subscribe, and a follow. 
I'm just a gamer, bro! Help me get a new computer setup!


///////////SETUP\\\\\\\\\\\\\

#Add the following to your .bashrc file in your $HOME dir. The spot for it is near the bottom.

if [ -f ~/.bash_streaming ]; then
    . ~/.bash_streaming
fi

Keep your keys and RTMP urls in a separate .env file. That should look like this:

export YOUTUBE_KEY="SECRETKEY"
...
...
export YOUTUBE_RTMP="RTMP_URL"
...
...

Just do it for each key. Three keys, three urls, etc.
The .env should be saved in a separate dir, probably your .config directory.
Want to lock it to your user? In your terminal run:
'chmod 600 ~/.config/stream_keys.env'

NOTES:
  This is basically bare bones OSB of my own making.
  I'm trying to keep quality up, yet sacrifices are to be made.
  If you don't have figlet, or lolcat, just apt install them. Or erase where you see them.
  Set your resolutions. My monitor is 1600x900, so I work with that. Math is involved.
  Image input is your bluescreen image. Keep it to exact size of your webcam, and a jpeg to conserve cpu.
  If you're not using a bluescreen, just ask ChatGPT to take it out. Or figure it out.
  'pactl list short sources' will help you find your audio names! I'm using Pulse audio.
  apt install pavucontrol, if you want to boost your mic.
  adelay is set to 2000 each. For audio sync, adjust 1000-2000ish. Run tests. CPU dependant.
  I have five inputs 0-4. Just be aware of the flow.
  Any other tweaks are up to you.
  This is a work in progress.
