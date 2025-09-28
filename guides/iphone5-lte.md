# How to enable LTE (4G) on any iPhone 5 on iOS 6
*Date: 21 June 2024*

This guide is for enabling LTE (4G) even if your carrier did not support it on iOS 6 !

# What do you need

* Your iPhone should not be on 6.1.3 or on 6.1.4. Really, there's no bypass even by faking the version number. Commcenter will install if you force it to do it on 6.1.3 on 6.1.4 but it will not work to bypass signatures of carrier packages so it will just never work.
* If you are on iOS 7 or iOS 8, this guide will probably still work if you use the a more recent Commcenter patch.
* Best version of iOS to do this is 6.1.2. It's almost the same as 6.1.3 excepted a security patch in webkit (and security patches to block jailbreaking) and it is almost the same as 6.1.4 which contained only a patch to the speaker profile.
* This guide should also work for the iPad Mini 1G/iPad 4 on iOS 6
* It should work on Coolbooted/dualbooted iOS 6. My setup is tethered using Legacy iOS Kit.
* Commcenter patch for iOS 6 : [iphone5-lte/jp.backspace.ios5.commcenter.patch_6.1r1-23_iphoneos-arm.deb](<iphone5-lte/jp.backspace.ios5.commcenter.patch_6.1r1-23_iphoneos-arm.deb>) (you can also find it in this Cydia repo : [http://beta.leimobile.com/repo/](http://beta.leimobile.com/repo/) )
* iFile (on Cydia)
* A SIM card should be inserted and unlocked. Your phone should be connected on the 2G/3G network of your carrier if possible (just so the symbolic link will be created to directly go to the right bundle of your carrier using iFile).

# The steps to follow

1. Install the Commcenter patch ! Without it, all modifications done below will not be applied.
2. With iFile, go to /private/var/mobile/Library/Carrier Bundle.bundle/ (which is a shortcut to your current Carrier Bundle)
3. Open the file carrier.plist with the Properties reader
4. Click on the « + » button and add a boolean key called « Show4GSwitch » then validate. Then, enable this boolean key !
5. Erase the folder called "overlay" that is located in /var/mobile/Library/Carrier Bundles/
6. Reboot. Now you need to check if the 3G switch has been correctly replaced by the LTE switch.

If it is the case (it was the case for me), congratulations ! If not, follow those extra steps to help refreshing it :  
7) Reset network settings

8) Reboot. The 4G switch should be there. It's called "LTE" on iOS 6, but it's just the other name for 4G. Now enable it. If you do not get 4G after enabling it, it's probably because you do not have any compatible antennas around you.

# Cons

