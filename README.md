# Cool way to edit metadata without the use of exiftool

This dummy repo collects few commands to remove or edit metadata from multiple sources


Change whole file title:
```
ffmpeg -i input.mkv -map 0:v -map 0:a -map 0:s -metadata title='whatever' -c copy output0.mkv
```

Change video stream title:
```
ffmpeg -i input.mkv -metadata:s:v:0 title="HEVC Video" -map 0:v -map 0:a -map 0:s -c copy output.mkv
```

I think `:s:v:0` some of the comments stands for:

:v = Video stream :0 = Use first video stream


Credits, of course stackoverflow:

- [source 1](https://stackoverflow.com/questions/11474532/how-to-change-metadata-with-ffmpeg-avconv-without-creating-a-new-file)
- [source 2](https://stackoverflow.com/questions/26666879/ffmpeg-video-metadata-change?rq=1)
