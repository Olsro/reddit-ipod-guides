# Some important facts about iPods that I wished I could know when I started getting into this hobby
*Date: 12 September 2024, last edited: 23 November 2024*

Hello all !

Here again to share some thoughts, I hope those can be helpful for someone here !

# About hardware

* Get an iSesamo (or equivalent) and tools (plastic) from iFixit or any good source. This is an investment that will avoid you to use improvised tools that you already have at home and that can multiply your chances to ruin your iPod when you will try to open it. Opening an iPod is very difficult without good tools and risky. But with good tools, the experience is very different.
* Breaking a connector is easy, even on the iPod Minis. This is still fragile old electronics, so it's important to do things very slowly and gently.
* iFlash adapters are good for Stock OS but very bad for Rockbox; using any SD adapters with Rockbox ruins the battery life
* Avoid the sketchy red CF adapter. It's bad and cause corruptions even with 128GB. And anything more than 128GB with it has serious issues.
* Compact Flash memory cards can be found for very cheap on Ali Express (search "KingSpec compact flash")
* USB fast charging cables that will output 12V if you have any fast-charging Android charger can be found on Ali Express for around 15 dollars. This is in my opinion a better option rather than getting the firewire brick (search for "usb 12V Ipod").
* SATA modding is not recommended even if Rockbox supports power management with it, this solution has too much spin-up latency and is more power hungry
* Compact Flash modding is the most power efficient and safe way to get the best possible experience. It's in my opinion the best current way to storage mod iPods. Avoid the quest of making 1 or 2TB pods like pest, it does not worth it overall excepted maybe if you expect to use Stock OS with AIFF or ALACS.
* I formerly had an iPod Classic 7th gen with an Imcort Design. It has issues with many accessories and also playback was unstable on Stock OS randomly (it completely stop until reboot). It had two 512GB Samsung EVO microSD cards in it, which is a recommended brand and type of cards to use.
* It's better in my opinion to compress songs to lossy like Musepack rather than use FLACS on a 1TB pod that will have many issues with Rockbox and a poor battery life. 256GB CF cards still have plenty of space and allows me to compress my whole library to Musepack q7. Currently have many audiobooks and around 30000 mpc q7 songs and still have 40GB of free space.
* Someone reported on the Rockbox bug tracker that Kingspec CF cards (and maybe all CF cards ?) have issues on the iPod Classics 6th gen+, so be very carefull : \[https://www.rockbox.org/tracker/task/13412?string=compact&advancedsearch=on&type%5B0%5D=2\](https://www.rockbox.org/tracker/task/13412?string=compact&advancedsearch=on&type%5B0%5D=2) ATA code of the iPod 6th gen+ is different on RockBox.
* The screen of old monochrome iPods will be very readable in direct sunlight compared to color screens from modern iPods. I like those monochrome screens, even the one of my Mini when using a small font with Rockbox to print as much text as possible to ease the navigation.
* The iPod Video can get a 3000 mah battery mod which will make it last like "forever" without charging.

# About software

* At first, I thought like Stock OS will be good enough for me. But it is a really frustrating experience especially on anything before the iPod 6th gen; it's missing important tags (like Album artist), customization and features like a search on very old iPods. Also having to be forced to use an old AAC encoder for lossy music to sound fine is a big drawback. Having to use iTunes can also be considered to be a strong drawback. Stock OS often "just works" but feels like 2005, while Rockbox feels much more modern and "on-par" with modern music player apps on smartphones. Stock OS may be good enough for small music librairies though. And when you know how to use Rockbox and all of this possibilities and the good themes to use (and even modify ones), I feel really like home with Rockbox.
* The Musepack audio codec is damn good, and encoding your FLACS to Musepack rather than MP3 is a very good decision that I can't regrest in any way. It sounds awesome and Musepack is VBR by default, and also Gapless. Starting Musepack q5, quality is very very reliable with this format. It does handle electronic music very well. You just convert all all forget about it.
* Stripping embedded cover arts and resizing cover arts is very important and can make you save some GigaBytes easily if your library is huge. It's really something important to include in your management process :)
* Always keep your original FLACS so you can always change your lossy format later and even build multiple lossy librairies for different devices
* Foobar2000 and DBPoweramp are very good tools to convert your music in batch without messing with metadata
* Foobar2000 can sanitize the metadata which helps Rockbox at scanning all of your files without errors (it is especially true with Musepack)
* MP3tag is a good tool to process cover arts in batch and to do change in batch in MP3Tags
* With a CF card, I have issues with the stability of Disk Mode only on my iPod Video. It sometimes freeze on the PC (and on the iPod itself I don't see anymore any kind of activity) so I cannot continue copying/see the files until I reconnect. But if I boot completely the Stock OS and let it connect as a disk, it's perfectly stable from there.
* I documented many things about a Rockbox iPod Mini setup here, there is many precise infos on it that you may find helpful : [https://www.reddit.com/r/ipod/comments/1ebxjur/ipod\_mini\_sharing\_thoughts\_and\_tricks\_on\_daily/](https://www.reddit.com/r/ipod/comments/1ebxjur/ipod_mini_sharing_thoughts_and_tricks_on_daily/)
* If you want your database to build faster on device, avoid the Musepack format, it looks like it need 3x more time to parse the metadata compared to AAC. But if you use your PC to build the database, it will be fast enough (requires only a few minutes for me to build the database for 30000 songs).
* Gapless music playback is supported on Stock OS only starting the iPod Nano 2G or the iPod Video 5G which is pretty surprisingly late in the iPod line of products. Any older iPod (like the mini) did not support it. But Rockbox has this feature for all models of iPod.
* Syncing your content by using an old iTunes version (9.2.1 or 10.7 especially) runs like a dream. It is a fast&reliable syncing setup, and fully compatible with Phase playlists. In the other hand, using anything newer than iTunes 12.0.1 is known to break smart playlists auto-refresh on the iPod itself. Also, syncing a Windows formatted iPod on MacOS Sonoma is known to lead to broken album arts on device, you've been warned.

# Support me on Patreon

You can tip me here if you appreciate my work : [https://www.patreon.com/Olsro](https://www.patreon.com/Olsro)