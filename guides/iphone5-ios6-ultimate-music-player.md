# Building the ultimate and storage-optimized (but sounding very high quality) classic Apple legacy device music player. It's about iPods, the annoying AAC decoding bug (with solutions) and legacy Apple devices, and sharing my feedbacks, discoveries and experiences with all of this.
*Date: 17 July 2024*

That Reddit post is a rewrite of this one : [https://www.reddit.com/r/LegacyJailbreak/comments/1d4btbz/the\_difficult\_and\_long\_quest\_of\_turning\_an\_iphone/](https://www.reddit.com/r/LegacyJailbreak/comments/1d4btbz/the_difficult_and_long_quest_of_turning_an_iphone/)

I did more tests and acquired more knowledge since then about old iOS and audio formats. This post is here to share you all of my finding and thoughts.

Why did I name "Apple music player" instead of "iOS" ? Because I am also gonna compare some iPods here, because I own some and it seems like they are also concerned by the same decoding bug which affects the playback of some songs (I can provide a sample which has clear artifacts to me if you wanna do your own tests).

# Update from 2024-08-19

This does not work well on iOS 6. Sometimes the iPhone 5 will go to recovery mode by itself for no reason when it is charging. To get a reliable experience as a music player on this device and all of the storage, using it on iOS 10 is your only option (or get an iPhone 5 that can use iOS 6 untethered).

# My music library

My library is full of FLACS and is around 20000 songs. I manage it using Swinsian on a MacOS Sonoma M2 Mac. I have a parallel and smaller Music library to sync with my iOS devices with much less songs, currently around 12000 (which represents around 47 gb of music after passing through my optimised conversion workflow). This whole paper is dedicated especially toward those who want a big jukebox filled with thousands of songs.

It's addressed to music-lovers who want to learn about finding a really good compromise between quality and portability while playing their offline music collection on a distraction-free device that is fast, reliable and fun to use. That's all a matter of optimisation and wanting to store and enjoy a lot of songs on a very legacy environment.

Because well, this whole affair could be closed by saying "Use MP3 LAME at VBR0/fdk-aac VBR5/fdk-aac CBR 256kbps" and you will be more than happy (especially if you have a little library). But what's interesting with lower bitrate (and especially with AAC which was designed to be transparent at just 64kbps by channel) is that you can store much more songs with much less storage. And storage is very limited especially on Nanos and iOS devices without any possible extend over time.

# Hardware compare

# iPod Minis 2nd gen

Pros :

* Sounding a bit warmer than neutral thanks to the Wolfson DAC which is a fun little sound signature that I find is subtile but enjoyable
* Can be modded pretty easily (battery replacement & flashmod)
* Can use Rockbox if flash-modded using a real CF card
* Feels rock solid like a Nokia 3310
* Really a distraction-free music device
* It's fun tech to use

Cons :

* Stock OS do not support modern and important metadata like the "Album artist" one
* Searching for a precise song is painful with the clickwheel
* The screen is too small to navigate conveniently between a lot of songs
* Not compatible with the remote of your headphones
* The battery indicator is not precise, especially on stock OS. You are stuck a lot of time with 0 bars of battery. When you are in this state, you fear that it will shutdown at any time.
* If you do not use it after 24 hours, it shuts down on Stock OS. Stock OS booting is very slow. Rockbox boot process is also slower compared to an "always-on" iOS device that wakes up instantly.
* CPU is slow and shuffling between a lot of songs takes several songs on Rockbox. On stock OS it's faster because stock OS stores everything in RAM at boot.

# iPod Classic 7th

Pros :

* Incredible battery life
* Really a distraction-free music device
* Very high storage. I have 1TB on it, I can litterally throw my whole library in FLAC.
* It's fun tech to use.

Cons :

* Searching for a precise song is painful with the clickwheel
* Not compatible with the remote of your headphones on RockBox. But it worked (at least for EarPods) on stock OS (as long as your iPod Classic is a gen 6.5+, it work on Stock OS).
* Difficult to get a stable experience under stock OS. Many microSD cards are making the device unstable.
* When using iFlash, there's no power management under Rockbox which makes it a power hog
* If you do not use it after 24 hours, it shuts down on Stock OS. Stock OS booting is very slow. Rockbox boot process is also slower compared to an "always-on" iOS device that wakes up instantly.
* A pain to open and repair. If I ever get another classic iPod in the future, I will opt for an iPod Video or I will just stick with the Mini.
* I had weird issues with it, like stopping songs/non working accessories (that should work on it like the FM radio) on stock OS.

# Legacy iPhones (from 3GS to 5)

My iPhone is an iPhone 5 64GB with a brand new battery from iFixit.

Pros :

* Can do anything an iPod Touch can do
* Touch gestures are really convenient at browsing and searching on a large music library
* Headphone remote is fully supported
* Native bluetooth audio support which can be useful to send some music to any speaker or headphones that support it
* Excellent DAC. It really sounds exactly the same as my iPod Classic 7th gen : a flat and precise sound.
* Can be found for really cheap.
* Can play web-radios using TuneIn Radio Pro or VLC
* Can play old iOS games. Many of them were archived and can be sideloaded easily. Their quality were much higher compared to click-wheel games.
* Very precise battery indicator with percentage

Cons :

* Difficult to downgrade to iOS 6 untethered in some conditions
* Limited storage. If you have a large library, you have basically no choice to get a 64GB model. Only the 5 and the 4S exists in 64GB.

# iPod Nanos

Not recommended, very low storage and very difficult to repair

# iPod Touches

Not recommended

* Those are often difficult to find in great physical shape and with good storage at good price.
* No auto brightness sensor, which helps a lot at reducing battery consumption
* Very difficult to repair
* Painful to downgrade untethered and even tethered depending on the model
* iPhones had Flash and much better cameras
* But if you already have one, well, this tutorial will also help you to enjoy it a bit better especially if your iPod can't go to iOS 7.

# Software compare

# iOS 6.1.2

Pros :

* Classic CoverFlow, which is very fun
* Fastest music app, that is also very ergonomic. You can do everything without frustrations : swipe left while playing a song to go back the album songs list, double tap to rate, shuffle an album or a whole artist, etc. Everything works fast and as intended, and feels natural.
* Best battery life
* Commcenter patch working to force enable LTE

Cons :

* Shitty modern app compatibility (but it's also a pro in a sense because it makes this a distraction-free device)
* Anything internet related will be painful because of old SSL algorithms and because of a very old webkit/JavaScript engine that will strugle with anything modern

My minimal list of tweaks on iOS 6 (I now avoid anything related to customization and adding animations to avoid creating instabilities) :

* Cyueue : add a very useful music queuing feature
* AutoLSMusicControls : show the music controls automatically on the lockscreen without having to double tap the home button for it
* CameraTweak : to improve the quality of the camera
* AppSync Unified : to sideload anything you want
* Commcenter patch : to enable LTE if you carrier did not support it back in the day
* Data Usage Monitor : a great tweak to monitor data usage directly in the status bar
* FullForce for Phone : to extend to 4-inch uncompatible apps
* Jukebox : to get music controls directly in the notifications center
* LowPowerBanner : to get subtle banners when your battery is low rather than aggressive popups
* mikoto : to unlock the volume of EU devices and disable "Reset all" and OTA updates
* NCSettings : to get toggles directly on the notification center
* Springtomize 2 : to hide all badges in the springboard (I do not use any other functions)
* SwipeSelection : to swipe on your keyboard to navigate on a text
* TubeRepair : to repair old youtube app
* WeatherX from skyglow repo : to repair the weather app on the notifications center and on the app
* SSLPatch : to fix a security hole
* iFile : to navigate the file system
* CocoaTop : a full featured process monitor
* KillBackground : to clear fastly the whole multi-task

My list of recommended apps on iOS 6 :

* Google Maps 4.3 : still work perfectly
* Opera Mini : block all ads and bypasses SSL errors on many sites like Wikipedia
* TuneIn Radio Pro/VLC : to listen to web radios using a streaming link
* OpenMaps : also a still working Maps app. Less intuitive than Google Maps but uses the OpenStreetMap APIs.
* Some retro games

# iOS 6.1.4

Same as 6.1.2 but the commcenter patch do not work, so it's not recommended.

# iOS 7.1.2

Pros :

* Great coverflow
* Great music app. Everything synced properly.
* Not concerned by the "AAC decoding bug"

Cons :

* Cannot enable LTE even with right commcenter patch applied (the switch appears but does not do anything)
* Flat design lol

# iOS 8.1.3

Pros :

* Same music app as iOS 7 which was great
* LTE supported without any patch
* Since iOS 8, external apps (like VNC and Infuse) could use hardware accelerated videos decoding. So if you wanna watch a lot of videos on fancy formats (like mkv), it's the version you want to use.
* Great camera app with HDR support
* Not concerned by the "AAC decoding bug"

Cons :

* Flat design lol
* Cannot connect to iCloud

The 8.1 music app could be improved with a tweak called "UpNext" to add music queuing feature. It works great. I do not recommend Aria 1, it's looking great but it's adding some weird bugs.

# iOS 8.2/8.3

Not recommended. Sorting is completely glitched. Many artists were sorted on the wrong letter.

# iOS 8.4.1

Not recommended with a large music library. Some tracks were searchable but were missing in the album view ! Very frustrating version to use.

# Latest release of iOS 10

It's working OK. Definitely usable and stable, but a bit boring. Some modern services/apps will still work on iOS 10. If you really need modern apps compatibility, that's the version you will want to use.

# My prefered version

iOS 6.1.2 without doubts. Especially since I found a work around to the AAC decoding bug which allows me to put the same number of songs on iOS 6 with great quality compared to any other iOS versions. Skeumorphic, fast, and very ergonomic stock music app is really great. The lockscreen was also very clean with fullscreen album art.

# Thoughts about dualbooting and coolbooter with iOS 6

I do not recommend dualboot. You lose too much storage space and there's some strange things with the dualbooted OS. Your music will glitch during certain actions like unlocking your device, locking it again, or switching apps in the multitask or pulling down the notification center. It seems like the dualbooted OS behaves differently compared to a real OS. I find it better (and ironically more stable) to use a tethered downgrade using Legacy iOS Kit rather than dualbooting to get the full iOS 6 experience.

To make the downgrades, you need to use "Legacy iOS Kit" from your Mac or from a Linux distro installation.

# The AAC decoding bug

On a previous post, I spoke about the AAC bug which concerned any iOS below 7. I made more tests since then. It's also happenning with MP3 songs, and even .opus when played through VLC ! It seems to concern all songs especially with low bitrate. Not all songs are affected the same way by this issue, and even on an affected song, most part of the song will not sound awful all along. I noticed that my iPod Classic 7th was also affected by this issue : it was sounding exactly the same as my iPhone 5 on iOS 6 with an affected file. It seems like they share the same audio decoding technical stack. The same file will play just fine on any modern iOS or device. The artifacts because of this bug are deal broker and very hearable to me. The whole sound is crackling.

# Get around the AAC decoding bug

I made more tests and noticed that you get around this bug by making yourself more cluttered inside the legacy Apple golden jail. If you convert your FLAC/ALAC/CD using a very old AAC engine that was made from Apple directly but before even iOS 6 was released, it will sound awesome and just as it should at any given bitrate. Is it a very bad idea to go back to a 2010 AAC encoder ? Not really. The quality did not improved by much for the AAC Low Complexity apple encoder during the last decade. On 2010 it was already very mature.

If you use an old iPod, you can also get around the "AAC decoding bug" just by starting using RockBox instead of the stock OS to play your modernly converted AAC files. On Rockbox, everything sounds as intended.

To make it more clear, here is how you can circumvent this issue, choose the solution you prefer :

* If you want to continue using modern tools to convert on your Mac like DBPoweramp, iTunes, or fre:ac, the faster/easiest way is to convert to ALAC, or to FDK-AAC VBR5 or CBR256kbps, or to MP3 with LAME VBR0. But by doing so you sacrifice a lot of storage, way too much to my liking.
* Don't touch your files and just upgrade your iDevice to iOS 7+ if it's possible. If you are on an old iPod, stop using Stock OS and stick with RockBox.
* Ditch your whole current lossy library and re-convert everything from your FLACS or from your CD using a very old iTunes version (< 10) or QuickTime version (< 7.7.1). And that's what I am going to explain with more details in the next chapter section...

# How do I convert my songs

# Required Tools

* Old iTunes/QuickTime : to do the music converts
* Any version of iTunes or MacOS "Music" app : to manage the library and sync with the device
* Foobar2000 windows version (can even be the ARM64 version on a virtual machine, it work on my M2 mac)
* Latest release of qaac : \[https://github.com/nu774/qaac/releases) If you need very old versions like the 0.99, I found it there : [https://www.videohelp.com/software/qaac/old-versions](https://www.videohelp.com/software/qaac/old-versions)

# iTunes versions tested on Windows 11 ARM on a Virtual Machine

iTunes [7.7.1.11](http://7.7.1.11) 32 bits : Sounds perfect

iTunes [8.2.1.6](http://8.2.1.6) 64 bits : Sounds perfect

iTunes 9.0.3 : Cannot install (can't start apple device service)

iTunes 9.2.1 : Cannot install (can't start apple device service)

iTunes [10.0.1.22](http://10.0.1.22) 64 bits : Converted files have the "AAC decoding bug" on old devices

iTunes [10.1.2.17](http://10.1.2.17) 64 bits : Converted files have the "AAC decoding  bug" on old devices

iTunes 10.5.3 64 bits : Converted files have the "AAC decoding  bug" on old devices

I do not recommend using an old iTunes version excepted if you use an old Mac or Windows machine. My process below just need QuickTime on Windows.

# QuickTime versions tested on Windows 11 ARM on a Virtual Machine

Short version : Just install Quicktime 7.6.6 : [http://www.oldversion.fr/windows/quicktime-7-6-6](http://www.oldversion.fr/windows/quicktime-7-6-6)

Long version :

Quicktime 7.6.2 : TVBR 127kbps Sounds perfect. Also do not install crap (does not install Apple Software Update and Apple Application Support). But requires an old iTunes or qaac 0.99. Also, for some reason, during the convert process is was losing multithreading. So it converted very slowly after some thousands of songs. Foobar maybe did not detect all time a successful convert or a failure ? Or the program could freeze ? This may be fixable using a very old build of Foobar2000 maybe. Since it requires a very old qaac version, I cannot recommend it.

Quicktime 7.6.6 : Perfect (Tested CVBR 128kbps and TVBR 144kbps). TVBR 144kbps whole library is 6% bigger than CVBR 128kbps. Quicktime 7.6.7/7.6.8 : For some reason, using TVBR and the latest version of qaac, many songs can't be encoded with error "Conversion failed: The encoder has terminated prematurely with code -1073741819 (0xC0000005); please re-check parameters". I don't want to look further. Using very old versions of qaac might help.

Quicktime 7.6.9/7.7 : TVBR not recommended by some folks on Hydrogenaudio because it produces even lower file sizes. Too low to their liking. I have also seen a bug report on this version with some songs on the Hydrogenaudio forum. I feel like 7.6.6 is a better version to trust. 7.6.6 is also the last existing version for Mac (excepted for Leopard), which means something; it is considered as very stable since years.

Quicktime 7.7.1 (and anything newer) : The first version that introduces the issue on legacy iOS/iPods by generating noisy artifacts when played on any legacy iOS or iPod. Not recommended at all. Excepted if you are going to play files using iOS 7 or if your iPod is rockboxed (but then, just use the latest encoding tools from Apple at this point...). In theory, using latest versions of Apple encoders should improve very slightly the quality at a given bitrate. But don't be fooled; the AAC encoding was already very mature around 2010 and Apple was using themselves AAC128kbps ABR for their whole iTunes Store and it was sounding very good.

# The convert process

Like I said at the beginning of this post, I do not want a small music library but to really take advantage the most of all of my available flash storage. The most interesting topic I found is this one about testing AAC : [https://hydrogenaud.io/index.php/topic,120166.0.html](https://hydrogenaud.io/index.php/topic,120166.0.html) It appeared that using AAC at 144kbps TVBR improved the quality by a lot while 128kbps TVBR remains very clean for all songs with very little to no disturbing artifacts. I personnally tried AAC CVBR 128kbps (same as iTunes when you tick the "VBR options), AAC TVBR 128kbps and TVBR 144kbps. All of those options sounds perfect/very near to a CD original especially if you listen to easy to encode music types like rap or pop.

I personnally decided to use TVBR at 144kbps to convert all of my music.

But not through iTunes ! My whole collection is FLAC. If I want to use iTunes, I first need to convert all to ALAC and create another duplicates of all of my music library. Then use iTunes. It will take ages and put me deep in many more complexity to handle...

My workflow is that I first use "DBPoweramp" to convert all music I find or dump to FLAC 44,1/16KHz, even .opus etc when I have no other choices. Most of my FLAC collection is legit FLAC files. But sometimes (from youtube content) you have to download 128kbps opus and have no choice. I converted also that minority of songs from my library to FLAC just to uniformize everything and be sure that everything is really 44,1/16 (CD quality standard). iTunes is also very slow because it does not use all cores of your CPU but only one. And iTunes cannot use the most advanced quality feature from the Apple AAC encoder, which is TVBR "True Variable Bitrate".

The key here is to use Foobar2000 that will call multi-threaded to all your CPU cores multiple instances of the program "qaac" (use the latest 32 bits version from here and put it in your encoders folder of Foobar2000 : [https://www.videohelp.com/software/qaac](https://www.videohelp.com/software/qaac) ) and remove qaac64.exe from that encoders folder. Foobar2000 will cleverly extract the PCM audio from your FLACS to transfer them to qaac. Then, qaac will call a library from Quicktime 7.6.6 to really do the convert. Foobar2000 will take the result and apply automatically the right meta-data on the converted .m4a file. You can even integrate SoundCheck/ReplayGain metadata using Foobar2000 after the convert process.

Then your file can be put on your iTunes library (or Music app on the latest MacOS Sonoma, it will also work) and can be synced safely to your device. It will sound freaking amazing. Low storage and very high quality, optimised as hell. [https://kenrockwell.com/apple/itunes.htm](https://kenrockwell.com/apple/itunes.htm) Ken rockwell even recommended 128kbps CVBR as transparent enough. Here we are at 144kbps TVBR which is even safer while still mainting the storage usage very low compared to the audio-lover quality you will get from your iDevice.

# About batteries replacements

I can't recommend enough iFixit. iFixit are not seeling cheap products but are testing their batteries (and it's really precious because when you buy anything for a legacy device you take a high risk at buying very old stock). I tested 2 iphone batteries from them and those were at 100% real capacity (even 105% capacity from one). On the other side, I got recently a battery 10 dollars cheaper from Amazon but it was only at 90% capacity when put into the iPhone. So if you need any battery, source yourself from iFixit or from any seller that can guarantee you the capacity and the quality of the battery that you are buying.

# Bluetooth or wired ?

I noticed that Bluetooth is sucking hard on the battery. It's better to use wired whenever possible. Using direct wired also avoid another layer of "transparent" compression.

# What headphones do you use ?

Pretty much only cheap ones but ones that sounds really good for their price ! I am going to share to you everything I use, feel free to answer me in comments to tell us everything you also use, I am very curious about all of this and I do not know (yet) much about headphones !

Here is my list of what I tested on it : Sony MDR-ZX310APB : 20 dollars only. That headphone is not covering any noise, they feel noisy for people around you who will hear your music easy. But that headphone sound really good, easy to drive for portable devices. It has also has a simple remote (without volume controls). Recommended if you play music in a pretty calm environment. It is very enjoyable to use and has a satisfying sound.

Sony MDR-EX110APB : 13 dollars only, intra-auriculars. Those intras are sounding so good and they have noise reduction. Not total reduction. But just enough to cover almost all annoying noise that enters your music. I recommend a lot those pair. They also have a simple remote (without volume controls). I love to use them.

Sony MDR-7506 : 99 dollars. This one is the most "audiophile" product I own that has a really rich song. It does not really isolate the noise around you so I also recommend using it in calm environment. The sound is obviously different and more rich than the 20 dollars MDR-ZX310APB but that headphone is also heavier to carry and better suited to use at home.

Apple EarPods : they sound OK, are cheap and the remote is convenient but they do not have any noise reduction which makes them painful in noisy environments. I do not recommend them much.

# Videos playback

A little bit more than music but old iOS devices had a screen of an amazing quality to enjoy watching shows and movies on them. Netflix is obviously dead for Legacy devices at this point but you can still convert your files yourselves using Handbrake. On iOS 6 I recommend to convert to mp4 and to play them using AcePlayer (which will call the native player if possible) or the native video player to take profit of hardware encoding. Kodi also can play mkv h264 files just file with hardware acceleration but you need to sideload the version 16.1.0 specifically to take advantage of it and get good battery life and performance. To transfer files fastly to Kodi iOS, you can install Apple File Conduit on Cydia then use iFunBox/iMazing to do the transfers of your video files. VLC or Infuse or any other App Store video players cannot use hardware acceleration for videos on iOS 6 because APIs related to that feature were private back then. Apple opened those APIs to developers only starting iOS 8. A4 devices (iPod Touch 4G/iPad 4) are limited to 720p. A5+ devices can go up to 1080p. With Handbrake when you are converting your files, use the "veryslow" preset and the Software Encoder to get a very high quality file with as little disk space as possible. Also, playing 1080p on the iPhone 5 will work but will not really look much better than 720p because of the size of the screen.

# Conclusion

Thank you for reading ! I hope you've learnt something. The last missing piece would be to understand, technically speaking, why any file converted with QuickTime 7.7.1 or equivalent iTunes version starts to encode files that will trigger the "old Apple devices" decoding glitch. I tried to hex compare 2 files (one affected and converted with QT 7.7.1 and one that is not with 7.7.0) but did not understand anything. I can't go any further on this field. If anyone that has good technical knowledge about the AAC format is reading this, feel free to do your tests and to investigate if modern AAC files could be "patched" to playback perfectly on old Apple devices.

My prefered setup and the one I now use the most is clearly my 64GB iPhone 5 on tethered iOS 6.1.2, even if I did not put my whole collection on it. Just about music quality itself, the music is sounding exactly to my hears the same as the FLAC music that is stored on my iPod Classic 7th and that is played with Rockbox. Compression is not noticeable with the settings I choosed (but it is maybe on some specific parts of some of specific of my tracks if I choose to not listen to music but listen and searching to any little and very subtle difference/artifact on it), which is not my cup of tea.

Most of the enjoyment about music will in my opinion be about your listening environment, your mindset and the quality of your headphones. Compression is a very little part of it as long as you respect the rules of the formats you use and as long as you convert from high quality files and at decent bitrate.