# MacOS (Sequoia / Sonoma / Ventura / Monterey / Big Sur) USB Installer

This is a small how-to showing how to create a MacOS USB Installer and why you should do this.

![alt test](/Pictures/USB-STICK-Sonoma-Sequoia.png)


# Why creating a USB installer:

There are mainly 3 reasons I can think of to have a USB installer prepared:
-	Have a USB-stick ready (with your pre-made EFI) to install MacOS on a fresh system.
-	Have a USB-stick ready (with your pre-made EFI) to boot your current Hackintosh from, in case your Hackintosh EFI is messed-up somehow, and/or to perform recovery tasks if required.
-	Have a USB-stick ready (with your pre-made EFI) to boot your current genuine Mac and/or to perform recovery tasks if required.


# How to Create the USB Installer:

You need:

-	1 USB stick. I recommend a 32GB stick. You can get them very cheap over here: 
https://www.aliexpress.com/item/4000495003631.html?spm=a2g0o.productlist.0.0.4aa64b6akYvBql&algo_pvid=0d8314eb-bf69-4d98-ab9f-6c4cd2230651&algo_expid=0d8314eb-bf69-4d98-ab9f-6c4cd2230651-1&btsid=2100bdd716170225997251459e7502&ws_ab_test=searchweb0_0,searchweb201602_,searchweb201603_
-	A Mac (Hackintosh already or a genuine Mac) with a USB port
-	A little bit of time and patience

1a.	Download MacOS (Sequoia / Sonoma / Ventura / Monterey / Big Sur) in the AppStore on your current Mac:
Download it and wait. It’s approx. 13 GB so it can take a while depending on your internet connection.

1b. Alternatively you can use Mist. This tool downloads the desired OS straight from Apple's server.
https://github.com/ninxsoft/Mist

![alt test](/Pictures/2023-10-31_08-22-29.png)

1c. Alternatively you can use GibMacOS. This tool downloads the desired OS straight from Apple's server.
https://github.com/corpnewt/gibMacOS

- Download the files from Github.
- On a Mac, use ```gibMacOS.command```
- Download the desired OS.
- Go to folder ```macOS Downloads``` and hit ```InstallAssistant.pkg```. This will copy the OS Installer to your ```Applications```. folder.

1d. Alternatively you can download the latest macOS version here. It will be downloaded straight from Apple's server. 
https://mrmacintosh.com/macos-sonoma-full-installer-database-download-directly-from-apple/
- Go to folder ```macOS Downloads``` and hit ```InstallAssistant.pkg```. This will copy the OS Installer to your ```Applications```. folder.

![alt test](/Pictures/2023-07-04_08-17-41.png)

After it’s been downloaded you will see the following screen, but you need to close it. Don’t worry, your download can still be found in your ```Applications``` folder as ```Install MacOS XXXXX.app```.

![alt test](/Pictures/2023-07-04_08-52-13.png)


2.	Format your USB stick, using the ```Disk Utility``` app, as follows:
- 2a. Name it ```USB```
- 2b. Format as ```Mac OS Extended (journaled)```
- 2c. Choose ```GUID Partition Map``` scheme

![alt test](/Pictures/usbformat.png)

Your USB should now appear as ```USB``` in Finder. 

3.	Open the ```Terminal``` app and copy and paste one of the following in the Terminal window, depending on which MacOS version you will install:

# Big Sur (final):
```sudo /Applications/Install\ macOS\ Big\ Sur.app/Contents/Resources/createinstallmedia --volume /Volumes/USB --nointeraction --downloadassets```

# Monterey:
Beta: 
```sudo /Applications/Install\ macOS\ Monterey\ beta.app/Contents/Resources/createinstallmedia --volume /Volumes/USB —nointeraction —downloadassets```

Final:
```sudo /Applications/Install\ macOS\ Monterey.app/Contents/Resources/createinstallmedia --volume /Volumes/USB —nointeraction —downloadassets```

# Ventura:
Beta:
```sudo /Applications/Install\ macOS\ 13\ beta.app/Contents/Resources/createinstallmedia --volume /Volumes/USB —nointeraction —downloadassets```
or
```sudo /Applications/Install\ macOS\ Ventura\ beta.app/Contents/Resources/createinstallmedia --volume /Volumes/USB —nointeraction —downloadassets```

Final:
```sudo /Applications/Install\ macOS\ Ventura.app/Contents/Resources/createinstallmedia --volume /Volumes/USB —nointeraction —downloadassets```


# Sonoma:
Beta 1:
```sudo /Applications/Install\ macOS\ 14\ beta.app/Contents/Resources/createinstallmedia --volume /Volumes/USB —nointeraction —downloadassets```

Beta 2:
```sudo /Applications/Install\ macOS\ Sonoma\ beta.app/Contents/Resources/createinstallmedia --volume /Volumes/USB —nointeraction —downloadassets```

Final:
```sudo /Applications/Install\ macOS\ Sonoma.app/Contents/Resources/createinstallmedia --volume /Volumes/USB —nointeraction —downloadassets```

# Sequoia: 

Beta:
```sudo /Applications/Install\ macOS\ Sequoia\ Beta.app/Contents/Resources/createinstallmedia --volume /Volumes/USB —nointeraction —downloadassets```

Final:
```sudo /Applications/Install\ macOS\ Sequoia.app/Contents/Resources/createinstallmedia --volume /Volumes/USB —nointeraction —downloadassets```


You will then see the percentages for formatting, installing it on the USB, etc. Wait till it’s finished. This can take some time! It usually takes an hour and a bit more on my system.

![alt test](/Pictures/2023-07-04_08-15-44.png)
![alt test](/Pictures/2023-07-04_08-16-04.png)
![alt test](/Pictures/2023-07-04_08-18-27.png)
![alt test](/Pictures/2023-07-04_08-18-37.png)
![alt test](/Pictures/2023-07-04_08-29-36.png)
![alt test](/Pictures/2023-07-04_08-30-40.png)
![alt test](/Pictures/2023-07-04_08-30-52.png)
![alt test](/Pictures/2023-07-04_08-31-05.png)
![alt test](/Pictures/2023-07-04_08-31-05.png)
![alt test](/Pictures/2023-07-04_08-32-18.png)

If it fails at a certain point, keep trying by starting from step 2 again. 

4.	Now, the only remaining thing is to copy your pre-made EFI folder to the EFI partition of your USB stick. So, mount the EFI partition with e.g. OpenCore Configurator (go to Tools -> Mount EFI) and then copy your pre-made EFI folder to the empty EFI partition. 

# Enjoy! 
Once you boot your system, and start-up from the USB stick (using F12 or Del key), you'll have a way to boot your system from or install a new Hackintosh system with. 
