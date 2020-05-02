It's always astonishing what the Android community itself develops for an “old” device like the Samsung Galaxy S2 i9100.

As most should know, the Galaxy S2 was launched in May 2011. The latest firmware was based on Android 4.1.2 JellyBean and was last released in Germany for devices with Vodafone branding in August 2014. Since then, Samsung has discontinued support with newer Android versions for the Galaxy S2.

Anyone who did not discontinue Android support was and is the Android community, which not only made Android 4.4.x KitKat, Android 5.xx Lollipop, Android Marshmallow 6.xx, but also Android Nougat 7.xx. And I wouldn't be surprised if Android Oreo 8.x for the Galaxy S2 would appear soon.

Since there are obviously still enough users who own a Samsung Galaxy S2 i9100 and maybe even want to use it with a current Android version, there is now a complete guide on how to get the current Lineage 14.1 on the Galaxy S2 i9100 Version flashes or installs.

### Preliminary information:

In addition to various files that we have to download, the file system of the Galaxy S2 must also be changed. As you know, the Galaxy S2 didn't have too much memory. In particular, the memory for the system was very limited at 512 MB. For the Android versions up to KitKat, the whole thing was still sufficient. Starting with Android Lollipop, things got pretty tight because not only the Android version but also the standard Google Apps are installed in the system partition. However, since Android Marshmallow at the latest, there is no longer enough space.

Therefore, we not only have to flash Lineage OS, but also change the partition sizes beforehand. The use of a MicroSD card is definitely helpful here with the Galaxy S2 - especially after installing Lineage OS - because the "enlargement" of the system partitions means that the total memory available is smaller.

**Attention:** I am assuming with these instructions that an original Samsung firmware Android 4.1.2 is installed on the Galaxy S2 and that its data, if it is still being used, is backed up in advance. If you have already installed a Custom Rom on your Galaxy S2, you may have to do it differently, but you can inquire here in this thread.

So what do we need to install Lineage 14.1 (all files must be copied to the micro SD card that has to be inserted into the Galaxy S2):

Lineage OS https://download.lineageos.org/i9100

*Attention: at lineageos.org support for the Galaxy S2 i9100 is no longer available. I cannot say at the moment whether this will happen again in the future or whether Lineage has stopped further development.*

We have therefore downloaded the last Nightly from December 16, 2018 for download .

For further versions you have to either go via the built-in update function (to be found in the settings) or you check out the XDA forum from time to time.

Gapps (Google Apps)The Open GApps Project (ARM / Android 7.1 / desired variant - I prefer Nano to maximum Mini, because everything else on Google Apps can be installed from the Play Store)

If you want to root, you still need the SU Addon LineageOS Downloads (Version 14.1 in the ARM variant), because obviously there is no root in Lineage.

Also required for preparation:

PhilzTouch Recovery 5.15.9 Download

Lanchons IsoRec Kernel StackPath
The Gangsters TWRP StackPath

Lanchons script for changing the partitions StackPath. Goes to the folder from (currently the last change) 01/15/2017. Download the version lanchon-repit-20170115-system = 1G-data = same-sdcard = max-preload = min + wipe-i9100.zip .

We are aware that it is not exhilarating to download files from various sources. We would also like to make it completely available to you in our download base, but the modders and devs are against it and have asked not to do this.

Now we come to the preparatory work. For this we should definitely use an SD card in the Galaxy S2. First of all, the downloaded files should be copied to the SD card, because the memory of the Galaxy S2 must definitely be completely deleted during the installation.

Before we copy Lanchon's script for repairing to the SD card, we have to adjust the name of the file. The reason is that the partitioning is changed using the name of the file.

The name of the downloaded file is only the basic structure. I changed the name for my needs as follows:

lanchon-repit-20170115-system = 2G + wipe-data = 6G + wipe-sdcard = max + wipe-preload = min + wipe-i9100.zip

Explanation:

