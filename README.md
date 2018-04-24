# MOD. useful code snippets

1. [ffmpeg](#ffmpeg)
2. [Windows](#windows)

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