# MOD. useful code snippets

1. ffmpeg

## ffmpeg

To stitch videos together horizontally losslessly using the audio from the left-hand video:

`$ ffmpeg -i left.mp4 -i right.mp4 -filter_complex "hstack,format=yuv420p" -c:v libx264 -crf 18 output.mp4`

To rotate a video clockwise:

`$ ffmpeg -i in.mov -vf "transpose=2" out.mov -c:a copy`