system = 2G + wipe (extends the system size to 2 GB and at the same time deletes the current content - standard would be 0.5 G = 512 MB)

data = 6G + wipe (extends the data partition to 6 GB and simultaneously deletes the current content - standard is 2 G = 2 GB)

sdcard = max + wipe (makes the rest of the built-in memory - not to be confused with an additional micro SD card - available to the system and at the same time deletes the current content - standard is = max)

preload = min + wipe (the Prelaod partition is not used with Lineage and can therefore be reduced to the smallest possible size - 8 MB - so that you have a little more space for the data partition - the default here is 0.5 G = 512 MB).

If you want, you can of course also take a smaller size. Because the size I prefer is the maximum that you should take with the Galaxy S2. Here is another example of a smaller partitioning:

lanchon-repit-20170115-system = 1.5G + wipe-data = 4G + wipe-sdcard = max + wipe-preload = min + wipe-i9100.zip. So later you would not only have about 6 GB as an internal SD card, but 8.5 GB.

Next we start the Galaxy S2 in recovery mode. To do this, press and hold the Volume Up buttons, the home button and the power button simultaneously until the Android male appears.

The whole thing should look like this: Use the volume keys to navigate to the “apply update from external storage” item and confirm with the power button. Now navigate to “Philz-cwm6 ……” and confirm with the power button. The Philz Recovery should now be loaded.Los01.jpg



Los02.jpg Los03.jpg Los04.jpg

Now navigate back to "../" and confirm. Here you have to select the item "reboot system now". After restarting the Galaxy S2, it must be switched off again and restarted in recovery mode. If your Galaxy S2 gets stuck at this point (happened during my test attempts), simply remove the battery briefly, insert it again and start in recovery mode. The recovery menu now looks very different, of course.

Los05.jpg Los06.jpg





Here we first go to the "Backup and Restore" item and select the "Custom Backup and Restore" item and then the "Custom Backup Job" item. At this point you can choose which points should be saved. I personally use the items "Backup boot", Backup recovery ", Backup system", "Backup data", Backup "Cache" and "Backup modem". Finally, on the point "Start Custom Backup Job". Now select the "Backup to External sdcard" item.

Los08.jpg Los09.jpg Los10.jpg Los11.jpg Los12.jpg Los13.jpg Los07.jpg

In a second step, we go to this "Custom Backup Job" menu again and only select the "Backup EFS" item. Here again select "Start Custom Backup Job" and "Backup to external sdcard". Unfortunately, you had to do this separately, as there is no way to back up both together with this recovery. Now that we have saved everything, we come to the next point. Goes back to the beginning via the menu item "Go Back". Here we have to select "Wipe Data / Factory Reset". On the next page, select "Wipe Data / Factory Reset again and then navigate to" Yes "and confirm. When that's done, go back to the home page.

Los14.jpg Los15.jpg





Los16.jpg Los17.jpg Los18.jpg Los19.jpg Los20.jpg


Then select the "Install Zip" item in the start menu. Here we first flash the downloaded ISO Rec Kernel, ie "kernel-Lanchon-20160406-cm-13.0-i9100.zip and then the file" recovery-the.gangster-IsoRec-TWRP-3.0.2-1-i9100-with -preload-support.zip.

To do this, select the "Choose zip from sdcard" item after "Install Zip" and first install the "kernel-Lanchon ...". In the second step, select "Choose zip from sdcard" again and select the file "recovery-the-gangster ....". After flashing these two files back to the start menu page and then restart. The Galaxy S2 should now start directly in recovery, but in the TWRP recovery that we just installed.

Los21.jpg Los22.jpg Los23.jpg Los24.jpg Los25.jpg Los26.jpg Los27.jpg Los28.jpg



Los29.jpg



Here we first go to "Select Language" and set it to German. Then it is imperative that you use the slider at "Allow changes". Then we are in the TWRP recovery menu. (During my attempts it also happened that after the first restart the TWRP recovery was set to German directly and there were no setting options.)

