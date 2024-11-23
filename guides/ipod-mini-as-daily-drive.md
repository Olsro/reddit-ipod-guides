# iPod Mini : sharing thoughts and tricks on daily driving it !
*Date: 25 July 2024, last edited: 23 November 2024*

# Motivation to write this

It's possible to find many resources about other models of iPod, especially the video and the classic. Finding resources on Rockbox is more difficult compared to stock OS. And generally, the Mini received much less love overall. There's not much updated documentation and thoughts about Rockbox on it.

I feel like the Mini is the perfect starter but many people here replaces it as soon as they can for an iPod Video, an iPod Touch or an iPod Classic and keep their iPod Mini in "collection" but prefers to use for "real use" other kind of iPods that have larger screens and more modern ergonomics and stock OS firmware.

I personnally came back from the Classic and the iOS 6 iPhone 5 to go back on roots to daily drive my blue 2nd gen iPod Mini and give it the attention it deserves and get is as "ultimate" as I did for my other legacy Apple devices.

# My current iPod Mini configuration

My current iPod Mini 2G is blue (Da ba dee da ba di) and has a new battery and flash storage.

* The battery is a Cameron Sino 750mah (### CS-EC003XL). I definitely recommend it, it perfectly fits in
* The Flash storage is a real compact flash of 128GB. 128GB is the maximum that you can get for a reasonable price, anything higher is just absurdly out of price. Excepted on Ali Express, where you can find 256GB ones for pretty cheap, search "kingspec cf card", those are confirmed to work great on iPods.

The Mini is clearly the iPod that is the most fun and safe to open.

That iPod is almost fully loaded of songs . The music folder is synchronized to it using the software "ChronoSync" on MacOS Sonoma. That music folder has around 25000 songs converted at TVBR AAC 144kbps using Foobar2000 and QuickTime 7.6.6 and qaac 32 bits. You can find more info here : https://github.com/Olsro/reddit-ipod-guides/blob/main/guides/iphone5-ios6-ultimate-music-player.md (on this topic, it's the same library for the iPhone 5 64GB iOS 6 but heavily filtered to fit into 64GB of storage). Here on my mini I have enough space to put everything unfiltered. That's a lot of content...

# Advices about Rockbox configuration

There's some things I advise you to change (I will always explain why) to get a better experience on your Mini with Rockbox.

* Use the latest daily build. It is recommended by Rockbox developers themselves to get the best experience overall. Install the Font Pack during installation, it's very important so themes will work ok out-of-the-box. Be also aware that most theme you will be able to download for the iPod Mini does use fonts that does not support japanese characters.
* EDIT 2024-08-03 Now I fully switched to the (dead but still audiophile) Musepack (.mpc) format ! A detailed post is available here https://github.com/Olsro/reddit-ipod-guides/blob/main/guides/musepack-2024.md it's the most efficient music format for Rockbox devices. It will save you some battery and is also more storage efficient than mp3. AAC is better on low-bitrate but requires more CPU power to be decoded. If you switch to the Musepack format, don't forget to sanitize tags using Foobar2000 or Rockbox will not be able to decode them. I did battery benchmarks and get 30 minutes more with Musepack -q 7 files (which are far more heavier than AAC 144 kbps TVBR files, but I can still put far enough music to be satisfied). If you decide to switch to Musepack, I advise you to select a quality between -q 5 and -7 to get an excellent audio quality.
* It is useful to stop the playback if you accidently unplug your headphone from the iPod : Settings -> Playback Settings -> Pause on Headphone Unplug -> Pause on Headphone Unplug -> Select "Pause".
* It seems like charging the iPod Mini directly on your PC/Mac is much faster compared to charge it on a "fast charging" modern mural USB charger.
* Use the database rather than the file browser : the database allows much more flexibility. I use the file browser only for my audiobooks (I added an empty file called "database.ignore" so my audiobook folder is never indexed on the database). Initializing the database each time you add or remove songs is very long at first but when it's done it just work until you need to do it again. You can now also build the database much faster if you learn how to build it directly from your PC: https://github.com/Olsro/rockbox-docker
* Let's change some settings about the database, go to Settings -> General Settings -> Database :
   * Load to RAM : QUICK (because "On" is too slow at boot. Enabling load to RAM will allow to navigate much more fastly and confortably and also to create playlist (for example to shuffle all of your library) much faster)
   * Auto Update : NO (because YES is very very slow, it cannot be reasonably enabled if your library is huge like mine)
   * Gather Runtime Data : NO (Why ? Because it often wakes up the disk to store some data which uses power, and also because it seems like to sometimes delay a lot during 10 and 20 seconds the refresh of the While Playing Screen at each songs change/skip. While it's frozen, the While Playing Screen still shows the name of the previous song that stopped playing seconds ago. So to get a consistent experience it's better to disable it.)
* Disable file system structure caching (because it will make longer boot times with no real advantages if you use only the database browser. The RAM you will not be able to use to bufferize songs before of that will stress your disk more. More RAM you have to bufferize songs, more less your iPod will need to wake up the disk to load data again from it.) : Settings -> General Settings -> System -> Disk -> Directory Cache -> No. Don't worry about speed if you need to sometimes use the file browser anyway (I personnally use it to load my audiobooks), it will still be more than decent.
* Enable Speaker Keyclick sounds (because it is fun and satisfying) : Settings -> General Settings -> System -> Keyclick -> Speaker Keyclick -> Yes
* Equalizers and any sound processing : I recommend avoiding it on the Mini. It will stress the little ant CPU of that device.
* Album art (Settings -> Playback Settings -> Album Art). Select "Prefer Image File". Use something like this : [https://www.mp3tag.de/en/download.html](https://www.mp3tag.de/en/download.html) to mass optimize and extract your covert arts (using the "Actions" menu) to JPEG at 98x98. More infos are available here : [https://github.com/Olsro/rockbox-mini2g-themes](https://github.com/Olsro/rockbox-mini2g-themes) Using cover arts is in general a little more work. If you don't need it, just completely disable album arts and never bother against with them. Cover arts will often not look very very good consider the size of the screen and the fact that it is a black&white screen.
* Theme : I use themes that I heavily improved, fixed and modified by myself. All my work is shared there : [https://github.com/Olsro/rockbox-mini2g-themes/tree/main](https://github.com/Olsro/rockbox-mini2g-themes/tree/main)
* Settings -> General Settings -> Playlists -> Playlist Viewer Settings -> Track Display -> Title & Album from ID3 tags. Enable this option to get a reliable view in any playlist viewers by using ID3 tags rather than file names. This option is especially relevant if you sync your music with iTunes which obfuscates heavily the file names.
* You should try enabling morse code input. I feel it's much easier than the clunky virtual keyboard to input things using just the center button of your click-wheel. (Settings -> General settings -> System -> Use Morse Code Input). It's useful to use the Search feature more comfortably.
* I advise to enable ReplayGain Track Gain especially if you shuffle a lot between different songs to normalize the volume (Settings -> Playback Settings -> Replaygain). Be sure that all your songs are properly tagged with ReplayGain, if not you can easily do it with Foobar2000 or DBPoweramp using a DSP Effect. You may also enable "Prevent Clipping".
* Enable Glyphs Caching to improve responsiveness of the UI : Settings -> General settings -> System -> Limits -> Glyphs To Cache -> 65540
* Set the Idle Poweroff to 3 minutes (Settings -> General settings -> Startup/Shutdown -> Idle Poweroff)
* Disable Fade On Stop/Pause (because it's adding an un-necessary processing) : Settings -> Playback Settings -> Fade on Stop/Pause
   * Use Foobar2000 to sanitize tags :
   * Before sanitization full library size : 109.7GB
   * After sanitization full library size : 105.47GB
   * Saved storage : 4.23GB. High quality cover arts are hungry on disk space !
* Rockbox wiki recommends disabling Accessory Power Supply while you do not use accessory to save some power (Settings -> General settings -> System -> Accessory Power Supply)
* Go to Settings -> Display -> LCD Settings and configure it like this, it's settings I like and that are power-saving friendly while still staying pleasant to use to get the backlight automatically when you will need it :
   * Backlight : 10 seconds
   * Backlight (While Plugged In) : 10 seconds
   * Backlight on Hold : Off
   * Caption Backlight : No
   * Backlight Fade In : Off
   * Backlight Fade Out : Off
   * First Buttonpress Enables Backlight Only : No
   * Backlight Exemptions : Enabled YES, then go to Settings and enable "Exempt volume" + "Exempt play" + "Exempt seek" + "Exempt skip"
* The screen of the iPod Mini can never be shutted down while playing music. If you want to save maximum battery while playing music, it seems like a good idea to lock your iPod on the main menu rather than in the while playing screen, which will avoid any UI constant refresh while you do not care about it. The battery saving that you may get doing this is probably very small, but it is also probably not null since you are reducing screen draws and background calculations by avoiding those constant screen refreshes.
* Speaking about battery life again, choosing the right format will also help at keeping your CPU usage low thus reducing energy consumption. FLAC format seems to be the king as a good compromise between disk usage and easy decoding by the player (as long as your FLACS are all 44.1 KHz/16 bits, be very carefull about this). So if you can fit all of your FLACS, just do it this way, that's my advice. But about me I personnally have just too many songs so I need to save a lot of space. AAC (which is MP4) is more efficient than MP3 especially at low bitrates but seems a bit harder to decode (not by much) by looking at the benchmarks. You can also control the bitrate to reduce the stress on your iPod. Use the Apple Encoder to get the best quality, and always with a VBR encoding mode. And do not use absurd (academical) bitrates like AAC320kbps CBR. Prefer TVBR or CVBR at 192kbps maximum. Anything starting 128kbps will sound very good with the AAC format. As I already wrote it, I personnally use AAC TVBR at 144kbps for music and AAC TVBR at 80kbps for audiobooks. Those settings lead to aggressive compression comparing to the lossless audio but it still sound very good. It's not just "meh", it's sounding very satisfying with all kind of music even classical or music from movies.
* If you want your database to build faster on device, avoid the Musepack format, it looks like it need 3x more time to parse the metadata compared to AAC. But if you use your PC to build the database, it will be fast enough (requires only a few minutes for me to build the database for 30000 songs).
* If you want to know more about Rockbox and feel more confident on using it and understand its philosophy, I can't recommend enough to read the full manual that was really well done by the developers : [https://download.rockbox.org/manual/rockbox-ipodmini1g.pdf](https://download.rockbox.org/manual/rockbox-ipodmini1g.pdf)

# Thoughts about Rockbox

I feel like using it Rockbox provides a really modern experience as long as all of your library is properly tagged. Building initially the database takes a very long time but once it's done and loaded to RAM, navigation is very fast and queuing songs and albums to a dynamic playlist is very fast and easy. You do not feel exactly like you are using a device from 2004 when it's rockboxed, it feels very fun and great to use even with an absurd amount of songs (I currently have 25000 tracks on it + many audiobooks).

Here is some advantages I found on using Rockbox :

* Bypass elegantly the 20000 tracks limit. It's so impressive that it still manage to boot only in seconds on Rockbox. And Rockbox is (kinda) multi-threaded so that you can start to navigate before the database is fully cached at boot, it will just be slower.
* Ability to queue songs. It's just so good. You can pick songs of your liking and add them to your queue. Just like you expect from any modern Music app. On iOS it was added very late, in iOS 8.4.
* Support more metadata (The metadata "Album artist" especially is very important and unsupported on stock OS)
* Support much more audio formats (flac can be useful). It also supports the modern "opus" format, but I tried it and it's laggy even with 32kbps files for audiobooks. The whole UI of Rockbox is lagging as the CPU of the iPods seems fully sollicitated on the task of trying to decode the audio. The best idea is that you stay focus on easy to decode formats : flac > aac > mp3. Aac is a bit slower on rockbox online benchmarks than mp3 but not by too much, and at usage it's all fine and there's no issues at decoding my TVBR 144kbps files.
* You get more compatibility with some accessories, like the Kokkia Bluetooth which does not work in stock OS on the Mini but works on Rockbox. The modern Apple Radio Remote also works on rockbox (the FM tuner does not work but the buttons on the remote do work).
* Auto real shutdown after a few minutes (sleep mode during 24 hours on stock OS is constantly sucking some battery)
* Very fast boot time especially with a lot of songs. Rockbox just need a few seconds to cache the database in RAM and while it is doing it at boot, you can already start to navigate and even play a song without any issue during the process.
* Customization. A lot of possible customization.
* You get the ability to search for songs in your big library directly from your ipod when you need. I advise you strongly to enable morse search, so it is even better to type letters conveniently with only the center button of your clickwheel.
* Gapless music playback
* Does not remove the stock OS, it's dual boot
* Smart views, which is even better than smart playlists but you need to create these views textually. You can learn how to do it if you follow this guide: https://github.com/Olsro/reddit-ipod-guides/blob/main/guides/rockbox-smart-playlists.md

# Thoughts about stock OS

Stock OS can be more interesting than Rockbox is your are sensitive to any of these points :

* Smart playlists created through iTunes
* You are syncing a pretty small music library (something like 1000 songs or less should be mostly convenient to navigate on stock OS)
* You really want to use it as Apple intended it
* You have installed any CF to SD adapter (iFlash, red adapter, etc). Stock OS will give you more than 3x time the battery life compared to Rockbox. Rockbox does not support power management on SD adapters unfortunately.

# What are the hardware little drawbacks of the Mini compared to most modern Apple tech as a music player

* Slow CPU/GPU, but it's ok as long as you do not try to use the .opus music format and as long as you stay reasonable with settings.
* Slow transfer speed. Modern iPod classic can transfer music files very fastly compared to the iPod Mini. It's a problem only once; because when your music is on it, it's ok.
* Little screen that is black&white : album arts looks ugly and there's not much space to print text. That's why I recommend to use a small font to feel less the little size of the screen. It's ok and charming when you get used to it. Scrolling always work great to show parts of text that you cannot read. Album art is gimmick to me, I can navigate without any album art and not see it in the while playing screen without any frustration. Overall this problem is overrated especially if you use my themes: SprocketModern/Minimless that are using a very small font and compared to Stock OS, Rockbox OS will always scroll automatically the long texts.

# A final word

I hope all of those info could help you at enjoying more from your device. The Mini is definitely fun to use with so much content on it and when it is finely tuned. It's also a great device to listen audiobooks. Rockbox also has many great apps like a great clock and many many games but I do not care about clickwheel games, the main interest of an iPod is about listening music with backlight off. Queing songs, and albums, then let it play all the songs one by one by doing something other or just chilling.

Feel free to let me a little kind message here if you appreciated the reading or if you have learnt something, it's always a pleasure to read the feedbacks. Or even to criticize things from my post or share your own settings and setup if you feel so :)

# Bonus

I made some battery Rockbox benchmarks here from my iPod Minis : [https://www.reddit.com/r/ipod/comments/1ee7dq0](https://www.reddit.com/r/ipod/comments/1ee7dq0)