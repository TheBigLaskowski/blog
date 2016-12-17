---
layout: post
title:  "How to Record Your Microphone and Speakers in Ubuntu 16.04"
date:   2016-12-16 04:30:11 -0400
categories: linux
author: Joe Laskowski
---

![record microphone and speakers in ubuntu](/img/2016/12/record-mic-speaker-ubuntu.svg){: .center-image }

On any given day I receive 20 to 50 phone calls and I utilize Google Hangouts so I can work hands free. I used to use a program called Audacity to record important phone calls. This required me to enable monitor mode in the Pulse Audio settings, as well as entering a few commands into the terminal to enable a loop back mode. This enabled a stereo mix and it was required so my microphone and speakers could work concurrently. This was not an ideal setup, while speaking you can hear yourself talking and it made it difficult to hold a normal conversation.

I recently upgraded my distro of Xubuntu to LTS version 16.04 and was hoping to find a new solution to record from the microphone and speakers simultaneously. A Google search for “Linux + stereo mix” eventually led me to discover a cross platform open source program called [Open Broadcaster Software Studio](https://obsproject.com/).

> Free and open source software for video recording and live streaming. Download and start streaming quickly and easily on Windows, Mac or Linux.

OBS Studio can do so much more than record Hangouts and Skype calls, however my initial interest was peaked when I discovered that OBS already has a stereo mix that works right out of the box. Unlike the Audacity method, OBS requires no manual configuration in PulseAudio, or enabling a loop back mode via the command line.

### [OBS Ubuntu Installation](https://github.com/jp9000/obs-studio/wiki/Install-Instructions#linux)

* FFmpeg is required. If you do not have the FFmpeg installed (if you're not sure, then you probably don't have it), you can get it with the following commands:

**For Ubuntu 14.04 LTS**, FFmpeg is not officially included so you will need a specific PPA:

```
sudo add-apt-repository ppa:kirillshkrogalev/ffmpeg-next
sudo apt-get update && sudo apt-get install ffmpeg
```

**For Ubuntu 15.04 and following versions**, FFmpeg is officially included:

```
sudo apt-get install ffmpeg
```

* Then you can install OBS with the following commands:

```
sudo add-apt-repository ppa:obsproject/obs-studio
sudo apt-get update && sudo apt-get install obs-studio
```

Once you have OBS Studio installed all you have to do is add your audio output capture and the audio input capture in the source panel. These settings will use the default microphone and speaker selections in the PulseAudio panel.


![obs-source-panel-settings](/img/2016/12/obs-source-panel.png){: .center-image }


That's it! Start recording and you are good to go. This works perfect with Skype, Hangouts and any other program that you require recording two way audio. I have mine set to minimize to the system tray where I can simply click on the indicator icon and start and stop recording when needed. Enjoy and if you have any questions leave a comment below the video on YouTube.


{% include youtube.html youtube_id="N7old9XFokU" %}
