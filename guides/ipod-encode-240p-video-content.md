# Encoding 240p video content for your iPod Classic / iPod Video / iPod Nano 3G-5G
*Date: 03 April 2025, last edited: 10 April 2025*

# Introduction
I am obsessed about writing this guide since months, but just couldn't find a way to accomplish this task in a satisfying way even just for me. And since I don't want to mislead anyone, I preferred to wait until I could find a definitive workflow to share and to apply also to myself.

There's also multiple guides out there but I couldn't find any that could meet all these conditions:
- I want to use maintained tools, so using the old version of Handbrake is not good. Using an old version of Handbrake is going to be even more painful each years as video formats continue to evolve (with AV1, HDR standards, etc). Also the old version of Handbrake is not Apple Silicon native.
- The sound must be good stereo on the iPod
- I want to use the h.264 format with all the parameters that the iPod support, not the MPEG-4 format because h.264 compresses much better
- I want produced video files to play great with all iPods (Videos & Classics)
- I want small & optimized files, without noticeable artifacts to never need to encode them ever again
- I don't want to rely on iTunes for this task because it's single threaded thus very slow. Also, iTunes requires mp4 containers as input which is another layer of annoyance.
- The settings should encode fairly fast, I don't want to do two-pass encoding non senses.
- I want something very simple to mass convert as fast as possible, and something that handle all special cases like HDR tone mapping etc to be able even to convert very modern content for the iPod.

# Showcase
*Warning: Convert only content you own !*
![Alt text](<ipod-encode-240p-video-content/Showcase 1.jpeg> "Showcase 1")

![Alt text](<ipod-encode-240p-video-content/Showcase 2.jpeg> "Showcase 2")

![Alt text](<ipod-encode-240p-video-content/Showcase 3.jpeg> "Showcase 3")

# MacOS guide
Looks like you are on Mac. You're lucky, it's easier for you !

1) Download and save my Handbrake profile for later steps: [ipod-encode-240p-video-content/Apple 240p30 (Olsro) (MacOS).json](<ipod-encode-240p-video-content/Apple 240p30 (Olsro) (MacOS).json>)

2) Just download the latest available version of Handbrake and copy it into your Applications folder: https://handbrake.fr/downloads.php then run it !

You can now scroll down to the ```Handbrake guide part (common part)``` then do all the steps within there.

*If you need to, a video guide equivalent is available from here:* https://youtu.be/kW1fsHI1wuw

# Windows guide
*If you need to, a video guide equivalent is available from here:* https://youtu.be/zVoweo5Vxxw

1) Download and save my Handbrake profile for later steps: [ipod-encode-240p-video-content/Apple 240p30 (Olsro) (Windows).json](<ipod-encode-240p-video-content/Apple 240p30 (Olsro) (Windows).json>)
2) Download and install the last version https://handbrake.fr/downloads.php , install it but don't run it yet. Don't download the arm64 version even if your computer is arm64: download the **x64 64 bit (Intel or AMD CPU's)** version.
3) https://github.com/FT129/Handbrake-and-FFmpeg-with-fdk-aac/releases get the latest ```hb_x_x_x.zip``` from there. This will mod your Handbrake to support the fdk-AAC encoder which will be able to encode properly the audio tracks of the video files, it's very important.
4) Unpack that ```hb_x_x_x.zip```  (x_x_x must correspond to the version of Handbrake that you've downloaded during step 1). Extract ```hb.dll``` and copy/replace the existing ```hb.dll``` that is located in your installed Handbrake folder.
5) You can now scroll down to the ```Handbrake guide part (common part)``` then do all the steps within there.

# Handbrake guide part (common part for both operating systems)
1) Import my preset and select it. Use the *Windows* preset if you are on Windows/Linux, or the *MacOS* preset if you are on MacOS.
2) Import your medias into the handbrake window
3) For each media you've selected, before adding them into the waiting line:
- Audio: Change the audio track to select the one that you want to use, that match the language that you want to use. Don't try to add another audio track, it will not work, because iPods can use only one audio track at once.
- Subtitles: Change "Foreign audio scan" to "None" if you don't want any subtitle. If you want to use a subtitle track, select it, and subtitles will be automatically burn by handbrake into the video stream of the converted file.
4) Add the file to the waiting line. Now you can start convert. To add more files, repeat from step 3.
5) Import your files into the TV app or into iTunes, then tag them manually according to your desires. Don't forget to select the correct type (TV Show, Movie, or Music clip).
6) Ready to sync and play !

