---
title: "Installing boot9strap (2xrsa)"
---

To use the [magnet](https://en.wikipedia.org/wiki/Magnet_URI_scheme) links on this page, you will need a torrent client like [Deluge](http://dev.deluge-torrent.org/wiki/Download)
{: .notice--success}

#### What you need

* The latest release of [SafeB9SInstaller](https://github.com/d0k3/SafeB9SInstaller/releases/latest)
* The latest release of [boot9strap](https://github.com/SciresM/boot9strap/releases/latest) *(standard boot9strap; not the `dev` file)*
* The Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)

#### Instructions

##### Section I - Prep Work

1. Power off your device
1. Insert your SD card into your computer
1. Copy _the contents of_ the `starter` folder in `starter.zip` to the root of your SD card
1. Create a folder named `boot9strap` on the root of your SD card
1. Copy `boot9strap.firm` and `boot9strap.firm.sha` from the boot9strap `.zip` to the `/boot9strap/` folder on your SD card
1. Copy `arm9.bin` and `arm11.bin` from the SafeB9SInstaller `.zip` to the root of your SD card
1. Reinsert your SD card into your device
1. Power on your device

##### Section II - Launching SafeB9SInstaller

1. Launch the browser and go to the following URL on your device
  + `http://2xrsa.3ds.guide`
  + If you are on a 2DS or New 3DS and Wireless Communication is off, you can re-enable the wireless by removing the battery and unplugging the charger for several seconds then booting back up
  + If you get the error "This service is not available in your region", use the System Settings to set your device's country to match the NAND region you installed with 2.1.0 CTRTransfer
  + If you forgot to disable parental controls before CTRTransfering or otherwise cannot access wireless settings, note that the device will autoconnect to any network named `attwifi` with no password
  + If you get another error, [follow this troubleshooting guide](troubleshooting#ts_browser)
1. If the exploit was successful, you will have booted into SafeB9SInstaller

##### Section III - Installing boot9strap

1. Wait for all safety checks to complete
1. When prompted, input the key combo given to install boot9strap
1. Once it has completed, press (A) to reboot your device
1. Your device will boot into boot9strap, then shutdown automatically because it does not yet have a payload to launch
  + Your device will not boot until you continue with the next page's instructions; do not panic, this is normal

___

Note that *New 3DS* users who ended up on 2.1.0 after a CTRTransfer *must* [restore their NAND backup](godmode9-usage#nand_restore) between "Section II - Configuring Luma3DS" and "Section III - Updating the System" of [Finalizing Setup](finalizing-setup).
{: .notice--danger}

Continue to [Finalizing Setup](finalizing-setup)
{: .notice--primary}
