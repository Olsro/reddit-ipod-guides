# Stock OS is more viable and fun than what I thought
*Date: 3 October 2024, last edited: 25 October 2024*

I recently got for cheap and restored a MacBook Pro 13-inch mid-2010 that is now running Snow Leopard 10.6.8 and iTunes 10.7 on a 500GB 2.5 SSD.

Last days, I worked into changing my way to manage and sync music to use again iTunes and see how good it can be to use that old device as an "iPod sync station" that contains all the music.

I already know that iTunes 10.7 can run (even on Apple Silicon macs) on Sonoma but with bugs and laggy coverflow so I gave up the idea to manage my music on my modern Mac. It feels wrong and also unstable as this workaround will probably break or be even more buggy on more recent versions of MacOS.

# What about 32mb RAM iPods on Stock OS

* My iPod Mini 2G with 26770 songs can shuffle all but it corrupts menus when I do it (Genres and Composers menus appears empty until reboot). Excepted that, it is fast and seems pretty reliable as long as you navigate and play reasonably sized playlists.
* My iPod 4G with 30198 songs crash (auto-reboot) when shuffle all or trying to play all songs. But for normal usage, it seems also to work just as excepted.

Both iPods are CF modded. The Mini is modded with a CF from Amazon, and the 4G is modded is modded with a Kingspec 256GB from Ali Express.

I was surprised how good those iPods could still be mostly usable even with so many songs. I thought they would not even be able to boot up... but they actually can !

Then I have my "Ultimate" iPod which is a 5.5 iPod Video with a 3000mah battery and a Kingspec CF 256GB as storage. Since this one has 64MB of RAM, it can shuffle everything (with also 30198 songs) and I probably still have plenty of RAM left to add much more than that. But for some reason, menus also corrupts after shuffling all songs, just like my iPod Mini 2G. I also now have also an iPod Classic 7G which can shuffle all songs without corrupting menus. Even with the same amount of RAM, it seems like the improved OS os the Classic can get a better usage of the available RAM.

# Library management

It is strongly advised to copy all your "Album artist" tag to "Composer" so you will be able to navigate using this tag on your Stock OS pod. It will feel just as good as under Rockbox (with the real "Album Artist" field) if you do it this way. I used the software mp3tag to achieve this.

I manage my files on an external drive connected on my modern Mac. When I finish processing the files, I transfer them (with network file sharing) to the old Mac that just copy the files to iTunes 10.7 without having to worry about anything. Finding reliable software on Snow Leopard is difficult and also the modern Mac has just much faster IO and CPU/threads to do mass operations on thousands of files.

# Library quality

