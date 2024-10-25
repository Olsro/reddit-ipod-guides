# Musepack : working with this music format in 2024 on a modern ARM64 machine
*Date: 30 July 2024*

# Introduction

I got interest in this format by reading its decoding benchmarks on the Rockbox website : [https://www.rockbox.org/wiki/CodecPerformanceComparison](https://www.rockbox.org/wiki/CodecPerformanceComparison)

It's even faster at decoding than mp3, and it's also more efficient than mp3; it's possible to get near perfect transparency at much lower bitrate. Even using -q 7 parameter, Musepack will still produces smaller files than mp3 lame VBR0. Musepack is a niche audiophile format.

# My laptop hardware

It's a mighty Macbook Pro M2 Pro. I have an ARM Windows 11 virtual machine. It's a very efficient laptop and also very silent but it's ARM and x86/x64 emulation can be pretty slow with old software and on special situations like this one we will look into.

# Music converters and Metadata

My first attempt was to use fre:ac on MacOS. Conversion to Musepack (.mpc) is fast. But then I noticed that the created mpc files were lacking some metadata. Even worse : some metadata were altered ! For example album artist with collabs. Sometimes, on my FLAC, the metadata will be "artist1;artist2". For some reason, the produced file by fre:ac will only show "artist2".

I also tried to set up a Linux virtual machine to use more different softwares. The most interesting and polished was SoundKonverter. It was also very fast at doing the file converts to mpc, but also have issues with metadata.

To my now extended experience, I trust only Foobar2000 and DBPoweramp at being reliable at reading and copying metadata to the converted files. Metadata are very very important on Rockbox as they will organize the whole database. Having errors in metadata directly affects greatly the user experience at finding music when you have a big library.

The issue here is that the Mac version of DBPoweramp does not support musepack. And Foobar2000 on Mac can't convert audio files at all.

So... am I really forced to copy 500GB on an NTFS external drive to do all the convert work on a x86/x64 windows machine to get some reasonable performance ? Nope, I've found a better way, so continue reading !

# Using a Windows virtual machine to do the converts

So I did exactly what I decided to do in the past with AAC using QuickTime 7.6.6 to produce compatible files for legacy iOS (anything below 7) : I just use the Windows version of Foobar2000 to do the things. It's slower than on native MacOS but it was fast enough to convert my whole library in a few hours even though the QuickTime 7.6.6 encoder is an old Intel x86 piece of software. The performance was reasonable enough.

The issue here is that the x86 Musepack encoder is very very slow on ARM64 Windows 11. It requires more than 1 day to do the task of encoding my whole FLAC library ! It's just too slow and not acceptable. But there's no way to call the musepack encoder arm64 linux version directly from the Windows version of Foobar2000. There's also no way to do that on Wine.

I tried to run Foobar2000 under CrossOver and it was also just as slow. The issue here seems that Musepack is really suffering from the translation layer doing in real time the convert of x86 instructions to arm64 so they can run on my Mac arm64 machine.

So I downloaded the C++ Musepack Source code from 2011 and managed with some tinkering to compile it fully under a modern Visual Studio C++ 2022 environment on my Windows 11 virtual machine.

I wanted to share here because it may help some people. I couldn't found any Windows artifact of this somewhere online (excepted the good old boring x86 version that is distributed in several places).

I compiled the latest sources in all of the 3 interesting architectures : arm64, intel x86, intel x64. It's very simple to use that architecture-optimized encoder : just replace the .exe in the encoders folder of DBPoweramp or Foobar2000 so they will be able to call it.

You can download everything directly on my GitHub repo : [https://github.com/Olsro/mpcenc-all-archs-windows-builds](https://github.com/Olsro/mpcenc-all-archs-windows-builds)

The encoding speed is now around 2.5x faster using the native arm64 version, so it definitely worth it. The magic of Apple silicons macs is that they can work on this task very silently and power efficiency is very good. Foobar2000 is handling 10 multi-threaded encoding tasks. I can even still use this machine normally during the converts, it's not very much slowed down. It's encoding music files in the average speed of x250.

# Does using a more efficient codec than AAC (easier to decode) really impacts the battery life of an iPod Mini ?

I will do the benchmarks in the future, stay tuned ! Theorically it should. I am currently using with AAC TVBR 160kbps files. I've noticed using the debug menu that the iPod often has to boost the CPU to 80MHz to decode them. On musepack files it stays stable at 30MHz underclock. With .OPUS it's the extreme case of slowness to decode : that very old iPod has to stay constantly at 80MHz to make realtime playback possible.

EDIT : DONE ! Available here : [https://www.reddit.com/r/ipod/comments/1ee7dq0/rockboxed\_ipod\_mini\_2g\_its\_time\_to\_benchmark\_the/](https://www.reddit.com/r/ipod/comments/1ee7dq0/rockboxed_ipod_mini_2g_its_time_to_benchmark_the/)

Using Musepack -q 7 files leaded to 2% more battery than AAC TVBR 144kbps files.

# Why using a dead format ?

It's pretty widely supported in fact and it was left dead in a very mature state. I've read on Hydrogenaudio that it can not be fully transparent with a very few killer samples, but it's also the same for AAC, and MP3 seems to have much more killer samples even at VBR0.

For real world listening, any settings starting with -q 5 will be fine. I personnally use -q 7 just because I will be able to put enough songs to my liking. The fact that it can be decoded so easily seems very interesting at reducing the power consumption of embedded devices with very low CPU performance. Musepack is even supported on Palm OS or Windows CE so you might enjoy it if you own those kind of very old PDAs : [https://www.musepack.net/index.php?pg=pro](https://www.musepack.net/index.php?pg=pro) Also, Musepack is fully open-sourced and patent-less. I hope that DBPoweramp will support Musepack encoding on Macs in the future so it will be even easier/faster for me but until then my workaround is acceptable and this might also be very useful for you if you own a (still rare) ARM64 Windows machine.

Musepack is also natively gapless !

# Is using the Intel x64 build faster than the Intel x86 ?

I seriously do not know. Do your tests and report here the result, I took the time to make an Intel x64 build just in case it could be useful to someone here. It may be a little bit faster than the Intel x86 one. I did not even tested it, it's just better for me to directly use the arm64 version.

# Thank you for reading !

# UPDATE1 2024-07-31

Rockbox cannot parse most of the tags unfortunately for some reason (Album artists, album, etc). Using Musepack seems like a dead-end unfortunately. The mpc tagging system is APEv2 which is different than what other formats use. On Foobar2000, Metadata are showed perfectly fine but the converter inside Foobar2000 is probably doing some weird workaround to integrate ID3Tags without any loss and Rockbox cannot understand this workaround. Bummer ! I am going back to AAC TVBR 160kbps because it just work.

# UPDATE2 (same day)

If using the Windows version of mp3tag (not the mac version !) it's possible to write ID3Tag version 1 easily to mpc files in addition to the APE v2 tags. But unfortunately, id3v1 does not support the "Album artist" tag so it is still kinda frustrating.

I can avoid this problem by remapping completely "Album artist" to "Artist" and it should be mostly OK if I accept to lose other metadata and rely only on simple ones. The ID3 metadata were pretty barebones.

The situation is pretty frustrating in my opinion. I don't wanna mess so much with metadata so I am going back to AAC TVBR 160kbps files. There's really no way to replace APEv3 to ID3v2.

The other way would be to encode to MP3 LAME but file sizes will be much higher than my AAC files for no real guarantee of saving up a lot of battery on my iPod Mini. I feel like it does not worth it and it might sound worse than my AAC files especially if I use an encoding setting lower than VBR0.

# UPDATE3 2024-08-01

Despite what is wrote on the Rockbox manual, Rockbox can perfectly read APEv2 tags on Musepack files (yeah, even complex ones like "Album artist"). But not on MP3 files. And not if your tags are not sanitized properly. I don't know what tags are really causing issues, but using Foobar2000 to sanitize them to only keep the basic ones is what will do the trick. I also deleted album art from tags while sanitizing the tags. Now everything is working perfectly. Rockbox is really perfectly compatible with Musepack V8 files and I am happy that it is.

# UPDATE4 2024-08-13

I switched to Musepack q5. It still sound very good and it allows me to store around 25% more songs compared to the q7 setting.