# Encoding audio tracks for any clickwheel iPod or below iOS 7 device with the best possible quality/disk space ratio
*Date: 6 October 2024, last edited: 2 April 2025*

Have you ever heared terrible crackling artifacts when listening to your self-converted lossy audio or videos on your iPod ? You are not mad; any iOS device below iOS 7 and any clickwheel iPod have issues with modernly encoded files. I reproduced it with modern AAC files but also with LAME encoded MP3s. This issue can be reduced by using very high bitrates, but it will sometimes still persist on some songs with less noticeable differences.

I will focus on this paper on how to get the most quality for your device while keeping the storage impact as low as possible. ALAC and AIFF lossless are supported on the iPods but both have a huge impact on battery life and syncing those heavy files takes forever. The iPod was designed to play lossy files at reasonable bitrates (128kbps CBR from the store especially) and it is what they do the best especially on Stock OS.

# Distinguish artifacts

You may hear also small artifacts coming from the compression itself on difficult songs or if you have golden ears. The trick here is that if you think that a music track sound awful on your iPod, you should also try to listen to it on any modern tech device like your computer. If the music does not have any crackles and terrible noise on your computer, this means that you have just noticed this terrible issue that only affect you if you play the same file on any old iOS device (< iOS 7) or clickwheel iPod.

Consider that if you find one problematic track, many more are also affected even if you notice it less, so I recommend just to blindly convert from lossless to lossy using this guide to uniformize everything (but always keep somewhere your original lossless tracks, you should never delete those files just in case).

# Important: About your source files
I recommend lossless files at 44.1KHz/16 bits/stereo (CD quality). After encoding, there will be no notions of bits in AAC, but the sampling rate (for example 44.1KHz) will remain in the AAC file. iPods needs 44.1KHz or 48KHz sampling rates; anything different will cause issues. If it's different, resample your audio source files (Foobar2K/DBPoweramp can do that) before continuing further in this tutorial.

# Windows setup (the easiest and most powerful method is here)

We are going to setup a powerful music convert environment here to mass (and in a multithreaded fashion) convert any kind of samples to your settings. You now (thanks to an update of this guide) don't even need to have iTunes or QuickTime installed on your computer for this to work, or any Apple software.

1. Install the latest Foobar2000 version (you can even install the ARM64 version if your machine is an ARM64 one) : [https://www.foobar2000.org/download](https://www.foobar2000.org/download) If you want to sync your iPod using Foobar2000 rather than iTunes, you must install the x86 version
2. Install the Foobar2000 encoders pack : [https://www.foobar2000.org/encoderpack](https://www.foobar2000.org/encoderpack)
3. Inside the ```foobar installation folder/encoders``` folder, typically located at ```C:\Program Files\foobar2000\encoders``` rename ```qaac64.exe``` to ```oldqaac64.exe``` and rename ```refalac.exe``` to ```oldrefalac.exe``` because we want Foobar2K to use our 32 bits version that will use the 32 bits QuickTime binaries.
4. Install the QuickTime 7.6.6 portable encoder by copying and replacing the files from [encode-audio-tracks-oldapple/foobarencoders.7z](encode-audio-tracks-oldapple/foobarencoders.7z) to the same folder as in the previous step (```Foobar/Encoders```). For making your own portable encoder, [look at #Building your own portable encoder](#building-your-own-portable-encoder)
5. You should now be able to do the converts directly from the Foobar2000 UI: 
	1) Scan some (lossless if possible) music to convert. Click on ```Library``` (located in the top menu of the app) then click on ```Configure```, a new window will appear. On the left of this window, click on ```Media Library``` then you can add your ```Music folders``` by clicking the adequate ```Add...``` button. Compared to iTunes, Foobar2K will scan everything, even FLAC files, and will be able to convert from them. Now that your library is scanned into Foobar2000, you can close this window with the ```OK``` button.
    2) Make sure you have enabled the album list window, this can be done by going to View -> Layout -> Quick Setup -> Any option with the Album List enabled
	3) In the dropdown view (bottom-left of the window), select ```by artist/album```
	4) Now right-click on ```All music``` then select ```Convert``` then select ```...```
	5) Click on ```Output format``` then double-click on ```AAC (Apple)```
	6) Bit rate mode must be: ```Constrained VBR``` and the quality ```128 kbps``` or ```160 kbps```. If you really need to save disk space, you can go down to 96 kbps (but it will not feel transparent enough all time). Any bitrate more than 128kbps will give diminishing returns perceptually more you increase the bitrate. If you don't know what to choose and want absolute guarantee that it will be very safely transparent even for Classical music (which is one of the most complex music type to compress), choose ```160 kbps```.
	6) Now click ```Ok``` to close the encoder configuration window, then click ```Back```. In ```Output format```, you should now see ```AAC (Apple), CVBR```
	7) Now click on ```Destination``` then check ```Convert each track to an individual file``` (should be already checked) then put this pattern: ```%album artist%/%album%/%filename%``` which will be clean, simple and without conflicts if your music is properly tagged.
	8) Now click on ```Back```; the new destination pattern should appear under the ```Destination``` clickable link. You can now ```Save <<``` your new preset with a custom name so you can re-use it anytime later (for example it can be: ```Apple AAC QuickTime```).
	9) Now you can ```Load >>``` your preset anytime you want then click on the ```Convert``` button to start converting the music files into the destination folder of your choice.

