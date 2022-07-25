# MacOS (Ventura / Monterey / Big Sur) USB Installer

This is a small how-to showing how to create a MacOS USB Installer and why you should do this.

![alt test](/Pictures/USB-STICK-VENT-MONT.png)

# Why creating a USB installer:

There are mainly 3 reasons I can think of to have a USB installer prepared:
-	Have a USB-stick ready (with your pre-made EFI) to install MacOS on a fresh system.
-	Have a USB-stick ready (with your pre-made EFI) to boot your current hackintosh from, in case your hackintosh EFI is messed-up somehow, and/or to perform recovery tasks if required.
-	Have a USB-stick ready (with your pre-made EFI) to boot your current genuine Mac and/or to perform recovery tasks if required.


# How to Create the USB installer:

You need:

-	1 USB stick. I recommend a 32GB stick. You can get them very cheap over here: 
https://www.aliexpress.com/item/4000495003631.html?spm=a2g0o.productlist.0.0.4aa64b6akYvBql&algo_pvid=0d8314eb-bf69-4d98-ab9f-6c4cd2230651&algo_expid=0d8314eb-bf69-4d98-ab9f-6c4cd2230651-1&btsid=2100bdd716170225997251459e7502&ws_ab_test=searchweb0_0,searchweb201602_,searchweb201603_
-	A Mac (hackintosh already or a genuine Mac) with a USB port
-	A little bit of time and patience..

1a.	Download MacOS (Ventura / Monterey / Big Sur) in the AppStore on your current Mac:

Download it and wait. It’s approx. 13 GB so it can take a while:

![alt test](/Pictures/MontereyDownload.png)

1b. Alternatively you can use GibMacOS. This tool downloads the desired OS straight from Apple's server.
https://github.com/corpnewt/gibMacOS

- Download the files from Github.
- On a Mac, use ```gibMacOS.command```
- Download the desired OS.
- Go to folder ```macOS Downloads``` and hit ```InstallAssistant.pkg```. This will copy the OS Installer to your ```Applications```. folder.

After it’s been downloaded you will see the following screen, but you need to close it. Don’t worry, your download can still be found in your ```Applications``` folder as ```Install MacOS XXXXX.app```.

![alt test](/Pictures/MontereyInstaller.png)


2.	Format your USB stick, using the ```Disk Utility``` app, as follows:
- 2a. Name it ```USB```
- 2b. Format as ```Mac OS Extended (journaled)```
- 2c. Choose ```GUID Partition Map``` scheme

![alt test](/Pictures/usbformat.png)

Your USB should now appear as ```USB``` in Finder. 

3.	Open the ```Terminal``` app and copy and paste one of the following in the Terminal window, depending on which MacOS version you will install:

Big Sur:

```sudo /Applications/Install\ macOS\ Big\ Sur.app/Contents/Resources/createinstallmedia --volume /Volumes/USB --nointeraction --downloadassets```

Monterey (BETA):

```sudo /Applications/Install\ macOS\ Monterey\ beta.app/Contents/Resources/createinstallmedia --volume /Volumes/USB —nointeraction —downloadassets```

Monterey (any FINAL version):

```sudo /Applications/Install\ macOS\ Monterey.app/Contents/Resources/createinstallmedia --volume /Volumes/USB —nointeraction —downloadassets```

Ventura (BETA):

```sudo /Applications/Install\ macOS\ 13\ beta.app/Contents/Resources/createinstallmedia --volume /Volumes/USB —nointeraction —downloadassets```

or

```sudo /Applications/Install\ macOS\ Ventura\ beta.app/Contents/Resources/createinstallmedia --volume /Volumes/USB —nointeraction —downloadassets```


![alt test](/Pictures/4.png)


You will then see the percentages for formatting, installing it on the USB, etc. Wait till it’s finished. This can take some time! It usually takes an hour and a bit more on my system.

If it fails at a certain point, just keep trying be starting from step 2 again. 

4.	Now, the only thing that lefts remaining is to copy your pre-made EFI folder to the EFI-partition of your USB stick. So, mount the EFI-partition with e.g. OpenCore Configurator (go to Tools -> Mount EFI) and then copy your pre-made EFI folder to the empty EFI-partition. 

# Enjoy! 
Once you boot your system, and start up from the USB stick (using F12 or Del key), you'll have a way to boot your system from, or to install a new hackintosh system with. 