* 4G draws the battery a little bit faster all the time
* Most of the time, I get a bad (or a very bad) 4G signal. It's still fast to use but it's also known that a low signal requires even more power by the phone to be maintained, which affects battery life.
* The iPhone 5 is a "fake" 4G phone : it did not support many bands (it's the same for all 2012 devices from Apple like the iPad Mini 1G or the iPad 4). Apple fixed this in later hardware revisions (iPhone 5C/iPhone 5S). This is why you will get weaker signals compared to using 4G using a modern phone : it's because you cannot connect to many existing antennas.
* Don't expect to phone anyone using the 4G network because VolTE is not hardware supported. So when 2G and 3G will be removed, you will not be able to call anyone.

# Pros

* Do it if 3G has been already removed in your country. It's better to have that limited 4G rather than staying on 2G all the time, because 2G is too slow for anything.
* 4G is very fast. Latency is very low compared to 3G and you have a lot of bandwidth. You feel the same experience as using your iPhone under a good wi-fi network, which is very positive and impressive.
* Connection sharing (tethering) through wi-fi or USB will provide a much better experience to your Mac and other connected devices when you are connected to the 4G.
* It's an option, so you can still disable it through a toggle to switch back to 3G at anytime

# The situation in France and iPhone 5 models

[https://support.apple.com/fr-fr/112016](https://support.apple.com/fr-fr/112016)

There are 3 different iPhone 5 models :

GSM A1428 that supports LTE bands : 4, 17 (AVOID THIS MODEL)

CDMA A1429 (it's the one I got) that supports LTE bands : 3, 5, 13, 25

GSM A1429 that supports LTE bands : 1, 3, 5

Here are some data about the situation in France in 2018 about LTE : [https://selectra.info/telecom/actualites/acteurs/choisir-smartphone-selon-operateur](https://selectra.info/telecom/actualites/acteurs/choisir-smartphone-selon-operateur) In France, the GSM A1428 is a model to completely avoid, because no antennas are compatible ! The CDMA is not so bad because it supports the Band 3 which is widely available The GSM A1429 supports also the band 1. It's the best model for France because it will support a bit more antennas compared to the CDMA model.

As you can see, whatever your model is, most bands are unsupported anyway especially the "band 20" which has the most amount of available antennas.

Check the situation in your country to understand the capabilities of your iPhone 5 where you are.

About 3G, [https://www.usine-digitale.fr/article/jean-christophe-ravaux-bouygues-telecom-nous-eteindrons-notre-reseau-2g-fin-2026-et-la-3g-fin-2029.N2095136](https://www.usine-digitale.fr/article/jean-christophe-ravaux-bouygues-telecom-nous-eteindrons-notre-reseau-2g-fin-2026-et-la-3g-fin-2029.N2095136) Bouygues Telecom should maintain the network until 2029 so it's still a lot of time from now to enjoy it.

# How do I use it

* My carrier is Bouygues Telecom, but my guide should work for any carrier in France. Orange/SFR are known to also have a strong 3G network. I do not recommend using Free since it's using the 3G network from Orange with limitations. Any MVNO (like NRJ Mobile, YouPrice, Prixtel, etc) will also be fine.
* At first, I did not use 4G all time to save the battery by staying on 3G as much as I can. But afterall, the difference is pretty minor and I get some 4G almost everywhere, so enabling it all time is safe.
* For web radios, I use TuneIn Radio Pro 5.1 (version 2.0 seems unreliable, version 4.3 seems to have a memory leak, and 5.1 is fine). On the go, I use the AAC128kbps streams that I add manually on the application. I tried streaming a lot with 4G and it's not more stable than 3G when you are static. I can even stream AAC320 streams under 3G without huge issues. For this usage, using 4G will draw more battery for almost no value. But, when I am walking around, it looks like that switching antenna for 3G is pretty slow and sometimes it cut (even with a buffer of 30 seconds) and lose network a bit of time when the phone is in the pocket. 4G seems to provide some more reliability over 3G at the cost of higher power draw, but 3G is far from unstable. The best choice is probably to use always 4G and have a powerbank to charge the phone if necessary :)
* For web browsing, 3G is enough with Opera Mini and sites are still loading fairly fast
* For tuberepair, 4G load videos faster. I recommend enabling 4G if you are going to binge watch streaming videos or downloading any huge file.
* For google maps version 4.3, 3G is enough for quick checking a thing but 4G will load photos and tiles almost instanteously just like when you are connected on wi-fi. It's not so much better to deserves switching to 4G in my opinion.
* For downloading apps on Veteris or in the App Store on the go and tinkering things by downloading things, 4G worth to be enabled.
* Deezer is the last music streaming service that still works on iOS 6, but I do not have any suscription. Using 4G with it will probably play songs 2x faster, but I know that 3G is very reliable for compressed music streaming web-radios (with TuneIn) so it should also be enough for Deezer. By using 4G for music streaming on the go, you will draw your battery much faster by not getting things faster enough to really justify it. Streaming audio is not like radio streaming, since you do not need a perfectly reliable connection which makes using 3G even more relevant in this case.
* And that's about it. It's difficult to find usages with Internet on iOS 6 since web browsing is difficult and many apps are not working anymore. I tried Alien Blue but it's mostly broken on many posts (because image formats ?) even with all of the patches.

Original source where I found the info, thanks to nico7775 who shared pretty clearly what to do : [https://web.archive.org/web/20140401124518/http://forum-iphoneaddict.fr/topic6580.html=](https://web.archive.org/web/20140401124518/http://forum-iphoneaddict.fr/topic6580.html=) and thanks [archive.org](http://archive.org) to exist to save that kind of precious info about how a device can work.

I hope this guide helped you, thanks for reading ! I had much trouble finding info about all of this but the process is pretty easy when you know what to do. Feel free to share your Speedtests (you can download Speedtest from Veteris). I personnally get around 25ms of ping in 4G and around 25mbps at downloading speed : it's very fast, I love it ! :)