6. Then you can copy the converted files and import these on your favourite iTunes version. Or you can do everything within Foobar (x86 version only) by using this great plug-in : [https://yuo.be/ipod-manager](https://yuo.be/ipod-manager). If going with this path, it's a good idea to configure the plugin to auto converts tracks before sending them to the iPod. That way, no needs of using iTunes to send the music and you won't have to convert it beforehand, the plugin will do everything for you! We just need some configuration. You need to provide the ```flac``` binaries for it to work in the same way as the conversion preset.
	1) Download the ```flac``` binaries from the github repo: https://github.com/xiph/flac/releases/download/1.5.0/flac-1.5.0-win.zip.
	2) Inside the ```flac-1.5.0-win/Win32``` folder, copy all 4 files to the ```C:\Program Files\foobar2000\encoders``` folder.
	3) Click on ```Library``` then click on ```Configure```. On the left of this window, click on ```Tools```, ```iPod Manager``` then ```Conversion```.
	4) Check the ```Convert audio track in unsupported formats```.
	5) Click on ```Edit presets...``` under the ```Encoder set-up``` and ```Encoder preset``` section.
	6) Click on ```New``` and call the encoder preset with a custom name, you can use ```Apple AAC QuickTime``` to keep consistency.
	7) In the ```Executable:``` field, input the path of the ```qaac.exe``` file, it should be ```C:\Program Files\foobar2000\encoders\qaac.exe```
	8) In the ```Parameters:``` field, input ```-v NUMBER - -o %d```. The ```NUMBER``` value is the one you have selected previously, ```128 kpbs```, ```160 kbps``` or ```96 kbps```. In this case, we want ```-v 160 - -o %d```.
	9) In the ```File extension:``` field, input ```m4a```.
	10) Click on ```Close``` button, it saves your newly created preset.
	11) Under the ```Encoder set-up```, select ```Apple AAC QuickTime``` in the ```Encoder preset``` dropdown.
	12) If you are using ```ReplayGain``` (Foobar2k works wonder to add it to your audio files), under the ```Encoder set-up```, select ```Calculate gain after encoding``` in the ```ReplayGain processing```. Because iPods don't support ```ReplayGain```, the plugin will neatly convert the values to the standard use by iPods, ```SoundCheck```. You can change which value you want to use in the ```Database``` page and the ```SoundCheck preference``` field. You can choose between ```Track gain``` or ```Album gain```.
	13) Because iPods don't process tags in the same way as other playback devices (especially the ```Artist``` tag), you can map the correct Metadata. That way, when converting / sending music to you iPod, it will adapt the metadata to be correctly processed by the iPod. In the ```Database``` page, under the ```Metadata``` table, go to the line ```Artist``` and input to its ```Mapping``` field: ```%album artist%```.
	14) Please note that iPods cannot process multi artist, therefore you'll have multiple entry with all artist configuration. It's not a big issue, but it's important to know this quirk.

Recommended settings :

