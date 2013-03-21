OMXPlayer
=========

OMXPlayer is a commandline OMX player for the Raspberry Pi. It was developed as
a testbed for the XBMC Raspberry PI implementation and is quite handy to use
standalone. 

This fork was forked from Pasky's fork which enables seamless looping.  It fixes
an error in which the first time a file played it had no sound and would not loop.
It is a hack fix where after the file opens the program calls seek(30) which fixes
the issue...no idea why.

Also adds --volume as a command line option where you can set the volume like so:
"omxplayer --volume 2700" where 2700 is 27.00Db  This feature was added to so that
 the volume of the track audio would be greater than that of the audio pop that
occurs when one stream closes and another opens.

Downloading OMXPlayer
---------------------

    git clone git://github.com/huceke/omxplayer.git

Compiling OMXPlayer
-------------------

GCC version 4.7 is required.

### Cross Compiling

You need the content of your sdcard somewhere mounted or copied. There might be
development headers to install on the running Pi system for the crosscompiling.

Edit Makefile.include and change the settings according your locations.

If you need help setting up a cross-compiler there is a great tutorial posted [here](http://www.cnx-software.com/2013/01/26/raspberry-pi-now-has-experimental-support-for-vp6-vp8-mjpeg-and-ogg-theora-video-codecs/).
### Compiling on the Pi

You can also compile it on the PI the native way ;)

Running OMXPlayer
-----------------

    make ffmpeg
    make
    make dist

Installing OMXPlayer
--------------------

Copy over `omxplayer-dist/*` to the Pi `/`. You may want to specify a valid font
path inside the `omxplayer` shell script.

Using OMXPlayer
---------------

    Usage: omxplayer [OPTIONS] [FILE]
    Options :
             -h / --help                    print this help
             -n / --aidx  index             audio stream index    : e.g. 1
             -o / --adev  device            audio out device      : e.g. hdmi/local
             -i / --info                    dump stream format and exit
             -s / --stats                   pts and buffer stats
             -p / --passthrough             audio passthrough
             -d / --deinterlace             deinterlacing
             -w / --hw                      hw audio decoding
             -3 / --3d                      switch tv into 3d mode
             -y / --hdmiclocksync           adjust display refresh rate to match video
             -t / --sid index               show subtitle with index
             -r / --refresh                 adjust framerate/resolution to video
                  --boost-on-downmix        boost volume when downmixing
                  --subtitles path          external subtitles in UTF-8 srt format
                  --font path               subtitle font
                                            (default: /usr/share/fonts/truetype/freefont/FreeSans.ttf)
                  --font-size size          font size as thousandths of screen height
                                            (default: 55)
                  --align left/center       subtitle alignment (default: left)
                  --lines n                 number of lines to accommodate in the subtitle buffer
                                            (default: 3)

For example:

    ./omxplayer -p -o hdmi test.mkv

Key Bindings
------------

While playing you can use the following keys to control omxplayer:

    z			Show Info
    1			Increase Speed
    2			Decrease Speed
    j			Previous Audio stream
    k			Next Audio stream
    i			Previous Chapter
    o			Next Chapter
    n			Previous Subtitle stream
    m			Next Subtitle stream
    s			Toggle subtitles
    d			Subtitle delay -250 ms
    f			Subtitle delay +250 ms
    q			Exit OMXPlayer
    Space or p	Pause/Resume
    -			Decrease Volume
    +			Increase Volume
    Left Arrow	Seek -30
    Right Arrow	Seek +30
    Down Arrow	Seek -600
    Up Arrow	Seek +600
