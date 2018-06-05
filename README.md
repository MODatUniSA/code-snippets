# MOD. useful code snippets

1. [ffmpeg](#ffmpeg)
2. [Windows](#windows)
3. [Raspberry Pi](#pi)

## ffmpeg

To stitch videos together horizontally losslessly using the audio from the left-hand video:

`$ ffmpeg -i left.mp4 -i right.mp4 -filter_complex "hstack,format=yuv420p" -c:v libx264 -crf 18 output.mp4`

To rotate a video clockwise:

`$ ffmpeg -i in.mov -vf "transpose=2" out.mov -c:a copy`

## Windows

To add an application or script to always start when Windows has finished starting up and logged in:

* Press `Win+E` to open a file explorer.
* Paste this into the address bar: `%APPDATA%\Microsoft\Windows\Start Menu\Programs\Startup`
* Create a shortcut to the application you’d like to start and add it to the Startup folder.

## Pi

**WiFi USB**

To compile & install usb -> wifi dongles for the Raspberry Pi for different kernels, use this script:
[http://downloads.fars-robotics.net/wifi-drivers/install-wifi](http://downloads.fars-robotics.net/wifi-drivers/install-wifi)

Run it as sudo: `$ sudo ./install-wifi.sh`

You may need to chmod it to make it executable: `$ chmod +x install-wifi.sh`

If it fails to self update, try commenting out those lines (line ~399) and re-run.

The script will need to be run every time you update the kernel version via `$ sudo apt update`.

**Setting the date/time**

If your pi won't get the time from an ntp server, you can run this one liner to set it from your favourite website:

`$ sudo date -s "$(wget -qSO- --max-redirect=0 google.com 2>&1 | grep Date: | cut -d' ' -f5-8)Z"`