* For an audio tracks of a video content : 160kbps CBR (Constant BitRate). It is the maximum supported by iPods in this case. Never use VBR here, I tried it and I had random colored ugly artifacts during video playback on my 5.5G iPod Video. To get an audio track from a MKV, use this : [https://www.videohelp.com/software/Inviska-MKV-Extract](https://www.videohelp.com/software/Inviska-MKV-Extract) Then you can merge the AAC file to an MKV using MKVToolnix : [https://mkvtoolnix.download/](https://mkvtoolnix.download/) then you can finally convert the mkv file to mp4 with AAC passthrough using Handbrake. You can download my Handbrake 240p profile here (confirmed working with both iPod Videos and Classics): [encode-audio-tracks-oldapple/Apple240p30.json](encode-audio-tracks-oldapple/Apple240p30.json)
* For music : 128kbps CVBR or 160kbps CVBR.

# Mac OS X setup (not recommended, less flexibility, and iTunes can't even convert in a multi-threaded fashion)

Snow Leopard (10.6) seems to be the last version to have a non-affected AAC encoder. But if you already applied all updates on your current installation, you are already screwed. Mac OS X is much more annoying than Windows about this, because QuickTime's framework is deeply embedded inside the OS itself. Also, Mac OS X does not have a very powerful tool like Foobar2000 on Windows to mass-convert from any type of files using the QuickTime encoded to mass-produce files with a multithreaded fashion, unfortunately.

If you don't want to import CDs or convert ALACs to AAC with your Mac, I advise you strongly to use iTunes 10.7 (coverflow) or 12.0.1 (last one to support smart playlists updates on device). 12.0.1 is not compatible with snow leopard but you can use the version 11.4 which can still connect to the store on this OS.

Edit : I also created a .pkg to downgrade the QT related librairies on your current installation of Snow Leopard. You can find it here : [https://github.com/Olsro/snowleopardquicktimedowngrade/tree/main](https://github.com/Olsro/snowleopardquicktimedowngrade/tree/main)

My recommendation is to clean install Snow Leopard again and follow this steps :

1. You can install it normally from the DVD. It can be 10.6.3 or 10.6.7 directly.
2. You can still update on Internet using this version of MacOS to 10.6.8. You can apply all updated excepted iTunes updates and the Security Update from 2013-004. Don't apply this security update or it will update your QuickTime to a problematic version that introduced the encoding issues ! If something from this security update matters to you, you can install parts of it using Pacifist (https://www.charlessoft.com/pacifist_olderversions.html) but it's old and very obsolete stuff anyway.
3. Now install iTunes 9.2.1 : [https://secure-appldnld.apple.com/iTunes9/061-8725.20100722.Bhnyt/iTunes9.2.1.dmg](https://secure-appldnld.apple.com/iTunes9/061-8725.20100722.Bhnyt/iTunes9.2.1.dmg) It is the last version that you can install to import your CDs and do your ALAC convert safely. Any iTunes version starting 10.0 does not call anymore the embedded QuickTime component on the OS and the encoding issue will be here. If you already have a more recent version of iTunes installed, it is possible to downgrade it easily by using Pacifist to force install it with administrator rights.
4. Now you can just set the import settings. My recommended settings are 160 kbps VBR. Also, you should really enable "Error corrections" if you are willing to import CDs.

If you need to sync iOS 5, iOS 6 devices, or iPod Nanos 6G or 7G you need a more recent version of iTunes. My recommendation if you need a more recent version of iTunes is to install Windows 7 or Windows 10 on Bootcamp and do all of the converts from there since doing it from Windows allows much more flexibility, and use a legacy iTunes version on your Mac partition (on Snow Leopard, Leopard, Lion, etc) with the glitched encoder that you will never use directly so it don't matter.

The issue here is on the produced music files, not on the syncing process by itself. So any version of iTunes that is 12.0.1 or below 12.0.1 is fine for just syncing.

# Why 128kbps or 160kbps and not 256kbps ?

AAC was designed for much lower bitrates than the very old MP3 to sound just as good. Taking advantage of it means using it around its recommended transparency threshold which is just 128kbps (64kbps per channel). You can read more about this here, your music will sound great with this setting (excepted if your source files are bad obviously, I recommend avoid convert lossy to lossy) : [https://kenrockwell.com/apple/itunes.htm](https://kenrockwell.com/apple/itunes.htm) Starting 128kbps CBR, it's around 99% perfect if your source is lossless.

Don't expect to get "2x more" quality if you use something like 256kbps. It will be very close in terms of quality but you will be able to store 2x less music on your pod and syncing will be 2x slower.

**Why not AAC TVBR rather than AAC CVBR ?**

AAC True Variable BitRate is considered slightly inferior in terms of quality. There is a small risk that it use a too low bitrate. CVBR is considered safer overall but increases slightly the size of the converted library. Also, TVBR is not even available on iTunes, so the widely used mode was always the CVBR one so I tend to put more trust in it.

**Why not just use some random iTunes version from around 2005 or 2000**

The AAC encoder evolved a lot to solve issues between 2000 and 2010. Using one of the last working AAC encoder guarantee you to get the best possible lossy quality that you can get with your Stock OS iPod/old iOS device.

# Can this help if my iPod is skipping songs ?

Yes. Those crackles may come from the inability of your device to correctly decode the modern files in some way. Using the product how it was intended reduces the risk of strange issues overall which includes skipping. If it still skips songs, check the sampling rate, it should be no more than 44,1 KHz for music content and never more than 48 KHz for the audio track of video content.

I tried to use my 3 CF-modded iPods (4G, Video 5.5G, Mini 2G) on their Stock OS and never had any issues of this kind with those legacy encoded AAC files. If your iPod is SD modded with SanDisk SD cards, you may try some other SD brand with it.

A Redditor confirmed to me that following my guide compared to using modernly encoded (with MediaHuman) mp3 files completely fixes all skipped songs issues he had with his iPod Video, by using the same SD card.

# What if I don't care about Stock OS and only use Rockbox ?

Rockbox is not affected at all by this decoding bug which is a software bug affecting old iOS and all iPods OS with modernly encoded files. You can just throw any kind of mp3 files and AAC files and from my experience, those will sound on Rockbox exactly how they sound on your computer. Nothing to worry about in this case, Rockbox does the job.

# On iOS 5/6, can I bypass this issue by using VLC ?

External players are also affected by the issue. I could even reproduced this issue by encoding .OPUS files and try to play those using VLC on iOS 6. So if you want to refurbish an old iPod Touch or iPhone, try to use it on iOS 7+ or follow this guide to build a fully compatible music library.

# What are exactly the affected versions of QT/iTunes ?

There is some documentation here : [https://www.reddit.com/r/LegacyJailbreak/comments/1e5ox79/bulding_the_ultimate_and_storageoptimized_but/](https://www.reddit.com/r/LegacyJailbreak/comments/1e5ox79/bulding_the_ultimate_and_storageoptimized_but/) On Windows, Quicktime 7.7.1 (and anything newer) is broken. I also reproduced the issue starting iTunes 10.0 on Windows. iTunes 9 could not install on my ARM64 virtual machine but this version will probably be OK. But on Windows, I prefer to just use QuickTime 7.6.6 and do all the converts with Foobar2000 which is great at preserving and processing the metadata of the music files.

# What if I do not hear any strange issues with my modernly encoded files ?

Continue to be happy and ignore this paper, music is all about feeling ;)

# Building your own portable encoder
You can make one yourself by using the ```qt-2015-makeportable.cmd``` file that I provide in this archive. Note - you must provide the installer with a Quicktime installer like QuickTime 7.7.0 or something else.

# Conclusion

It was such a long trip to understand then document this issues that required many tests. Right now I am very happy about the result, the music sound and feels like "CD quality" while saving a damn lot of disk space compared to ALAC or AIFF. The result is very satisfying. The AAC encoder was very mature around 2009 and well tested with all kind of musics to be rock-solid starting 128kbps CBR.

# Alternatives using moderns musics conversions stacks
DBPoweramp Music Converter (also available on MacOS !), fre:ac, Foobar2K and many popular programs can help you to encode your music using the modern Apple AAC encoder.

When using the modern encoders, it's crucial to convert at **very** (but not excessive) high bitrates to avoid old-devices artifacts so you will get a clean sound from your beloved iPod. 

I recommend to always choose 256kbps CBR because any kind of VBR mode is not giving any meaningful quality improvement past 192kbps. VBR was invented mostly because encoding CBR at around 128kbps was not transparent in some cases, so it is a way to help clearing noticeable artifacts in this case.

If you want to use iTunes/the Apple music app, you can choose the import preset "iTunes Plus" which is 256kbps CVBR, or select yourself AAC 256kbps CBR (without VBR). For reference, all songs purchased from the iTunes Store are as of 2025 still encoded at 256kbps CBR. Don't forget also to enable the option "Error correction" in your import settings if you plan to import real CDs on iTunes.

If you cannot use the Apple AAC encoder, use the fdk-AAC encoder at CBR 256kbps. The fdk-AAC encoder is available in most serious music converting programs.

**Don't use AAC 320kbps or any VBR setting that is close to it.** AAC is not like mp3: there's no meaningful quality improvements past 256kbps, anything more will be purely academical. Also, excessively high bitrates AAC files can/will cause instabilities when played with your iPod (TVBR setting -q 127 for example is known to cause system crashes at almost each songs switches on all iPods older than the Classic line).

# Support my work

Writing content takes time; so if you like my work, I would appreciate any kind of tip on my Patreon : [https://www.patreon.com/Olsro](https://www.patreon.com/Olsro)
