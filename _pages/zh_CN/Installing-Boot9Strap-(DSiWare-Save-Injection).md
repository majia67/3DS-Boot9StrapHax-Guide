---
title: "Installing boot9strap (DSiWare Save Injection)" #
lang: en
permalink: /installing-boot9strap-(dsiware-save-injection).html
---

Note that, on some versions of Luma3DS, the Luma3DS chainloader menu is only displayed if there is more than one payload detected. If there is only one payload detected, holding (Start) on boot will directly launch GodMode9.
{: .notice--info}

To use the [magnet](https://en.wikipedia.org/wiki/Magnet_URI_scheme) links on this page, you will need a torrent client like [Deluge](http://dev.deluge-torrent.org/wiki/Download)
{: .notice--success}

Before proceeding, ensure you have read all of the notices and warnings on [Installing boot9strap (DSiWare)](installing-boot9strap-(dsiware))
{: .notice--danger}

If you do not use the correct `.firm` corresponding to the target 3DS, you will BRICK! Ensure you download and use the correct one!
{: .notice--danger}

#### What you need

* Two 3DS systems
  + **The source 3DS**: the 3DS running some kind of custom firmware (such as boot9strap or arm9loaderhax) *on the latest version*
  + **The target 3DS**: the 3DS on stock firmware *on 11.4.0*
* Already own one of the following exploitable DSiWare games (a pirated copy of the game will **not** work) on **the source 3DS**
  + **Fieldrunners**
  + **Legends of Exidia**
  + **Guitar Rock Tour**  
  + **The Legend of Zelda: Four Swords**  
* The latest release of [3ds_dsiwarehax_installer](https://github.com/yellows8/3ds_dsiwarehax_installer/releases)
* The latest release of [GodMode9](https://github.com/d0k3/GodMode9/releases/latest)
* The latest release of [b9sTool](https://github.com/Plailect/b9sTool/releases/latest)
* The latest release of [boot9strap](https://github.com/SciresM/boot9strap/releases/latest)
* The Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)
* The 11.4.0 `.firm` corresponding to **the target 3DS**
  + [`2.54-0_11.4_OLD.firm`](magnet:?xt=urn:btih:0dd89d42ad711f770da899af05ee162ede0d0070&dn=2.54-0_11.4_OLD.firm&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
  + [`2.54-0_11.4_NEW.firm`](magnet:?xt=urn:btih:3b59dd43eec3edb133555f58d1180bfb196acbb4&dn=2.54-0_11.4_NEW.firm&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)

#### Instructions

##### Section I - Prep Work

Use a [save manager](https://github.com/J-D-K/JKSM/releases/latest) to backup any saves you care about on *the target 3DS* (it will be formatted!)
{: .notice--warning}

1. Copy `GodMode9.firm` (or `GodMode9.bin` for arm9loaderhax users) from the GodMode9 `.zip` to the `/luma/payloads` folder on **the source 3DS**'s SD card
1. Copy the relevant `public.sav` from the `/dsiware/(8 Character ID)/` folder in the 3ds_dsiwarehax_installer `.zip` to the root of **the source 3DS**'s SD card
  + **Fieldrunners USA Region**: `4b464445`
  + **Fieldrunners EUR Region**: `4b464456`
  + **Legends of Exidia USA Region**: `4b4c4545`
  + **Legends of Exidia EUR Region**: `4b4c4556`
  + **Legends of Exidia JPN Region**: `4b4c454a`
  + **Guitar Rock Tour EUR Region**: `4b475256`
  + **Guitar Rock Tour USA Region**: `4b475245`
  + **The Legend of Zelda: Four Swords EUR Region**: `4b513956`   
  + **The Legend of Zelda: Four Swords USA Region**: `4b513945`  
1. Reinsert **the source 3DS**'s SD card
1. Boot **the source 3DS** while holding (Start) to launch the Luma3DS chainloader menu
1. Launch GodMode9 by pressing (A)
1. Press (Home) to bring up the action menu
1. Select "More..."
1. Select "Backup NAND"
1. Press (A) to continue
1. Hold (R) and press (B) at the same time to eject your SD card
1. Put **the target 3DS**'s SD card into your computer
1. **Backup every file on both 3DS's SD cards to two separate folders on your computer (keep track of which is which)!**
1. Reinsert each SD card back into their corresponding 3DS
1. Press (Start) on **the source 3DS** to reboot

##### Section II - Installing the Save

1. Boot **the source 3DS** while holding (Start) to launch the Luma3DS chainloader menu
1. Launch GodMode9 by pressing (A)
1. Navigate to `SDCARD`
1. Press (Y) on `public.sav` to copy it
1. Press (B) to get back to the main menu
1. Navigate to `SYSNAND TWLN` -> `title` -> `00030004`
1. Navigate to the folder for your game and region:
  + **Fieldrunners USA Region**: `4b464445`
  + **Fieldrunners EUR Region**: `4b464456`
  + **Legends of Exidia USA Region**: `4b4c4545`
  + **Legends of Exidia EUR Region**: `4b4c4556`
  + **Legends of Exidia JPN Region**: `4b4c454a`
  + **Guitar Rock Tour EUR Region**: `4b475256`
  + **Guitar Rock Tour USA Region**: `4b475245`
  + **The Legend of Zelda: Four Swords EUR Region**: `4b513956`   
  + **The Legend of Zelda: Four Swords USA Region**: `4b513945`   
1. Navigate to the `data` folder
1. Press (X) on the existing `public.sav` to delete it
1. Input the key combo given to unlock SysNAND (lvl1) writing
1. Press (A) to continue
1. Press (Y) to paste `public.sav`
1. Select "Copy path(s)"
1. Press (Start) to reboot **the source 3DS**
1. Launch your DSiWare game on **the source 3DS**
1. Test if the save is functional
  + **Fieldrunners**: Touch the 'Scores' button at the main menu
  + **Legends of Exidia**: After pressing (A) or (Start) at the two title screens, select the first save slot and press continue
  + **Guitar Rock Tour**: Scroll down and go to High-Scores -> Drums -> Easy    
  + **The Legend of Zelda: Four Swords**: Just start the game
  + If your game has an error about `boot.nds` or a white screen, **then the exploit has been successful**
  + If your game behaves normally and does not give you this error, then you should stop and figure out what went wrong
  + If you get a black screen, [follow this troubleshooting guide](troubleshooting#twl_broken)

##### Section III - System Transfer

1. **Backup every file on both 3DS's SD cards to two separate folders on your computer (keep track of which is which)!**
1. Reinsert each SD card back into their corresponding 3DS
1. If **the target 3DS** has a Nintendo Network ID on it, you must format the device using System Settings:
  + Go to the last page of "Other Settings" and select "Format System Memory", then follow all instructions
1. Read the following:
  + Your CFW 3DS = the source 3DS = "Source System"
  + Your Stock 3DS = the target 3DS = "Target System"
  + **Move DSiWare titles if prompted!**
  + Do **NOT** delete the source system's SD card contents if prompted
  + Make sure neither device's battery dies during the transfer
  + 2DS/Old 3DS (source) to New 3DS (target) only - if asked which method you wish to use to transfer the SD card data:
    + **Do NOT** choose the "Low-Capacity microSD Card Transfer" or minimal option (option 2), it will only transfer tickets and likely will not transfer the DSiWare save.
    + Fast Method: If you have the ability to move the data from the SD card (source) to the microSD card (target), when prompted use the "PC-Based Transfer" option (option 3).
    + Slowest Method: If you don't have the ability to move the data on a PC use the **full** "Wireless Transfer" option (option 1).
1. Go to [this link](http://en-americas-support.nintendo.com/app/answers/detail/a_id/227/) and follow Nintendo's official instructions for System Transferring from one system to another while keeping in mind what you just read

##### Section IV - Restoring the source 3DS

1. On **the source 3DS**, complete initial setup
1. Do one of the following
    + Do the rest of the sections and then the full guide on **the target 3DS**, then wait one week, then System Transfer from **the target 3DS** back to **the source 3DS** *(remember you cannot transfer back from a New 3DS to an Old 3DS)*
    + Call Nintendo and tell them you no longer have access to the device that your NNID is linked to (which is **the target 3DS** in this case), and would like it linked to a different device (which is **the source 3DS** in this case)
    + You can also just [remove the NNID](https://3ds.guide/troubleshooting#rm_nnid) from **the source 3DS** if you'd prefer it remain on **the target 3DS**
1. Reboot **the source 3DS** while holding (Start) to launch the Luma3DS chainloader menu
1. Launch GodMode9 by pressing (A)
1. Navigate to `[0:] SDCARD`
1. Press (A) on your NAND `.bin` to select it, then select "NAND image options...", then select "Restore SysNAND (safe)"
1. Press (A) to unlock SysNAND overwriting, then input the key combo given
  + This will not overwrite your boot9strap installation
1. Input the key combo given to unlock SysNAND (lvl1) writing
  + This process will take some time
1. Once it has completed, press (A) to continue
1. Press (Start) to reboot **the source 3DS**

##### Section V - Backing up the target 3DS's FIRM

1. Copy `boot.nds` to the root of **the target 3DS**'s SD card
1. Create a folder named `boot9strap` on the root of **the target 3DS**'s SD card
1. Copy the 11.4.0 `.firm` corresponding to **the target 3DS** to the `boot9strap` folder on the root of **the target 3DS**'s SD card
1. Copy `boot9strap.firm` from the boot9strap `.zip` to the `/boot9strap/` folder on your SD card
1. Launch your DSiWare game on **the target 3DS**
1. Launch b9sTool using your DSiWare game
  + **Fieldrunners**: Touch the 'Scores' button at the main menu
  + **Legends of Exidia**: After pressing (A) or (Start) at the two title screens, select the first save slot and press continue
  + **Guitar Rock Tour**: Scroll down and go to High-Scores -> Drums -> Easy
  + **The Legend of Zelda: Four Swords**: Just start the game
  + If your game does not have the hacked save file installed, [follow this troubleshooting guide](troubleshooting#ts_dsiware)
1. Select "Dump F0F1" to backup **the target 3DS**'s FIRM
1. Make note of the FIRM backup's location
1. Exit b9sTool
  + You may have to force power off by holding the power button
1. Put your SD card in your computer, then copy `F0F1_N3DS.bin` or `F0F1_O3DS.bin` (depending on your device) to a safe location; make backups in multiple locations; this backup will save you from a brick if anything goes wrong

##### Section VI - Flashing the target 3DS's FIRM

**Do NOT use b9sTool on a device that already has arm9loaderhax installed or you will BRICK!**
{: .notice--danger}

1. Launch your DSiWare game on **the target 3DS**
1. Launch b9sTool using your DSiWare game
  + **Fieldrunners**: Touch the 'Scores' button at the main menu
  + **Legends of Exidia**: After pressing (A) or (Start) at the two title screens, select the first save slot and press continue
  + **Guitar Rock Tour**: Scroll down and go to High-Scores -> Drums -> Easy
  + **The Legend of Zelda: Four Swords**: Just start the game
1. Select "Install boot9strap" and confirm
1. Exit b9sTool, then power off your device
  + You may have to force power off by holding the power button
1. Your device will boot into boot9strap, then shutdown automatically because it does not yet have a payload to launch
  + Your device will not boot until you continue with the next page's instructions; do not panic, this is normal

___

Continue to [Finalizing Setup](finalizing-setup)
{: .notice--primary}
