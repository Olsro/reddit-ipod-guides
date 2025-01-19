# Some important facts about iPods that I wished I could know when I started getting into this hobby
*Date: 12 September 2024, last edited: 19 January 2025*

Hello all !

Here again to share some thoughts, I hope those can be helpful for someone here !

# About hardware

* Get an iSesamo (or equivalent) and tools (plastic) from iFixit or any good source. This is an investment that will avoid you to use improvised tools that you already have at home and that can multiply your chances to ruin your iPod when you will try to open it. Opening an iPod is very difficult without good tools and risky. But with good tools, the experience is very different.
* Breaking a connector is easy, even on the iPod Minis. This is still fragile old electronics, so it's important to do things very slowly and gently.
* iFlash adapters are good for Stock OS but very bad for Rockbox; using any SD adapters with Rockbox ruins the battery life
* Use the sketchy red CF-SD adapter only if you can accept slower transfer speed (around 30%) and their related 128GB limitation. These also often need an MBR repair trick to pass successfully the restore.
* USB fast charging cables that will output 12V if you have any fast-charging Android charger can be found on Ali Express for around 15 dollars. This is in my opinion a better option rather than getting the firewire brick (search for "usb 12V Ipod").
* SATA modding is not recommended even if Rockbox supports power management with it, this solution has too much spin-up latency and is more power hungry
* I formerly had an iPod Classic 7th gen with an Imcort Design. It has issues with many accessories and also playback was unstable on Stock OS randomly (it completely stop until reboot). It had two 512GB Samsung EVO microSD cards in it, which is a recommended brand and type of cards to use.
* The screen of old monochrome iPods will be very readable in direct sunlight compared to color screens from modern iPods. I like those monochrome screens, even the one of my Mini when using a small font with Rockbox to print as much text as possible to ease the navigation.
* The iPod Video and Classics can get fairly easily a 3000 mah battery mod which will make it last a very long time between two charges.
* Avoid CF modding with the green board if you can, because you will get some noise in your headphones during every disk accesses. iFlash products like the iFlash Solo don't have any disk accesses noises. Looks like the green boards are lacking some necessary shielding. If you are using a green board with a slim 4th gen Mono, it is possible to reduce the noise by sticking a sheet of paper on the back to reduce a lot of interferences. On other models (Classics/Videos), I couldn't reduce the noise.
* Be aware that there's a huge power management issue with Rockbox with the iPod 4th gen Mono/Photo, and minis 2nd gen (and maybe other models) that prevents Rockbox to completely shut down the storage of the device, so battery life on Rockbox with these models will be very bad when flash modded. Since October 2024, iPod Videos and Classics are known to be completely fixed for Rockbox with iFlash adapters, so get these models if Rockbox matters to you or wait for a fix.

# About software
* To use with Rockbox, the Musepack audio codec is damn good, and encoding your FLACS to Musepack rather than MP3 is a very good decision that I can't regrest in any way. It sounds awesome and Musepack is VBR by default, and also Gapless. Starting Musepack q5, quality is very very reliable with this format. It does handle electronic music very well. You just convert all all forget about it. Apple AAC VBR is also very reliable nowadays and a solid choice for Rockbox. The Stock OS does not support modern AAC features (the AAC PNS), so to get the best quality on Stock OS you should use an Apple AAC encoder from 2010 or before (I made a guide for that).
* Don't do overkill about compression settings. Starting AAC 128kbps VBR, you get at least 99% of the experience from the source file, and listening to your fear of missing something out, will just create more issues while taking much more storage and syncing times. You will start to fight for pretty much nothing in reality and a lot of placebo effect. For AAC, you want to convert between 128 and 192 kbps. About Musepack, use the default q5 setting. To increase significantly the quality, it's important to get good IEM and headphones and to listen in a calm environment.
* Stripping embedded cover arts and resizing cover arts is very important and can make you save some GigaBytes easily if your library is huge. It's really something important to include in your management process :)
* Always keep your original FLACS so you can always change your lossy format later and even build multiple lossy librairies for different devices
* Foobar2000 and DBPoweramp are very good tools to convert your music in batch without messing with metadata
* Foobar2000 can sanitize the metadata which helps Rockbox at scanning all of your files without errors (it is especially true with Musepack)
* MP3tag is a good tool to process cover arts in batch and to do change in batch in MP3Tags
* With a CF card, I have issues with the stability of Disk Mode only on my iPod Video. It sometimes freeze on the PC (and on the iPod itself I don't see anymore any kind of activity) so I cannot continue copying/see the files until I reconnect. But if I boot completely the Stock OS and let it connect as a disk, it's perfectly stable from there.
* I documented many things about a Rockbox iPod Mini setup here, there is many precise infos on it that you may find helpful : [https://www.reddit.com/r/ipod/comments/1ebxjur/ipod\_mini\_sharing\_thoughts\_and\_tricks\_on\_daily/](https://www.reddit.com/r/ipod/comments/1ebxjur/ipod_mini_sharing_thoughts_and_tricks_on_daily/)
* If you want your database to build faster on device, avoid the Musepack format, it looks like it need 3x more time to parse the metadata compared to AAC. But if you use your PC to build the database, it will be fast enough (requires only a few minutes for me to build the database for 30000 songs).
* Gapless music playback is supported on Stock OS only starting the iPod Nano 2G or the iPod Video 5G which is pretty surprisingly late in the iPod line of products. Any older iPod (like the mini) did not support it. But Rockbox has this feature for all models of iPod. On Stock OS, I've made a guide to encode whole CDs as chaptered tracks so you can store 10x more songs on Stock OS without lags/bugs and get gapless playback working with all models on the Stock OS.
* As of today, I feel at home both with Rockbox and the Stock OS. The Stock OS required a bit of work to fit my needs, but once everything is synced and properly tagged/converted, it's a pleasant and reliable experience.
* Don't forget to sync the preserved Clickwheel Games if you own an iPod Video/Classic to get some more fun from your device: https://github.com/Olsro/ipodclickwheelgamespreservationproject
* Syncing your content by using an old iTunes version (9.2.1 or 10.7 especially) runs like a dream. It is a fast&reliable syncing setup, and fully compatible with Phase playlists. In the other hand, using anything newer than iTunes 12.0.1 is known to break smart playlists auto-refresh on the iPod itself. Also, syncing a Windows formatted iPod on MacOS Sonoma is known to lead to broken album arts on device, you've been warned.

# Support me on Patreon
You can tip me here if you appreciate my work : [https://www.patreon.com/Olsro](https://www.patreon.com/Olsro)