# FAQ
## Why even use an iPod to play video content ?
- When battery modded, any iPod can play videos for a very long time
- The iPod screen is pretty bright and 240p content can render surprisingly good, especially 16:9 and native 4:3 content
- Using that optimized guide, you can put entire shows and many movies with very minimal disk footprint. But if you put the same files on your phone, they will look very bad because the phone will need to strech a lot the content. But on the iPod, the same 240p content will be satisfying to look at.

## Why not convert to 480p ? It's better quality and the iPod can support it !
The issue is that 480p content on an iPod provides an improvement only if you connect your iPod to a modern TV. Whereas on the 240p screen, it's actually looking worse because of the poor downscale that the iPod is doing in real time: better let Handbrake takes the best decisions from the source file to downscale to the iPod screen !

Also 240p files requires 2x less disk space.

## Can I stretch the content by modifying Handbrake settings ?
Stretching the content will break completely its aspect ratio, it's not worth it and you don't want to do this if you are searching for the best possible quality.

### But my movies have big black bars !!!! It's too annoying
Avoid converting 2.39:1 content; focus on 4:3 and 16:9 content that will fill all or most of the screen. Some aspect ratios just don't scale well to 4:3 unfortunately especially on a very small 240p 4:3 surface.

Sometimes the same content can exist in different aspect ratios across different materials. For example, the Super Mario Bros movie exists in 16:9 but only in the official DVD. So in this case you may want to get the better source that will downscale better to the iPod screen, and sometimes the best source iPod-friendly can be the good old DVD.

## Subtitles are not very convenient to read on my iPod, what can I do ?
Prefer dubbed content and burn only forced subtitles to reduce as much as possible the amount of reading on the iPod to appreciate the visuals.

## Why do I need to mod Handbrake on Windows ?
The Windows/Linux version of Handbrake includes by default only an open source AAC audio encoder, which encoder the iPod dislikes heavily. The non-open source fdk-AAC encoder is far better, almost just as good as the Apple encoder, and will give you an excellent experience at 160kbps CBR.

## I don't care about storage and want really maximum quality
You will get very little improvements by pushing harder than me the quality sliders. I am very close to the max supported by the technical specs of the product. For example, Apple recommend to never exceeds AAC at 160kbps (CBR). If you decide to push the sliders more, be prepared to encounter issues, and to create uncompatible files with some iPods (for example working files on iPod Classics but losing compatibility with the older iPod Videos).
Also keep the encoding speed of h264 at "medium", as "slow" and other different params are changing heavily the encoding logic which can also create issues.

## Why not use Handbrake 1.3 which contains the official Apple 240p preset ?
This version is obsolete and unsupported, which means it's going to have more and more issues with modern video input files. Also new versions encodes faster, or even way faster on Apple silicon macs.

## What can I do with my purchased iTunes Store movies ?
Downloaded movies/series from the iTunes Store will be encrypted with non-easily-removable anti-copy protections ; these protections also affects your freedom to downscale and reconvert the content freely to save disk space. 

An animation movie of 1h47 downloaded from the iTunes Store at 480p was a fat MPEG-4 1.66GB file. Most of the animation movies of same duration that you will convert with the parameters that I provide from my guide will produce a very optimized h.264 movie of just around 300mb only with very good quality. This drastic disk space reduction is also very good to save the battery of your iPod because the RAM buffer will be able to store way more duration of your content on playback thus reducing the need to power up the disk storage so often.

## I get sound/image artifacts on the destination file, what can I do ?
Double check that these artifacts and/or sound issues are not also here in the source file. The converted file will be a downscaled representation of your source file, it will never be any better. A lossy video compression algorithm is like a lossy audio compression algorithm: more your source have data and resolution, more the encoder will be able to understand all the details of your content to produce the best downscaled result that is possible. You can build remuxs (make 1:1 copies) from your DVDs and Blurays by using the https://www.makemkv.com/ program to generate perfect quality .mkv files from the content that you own.

# Support my work
Writing software guides and investigations takes as much time & energy as selling modded iPods and going hardware mods. If this work is valuable to you and saved you time, any support on Patreon will be greatly apprecied: https://www.patreon.com/Olsro