I converted that library into AAC 160kbps CVBR using QuickTime 7.6.6 on a Windows virtual machine on my modern Mac. Using an old Apple encoder avoid annoying artifacts that affects all old iOS and old iPods. You can find more details about it here : [https://www.reddit.com/r/LegacyJailbreak/comments/1e5ox79/bulding\_the\_ultimate\_and\_storageoptimized\_but/](https://www.reddit.com/r/LegacyJailbreak/comments/1e5ox79/bulding_the_ultimate_and_storageoptimized_but/)

I used mp3tag to convert album art to .PNG then to .JPG again with the software "mp3tag" at 500x500px quality. This process allow all of my cover art to be shown correctly on Rockbox and also to save up a lot of memory space. 500x500 is still excellent quality with cover flow on iTunes, it looks good.

Right now I never used iTunes 10.7 on that old Mac to import CDs. I don't know if it is recent enough to be affected by the artifacts issues. I know that iTunes 10.7 is affected by it on Windows and also on MacOS Sonoma because I tested it personnally in both cases. But maybe iTunes on Mac is using librairies on the system to do the encodings ? If so, Snow Leopard is probably fine since it was made in 2009 so before the encoding issues. EDIT : Snow Leopard 10.6.8 is affected by the encoding bug, even when downgrading to a very old iTunes (iTunes 8).

Right now I just continue to use my modern Mac to import new musics and I also continue to use my process with QuickTime 7.6.6 Windows version + Foobar2000 which guarantees equivalent quality both in Rockbox and on Stock OS on playback.

# Playlists management

Creating smart playlist on iTunes then syncing just work. It is a very pleasant experience to build a library with this version of iTunes, the UI is awesome and it is always butter smooth.

# What I found cool with Stock OS compared to Rockbox

* Real lowpower Sleep Mode; the iPod can wake up at any time almost instantly.
* A little animation when you navigate through menus. It feels very smooth.
* Being able to organize everything through iTunes then syncing just work. With this old iTunes version, there's no album art corruption or oddities. It is running very fast on this old Mac and does not feel broken or bloated like the Apple Music app.
* Simplicity. When everything is synced, the most difficult part of the job is done. On the device itself, there's almost nothing to configure and it just work.
* Rating songs and Plays count just work on Stock OS and will even be synced on iTunes and directly update all your smart playlists accordingly. It is simple but very powerful. Rockbox can also store those infos dynamically if you gather runtime data but I always had issues and lag when enabling it so it is disabled. So on Rockbox, the only way to organize persistent things is through the powerful dynamic playlist system while on Stock OS you can do it lazily just by rating your currently playing song and playing to them and all the smart playlists will update accordingly.
* On the iPod Video (or more recent), it's possible to play video content.
* Power management is working for iFlash adapters

# What makes me still want to boot into Rockbox

* Custom theming is very fun and showing album arts on black & white iPods is fun
* Battery percentage/status is very precise on Rockbox compared to Stock OS especially on my iPod 4G/Mini 2G
* Text scrolling in all menus + smaller font is improving a lot the navigation experience on the tiny screen of the iPod Mini especially
* Dynamic playlists and advanced queuing is great, it is much more powerful than an On-The-Go playlist. In general, Stock OS playlist engine is great depending on how good you have made your playlists under iTunes, while Rockbox focus on the "on-device" experience so you can sort and register your playlists directly on device.
* Shortcuts to rapidly shuffle and repeat songs by maintaining "MENU" in WPS is so convenient compared to the need to navigate through several menus to enable those options on Stock OS
* Rockbox can shuffle all of my songs without issues on all of my iPods, it will not crash or do strange RAM corrupts when trying to do it but will rightfully build a limited playlist picking songs from all of my music library
* For Audiobooks and Podcasts because Rockbox can play .OPUS files and encoding audiobooks at .OPUS 40kbps helps saving a lot of memory storage for this usage compared to mp3 or aac which require more than the double amount of necessary storage space to get an acceptable quality.
* Morse search is very efficient
* If I need to use the Kokkia Bluetooth transmitter, on my Mini it is working under Rockbox but not on Stock OS
* Excellent configurability. When my iPod is docked, I like to enable auto-backlight when switching songs but keep it off the rest of the time.

# Dual boot with RockBox

I noticed that syncing with iTunes actually helps a lot under Rockbox on a specific case. Now, BUILDING THE DATABASE IS 3x FASTER THAN BEFORE ! iTunes syncing creates very short paths for all of your music which seems to help a lot Rockbox at building its database. It now require only around 20 minutes rather than around 1 hour when all my music was sorted in directories following this (very standard and readable) structure : Album Artist / Album Name / Music file name.mpc

# Why iTunes 10.7 ?

* Last version with Cover Flow before Apple removed it
* Can sync also all old era iOS devices, even iOS 6 ones

But be carefull with this old version; I could not manage to make it connect to the iTunes Store or auth my Apple account on it. So if you bought music on Apple, you are screwed and need a more recent version of iTunes unfortunately. Online radios still work though.

# Films and TV shows on the iPod Video

How 240p content can feel so pleasant to watch ? I was amazed.

Tagging and converting content is very painful and requires several tools to do it right with very good audio quality. But once everything is done, the result is amazing especially for 4:3 shows and cartoons that will take the whole screen. It's pure 240p so it should theorically look very bad, but here the screen is so small that it actually look pretty good. More than good enough for 4:3 shows. Also, it is smooth, I could not notice annoying dropped frames.

I thought this was an useless and obsolete gimmick but it is in fact a definitely fun thing to do with a pod.

I used this guide as a base : [https://github.com/adriaanjelle/iPod-Transcoding-Guide](https://github.com/adriaanjelle/iPod-Transcoding-Guide)

If you are on a Mac, you can use fre:ac to convert a .dts file to a stereo FLAC rather than over-complicate yourself into using the DTS plugin on 32 bits folder. Then I use Foobar2000 (ARM64 version) + qaac (x86) + QuickTime 7.6.6 to encode a compatible audio track at 160kbps CBR (never use VBR and never go above 160kbps or you will get issues ! One possible issue was graphical glitches while playing the video). Look at the technical specs : [https://support.apple.com/en-us/112601](https://support.apple.com/en-us/112601)

Then when you have your AAC audio file, you have to use mkvtoolnix to merge it into an mkv. Then, you will need to use Handbrake to do the final convert to mp4.

I made an Handbrake profile, feel free to use it to save you some time (call it "Apple 240p30.json") : [https://pastebin.com/6UPhe6xK](https://pastebin.com/6UPhe6xK)

Finally, you can now import the mp4 file into iTunes. Now you need to manually tag your file under iTunes.

# Cracked Clickwheel Games on the iPod Video

Vortex is very fun... and that's almost it. Bejeweled is very laggy and difficult to control. Zuma feels great at first but it is complicated to be precise and it start getting frustrating as the difficulty increases. Also, the game start to lag when there is too much animated moving balls on screen. Playing Zuma on this device just makes me want into installing the full game on a real PC and control the frog using a real mouse on a big screen to get the real experience.

iPod Quiz is not really fun, questions can be too tricky and precise to find the answers even if you know pretty well your music library. The fun of this game depends on how the AI decides to ask you fun (and very possible) questions or when it decides to just punch you with impossible questions to make you lose all of your lives.

Brick/Pac-Man/Solitaire/Music Quiz can also give me some fun. I would like to test also the guitar hero clone (Phase) and some other games (Peggle seems fun !) but those are not available publicly yet unfortunately.

# Conclusion

I hope you've learnt some new things that can help you at managing your own iPod(s) ! Stock OS is clearly far from being obsolete and can still be fun and provide a good user experience. But when your amount of songs starts to be huge, building good playlists and tagging everything right is really important to get the most of it.

If you like my work, feel free to tip me on Patreon : [https://www.patreon.com/Olsro](https://www.patreon.com/Olsro)