At this point one or the other may ask why we first install Philz Recovery to deal with this to install a TWRP recovery and we did not immediately install the TWRP recovery. This is because the IsoRec kernel had to be flashed before the TWRP recovery. Only then can the TWRP Recovery be installed, otherwise it would not work correctly.

Now comes the most important, because to be able to install Lineage OS at all, we now have to adapt the file system of the Galaxy S2.

There is also a possibility to change the partitioning via a .pit file with Odin, but I find the variant presented here with Lanchon's script much easier and above all, you can do everything via TWRP. So you can continue with Lineage and the rest immediately after changing the partition.

Since we are already in the TWRP, we now go to the point "Install". Then the storage must be selected and switched to "External Storage", because that is the Micro SD card used.

Here we should now also see the file "lanchon-repit-20170115-system = 2G + wipe-data = 6G + wipe-sdcard = max + wipe-preload = min + wipe-i9100.zip" (or the one that you yourself with other partition information). Simply tap on the file and in the next window then move the slider (confirm installation) from left to right. For many, an error should now arise because something did not fit when mounting the sdcard1. This is not a problem, because the installation file has now been automatically saved to a tmp folder in the system partition.

Los30.jpg Los31.jpg Los32.jpg Los33.jpg Los35.jpg



For this we go back one step using the lower screen buttons so that we are back in the file overview of the Micro SD card. Here we click on the item "Parent folder" above, where we are in the system folder. Please scroll down here, to the folder "tmp" and tap it once. Now we should see our installation script again. We also tap this briefly. Now confirm the installation again and the script should run without an error message. If it says "Done" underneath, we can - but we do not have to - go briefly to "Clear Cache / Dalvik". Then we are back in the system folder. Here we scroll to the point "sdcard1", tap on it and are back in the file overview with our copied files.

Los36.jpg Los38.jpg Los39.jpg Los40.jpg Los41.jpg Los42.jpg



Los43.jpg Los44.jpg

Here we first tap on “lineage_14.1… .. * zip. In the next window, please select the item "Add more zips". Now we tap on the "open_gapps ... zip".

If you also want to use root access, you must now select "Add more zips" again and then select the "addonsu ... zip" file.

The last thing to do is to press "Confirm installation" again to flash the selected files. After all files have been flashed, the message "Done" appears again. Here you should definitely select the item "Clear cache / Dalvik". Only then use the "Restart system" field. Lineage OS 14.1 should now start. The start-up process takes a little time the first time. Finally, set up the system completely.

Los45.jpg Los46.jpg Los48.jpg Los49.jpg Los50.jpg Los51.jpg Los52.jpg Los53.jpg



Los54.jpg



Los55.jpg

**Note:** Everyone should be aware that Lineage OS is still being developed for the Galaxy S2 i9100. In each version there may be “errors” or functions not included. Via the built-in update function of Lineage OS - can be found under Settings / Via the phone / Lineage OS updates you can download and flash the current version at any time. I cannot say whether it is also possible to downgrade directly or whether you have to download the last satisfactory version yourself and then flash it again using TWRP, because I have not yet tested this.

And another note: To activate Root, you first have to go to Settings / Via the phone to the point "Build number" and tap there 7 times so that the developer options are activated. You will find the "Developer options" item in the settings directly under the "About the phone" item. Now open the developer options and scroll down to the "Root access" item. Tap once and select the one you want. I have activated "Apps and ADB".

And if you are already there, you can also activate "Android Debugging" (USB debugging).

Incidentally, I would advise everyone to use the micro SD card in the system as "internal storage" and not as mobile storage (to use the SD card in other devices or card readers). Because only in this way is there enough memory in the Galaxy S2 to be able to use it really well. But be careful, back up the files that are on the SD card. Because when connecting to the internal memory, the data on it should be deleted.


​



And here is a video that shows the whole thing again: