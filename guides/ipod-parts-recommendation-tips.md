# Getting iPod parts: my recommendation & tips
*Date: 13 August 2025, last edited: 13 August 2025*

Hey !

Now that I have experience repairing several iPod models, and that I used different iPods with daily usage for a while using parts that I will review there, it's time to look behind and share my experience with you.

No chat GPT AI writing, no conflict of interests & no bullshit: just someone who is willing to share human experiences with the stuff directly to the iPod community.

For things that I could not test by myself, I trust friends and got my review from them so I can recommend the products there. All products that I recommend are considered safe & good for daily intense usage of your favourite music player.

This guide will be mostly around the 5G/6G/7G iPods, and a little bit about minis/4G Mono. I don't own other iPod models at all for the moment.

# My situation
I live in France, which means imported packages have tarrifs & import fees. Take this in consideration while reading me. I share my experience and tell what I find was the best for me, but I can't talk for every individual situations with your own iPod.

Though I am convinced that my work is going to be helpful globally so people can avoid making some mistakes that I did.

# Was in early access for Patreons during 1 week
The guide required time and will make save yours. You may also save money by not buying bad parts that will take a long time to be shipped to you before you will be disappointed and need to order back new parts.

Since one week has now passed, this guide is now open sourced for everyone.

In this paper, more than **30 items** are hand-reviewed with tips when suitable.

# Storage mods: what road to follow ?
## The iFlash road
Reliable products & really relevant for 5G+ iPods. If you are not on a budget, always go this road. If you live in the US, you may want to get one from EoE to avoid tarrifs/import fees and get local support. If you live in Canada, get one from iDemiGods.

With these products, don't forget to secure the SD card inside with double-sided tape so it will not disconnect for random reasons at usage.

Note that untested products by me (like iFlash-CF/iFlash ATA) are very likely to work very well. If you don't want to get a cheap green board, get one of these. All iFlash products are just good stuff & I can blindly recommend them.

### iFlash Ribbon
https://www.iflash.xyz/store/hdd-ribbon/
Recommended: Reliable & high quality product for 5G+ iPods

### iFlash Solo
https://www.iflash.xyz/store/iflash-solo/
Recommended: Reliable & high quality product for 5G+ iPods

### iFlash Quad
Recommended: more expensive but buy this if you wanna fit the highest batteries on your iPod as it's the slimmest flashmod.

### iFlash SD-CF
https://www.iflash.xyz/store/sdcf-adapter/
Barely recommended: Suitable really mostly for iPod Minis in practice, but it's expensive. I prefer to recommend a cheap compact flash that will be more reliable. If you learn how to do proper AAC compression, you will not never more than 64 or 128GB on a monochrome iPod in my opinion.

### Tested SD card that works great
https://www.amazon.fr/dp/B0858J45S6

## The SSD NVMe 2242 road (cheap especially for high storages like 1TB)
https://fr.aliexpress.com/item/1005005225483214.html
Recommended: A very cheap M.2 2242 SD adapter. Power consumption will be pretty much comparable to the original iPod HDD, but it's a reliable way to mod your iPod. Can be tricky to install, so if your iPod show the red cross in loop you may want to clean contacts with isopren alcohol.

https://fr.aliexpress.com/item/1005008215403225.html
Recommended: Same M.2 2242 board but bundled with a working SSD + a replacement cable. Get this rather than the board alone if you are a new modder & don't have spare parts.

Don't forget to secure the board with double-sided tape so it won't disconnect at usage.

## The compact flash road
- Good for 4G + a cheap IDE 50 to CF board: https://www.amazon.fr/dp/B00S6AK592 Don't forget to secure the CF board with double-sided tapes & ensure at installation that it's not pushing against the screen (especially true for slim 4G). If you get weird electrical noises during data accesses (concerned my slim 4G but not the fat one), tape a little sheet of paper that cover the back (from the inside of the iPod) and it will be gone.
- My favourite storage mod for iPod Minis
- Good for 5G/6G/7G + a cheap ZIF1.8 to CF board: https://www.amazon.fr/dp/B00NPTXJTC

Note that some CF card models will not work with iPods for unknown reasons, so stick to models that works well.

CF cards are interesting because they provide even lower power consumption compared to SD cards, but they can't go over 256GB (limited by their norm) and the 256GB ones are stupidly expensive in general, and rares to find. Price per GB for this form factor is not competitive.

I prefer personally to use CF cards only for the Minis, and iFlash Solo or the NVMe board for the 5G+.

https://fr.aliexpress.com/item/1005005537898878.html
Cloudisk CF
Recommended: 64GB is the most competitive pricing, though 128GB can be relevant if you plan to put a lot of content on your iPod.

https://fr.aliexpress.com/item/1005006473663118.html
Kingspec CF 256GB
Recommended: Works perfect & reliably at good pricing but unfortunately it's out of stock everywhere for the moment.

