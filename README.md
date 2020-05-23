

![](https://i.dell.com/das/xa.ashx/global-site-design%20WEB/e72e3a10-12a0-adce-6a2f-68869c8493e4/1/OriginalJPG?id=Dell/Product_Images/Dell_Client_Products/Workstations/Mobile_Workstations/Precision/Precision_m4800/global_spi/laptop-precision-m4800-left-generic-hero-504x350-ng.psd)

# Dell Precision Mx800 Hackintosh Project

This repo is a collection of information, dumps, kexts and everything needed to hackintosh the Dell Precision Mx800 line of portable workstations (namely the 4800 and 6800).

While this was started with the idea of being M4800-only, it's bigger brother shares many of the same traits, only in a bigger package so most information available for the M4800 will apply to the M6800 too.

Specs rundown:

- 15.6" (M4800) or 17" (M6800)
- Motherboard models: W7R2C/THP1N/T3YTY (LVDS) & C3V2K/8KWV8/WNW0H/77KCT (eDP)
- 4th Generation Core i5 or i7 CPU (Not soldered, hence upgradeable)
- Up to 32GB of DDR3L RAM
- Intel (*) HD 4x00 Series iGPU (HD 4600) + nVidia Quadro / AMD FirePro dGPU (Upgradeable MXM Type A on M4800 and Type B on M6800)
- Realtek ALC292 Codec
- Intel Ethernet Connection I217-LM
- Intel Dual Band Wireless AC 7260 + Bluetooth 4.0 (There's no Whitelist in this model, so it's upgradeable)
- Maximum of 3 Hard Disks (1 x SATA, 1 x mSATA, 1 x Optical Bay (which will need a 9mm SATA to ODD adapter))

Dell has released the M4800 with six (!) different motherboard revisions and three different displays. Why am I telling you this? Well it's what matters the most regarding it's hackintoshing-ability.

As you've probably noticed, there are 3 variants of LVDS and 4 variants of eDP motherboards. All the LVDS motherboards are very hackintosh-friendly and there are many instructions and success cases online, but their maximum resolution for the internal display is capped at 1920x1080. On the contrary, the eDP versions can go from Full HD to Ultra HD (aka 4K). Note that there's also a QHD+ screen available with a resolution of 3200x1200. 

Also, according to Dell, the iGPU is not capable of driving a QHD+ or UHD panel, so if you get a laptop with the QHD+ screen (like me) or the UHD screen, the iGPU will be disabled hardware-wise and you will run into trouble since macOS doesn't detect the internal eDP port and as such no image on the internal screen will show (unless you boot with nv_disable=1). External monitors connected to the HDMI and DP ports do work fine. 

As I've found a schematic for my board, I've since realized that there is no MUX from the MXM Card to the eDP Screen. I've also found out that the iGPU eDP signal goes thru a eDP to LVDS converter and then a LVDS MUX before reaching the connector, hence the only signal available at the connector is LVDS (and that's why it's not "able to drive" the QHD+\UHD screens as they're eDP).

This isn't the only laptop with a Discrete GPU only (no iGPU), other examples are the ASUS ROG G750 (which was solved [here](https://www.insanelymac.com/forum/topic/293967-solved-asus-rog-laptops-with-kepler-cards-not-detecting-dp-2-connected-lcd-display/)). I believe that the Asus G75VW, HP Zbook G1/G2 and the Dell Inspiron SE 7720 suffer from the same issue.

So if you own one of these and want to help, PR's are welcome. If you don't own one of these but you think you may be able to help, I believe we're needing someone who actually understands DSDTs and the innards of nVidia kexts under macOS.

 



