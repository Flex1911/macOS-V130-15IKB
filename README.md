# Hackintosh configration for Lenovo V130-15IKB

This is a crappy (not really) config for my crappy (that's real tho) Lenovo laptop.
Based on OpenCore using ACPI hotpatch, tested with Catalina 10.15.4. 

## Retail specs:
* Intel Core i3-7020U (Kaby Lake)
* Intel HD Graphics 620
* 4GB DDR4 2400MHz Single-channel RAM
* 15.6" Full HD TN Display
* Intel Wireless-AC 3165 Wi-Fi + BT Combo
* Realtek RTL8168H Gigabit Ethernet
* ALPS AUI1657 Touchpad (Multitouch gestures only work on Windows with a proprietary driver)
* 2x USB 3.0 Ports (no EHCI since it's Kaby Lake)
* HDMI Port
* Optical Drive
* 500GB WD Blue HDD

Those specs look just ridiculous in 2020, right? Sure they do, but what else would you expect from a stripped variant of and already budget laptop (Lenovo V330-15IKB)?

Luckily this machine is *kinda* upgradable, at least in terms of RAM and storage.

## My current upgrades:
* Replaced the HDD with ADATA SU650 120GB
* Added another 4GB stick of DDR4 memory to support dual-channel
* Removed the optical drive and put an HDD with a caddy
* Added another 128GB SPCC SATA SSD in m.2 slot

That's much better. Well, at least it's comparable to Mid-2017 MacBook Air and works fine both in Windows 10 and Linux for some casual usage and **very-very** light coding. I could also put an NVMe m.2 SSD there, but I don't really see any point in that since it's essentially going to be bottlenecked by the low-end CPU.

## Why OpenCore?
My first setup with Clover on that laptop had a lot of memory-related issues I couldn't resolve without throwing away my second memory stick. It would require manual memory mapping in SMBIOS to boot the system and sleep mode instantly crashed the kernel.

I decided redoing it from scratch and thought that going with OpenCore would be a cool and fun idea since it's something new and I didn't deal with it earlier. Coincidentally or not, that fixed all my memory and sleep issues. Digging deeper into it made me realize that it's not just the lack of the memory issues what makes OpenCore better. I'm not going to explain all the advantages here since they're covered in every single article about OpenCore on the web, just going to say that it feels like a cleaner and more future-proof solution for me and I don't miss any Clover features it lacks.

## Current issues:
* No internal Wi-Fi (I use a dongle)
* Touchpad is detected as a mouse and only supports basic gestures (same on Linux, needs a custom driver)
* Card reader is not tested

## Hints:
* Laptop uses an m.2 NGFF slot and doesn't have Wi-Fi blacklist in the BIOS, so pretty much any macOS-compatible combo chip in that form-factor should work fine.
* HoRNDIS kext is included for USB tethering support.
* I use TP-Link Archer T2U Nano for Wi-Fi which works just fine with the official driver for Catalina.