https://www.amazon.fr/dp/B00NUB2TWI
Sandisk Extreme 128GB
Not recommended: Works great but the price per GB is just the insane.

https://fr.aliexpress.com/item/1005007469796260.html
This is a "Microdrive" Compact Flash
Not recommended: Did not work reliably with any iPod. Tested model: 256GB

### The Red CF-SD adapter
https://www.amazon.fr/dp/B0791FL6FS This one worked for me with the MBR trick. It's going to sync slower than an iFlash SD-CF or a real CF card, but playback was reliable. With them, stick to 128GB or lower; never try higher capacities. Even if you can make them "work" with more than 128GB, all your iPod will be fully corrupted as soon as you will really copy more than 128GB of data.

Avoid this cursed thing if you can, I've heared often from people that could never make them work.

# Batteries
## 2000mah slim (5G+)
https://fr.aliexpress.com/item/1005006011928847.html
Model: 44.5404.8mm thinback
Recommended: Can be paired with the NVMe adapter + a slim back. It will fit closely

## 3000mah slim (5G+)
https://fr.aliexpress.com/item/1005008716350605.html
Model: 79493.8mm Thin Back
Recommended but know what you do: Will not work with the NVMe adapter on the slim back because it will not fit. It seems like it fits on slim backs only with the iFlash Quad so be carefull with that.

## Cameron Sino CS-EC003XL (iPod Mini 2G)
https://www.amazon.fr/dp/B0922S1MGM
Recommended: high battery life & reliable. For this iPod model, don't forget to use the modded USB cable/firewire brick or Rockbox + the option ```force USB charging``` to get a reliable charging experience.

## Cameron Sino CS-IPOD4HL (Tested with 4G Mono)
https://www.amazon.fr/dp/B0922SPX4G
Recommended: high battery life & reliable. For this iPod model, don't forget to use the modded USB cable/firewire brick or Rockbox + the option ```force USB charging``` to get a reliable charging experience.


# Other parts

## Modded USB cable (for 3G+)
https://fr.aliexpress.com/item/1005004676081336.html
Recommended: A must have ! The iPod believes that it is firewire-charging. This can can help reviving & restoring older iPods, and I recommend it even with newer iPods because they will charge much faster using it.
I noticed also by pairing this cable with the first ```Apple Universal Dock``` (which is the only one compatible with firewire charging) that there's less hearable electrical noises compared to using the real firewire brick with an Apple firewire cable.

## Front cases (metal for 6G+)
https://fr.aliexpress.com/item/1005006984358050.html
Recommended: High quality, feels like OEM. It does not scratch easily especially on the screen. Be carefull when installing to remove the protective sticker without putting dust under the screen. Dust under the screen lens cannot be really removed without making it worse. I recommend buying 2 of these so you can put the other one if you fail installation of the first.

## Front cases (for 5G Video)
Transparent from here https://fr.aliexpress.com/item/1005004655859764.html and here https://fr.aliexpress.com/item/1005006984328148.html
Barely recommended: I can speak only for the transparent front case, but it scratched very easily and fast.
If you have the opportunity, on a 5G, change:
- The metal frame
- The clickwheel for a 6G+
Then get a metal front shell: your iPod 5G will feel more Premium and durable like this.

## Back cases
https://fr.aliexpress.com/item/1005006671803314.html
Recommended: Very good quality, feels OEM

From iDemiGods: bought a fat case
Not Recommended: Feels cheap compared to OEM

## Replacement screen (iPod Video 5G)
https://www.idemigods.com/5th_Generation_iPod_Video_LCD_Color_Display_Screen_p/5g_lcdvd.htm
Not recommended: Colors looks really bad & washed out. It's usable but disappointing compared to an OEM screen

## Replacement screen (iPod Classic 6G+)
https://fr.aliexpress.com/item/1005004755420259.html
Recommended: Very good replacement, feels like OEM

## Replacement jack port
https://fr.aliexpress.com/item/1005006984290270.html
Recommended: Used this replacement with daily intensive usage with my IEM. Did not break, feels like OEM.

From iDemiGods:
Not Recommended: Used a replacement with daily usage and the plastic broke after around 1 month of usage pretty quickly. Maybe it was just bad luck ?

## Dock plastic bezel (slim iPods)
https://fr.aliexpress.com/item/1005006137179932.html
Recommended: Great build quality, feels OEM

## Replacement screws pack
https://fr.aliexpress.com/item/1005004571411340.html
Recommended: If you need more screws & replacements, this will get you covered.

## Replacement Clickwheel for 6G+
https://fr.aliexpress.com/item/1005007021562024.html
Recommended: Decent quality, but not as good as OEM. For some reason, at unlocking, I need to press a key or relock/unlock to be able to register scrollings/touch inputs (it's like it need some annoying kind of manual re-calibration). Also keep in mind that they don't give you a middle button for the price.

I recommended it because I never tested any other alternative and it worked decently enough to be enjoyable, but I assume there's probably something better somewhere in the market.
