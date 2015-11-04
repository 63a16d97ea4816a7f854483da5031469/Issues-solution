# Android build command line:

How to package the apk in Android studio:


http://developer.android.com/tools/building/building-cmdline.html

**./gradlew :mcdonalds_sg_stg:assembleDebug**

chmod 777 gradlew       ====> give 777 privilege to this file.

$ chmod +x gradlew
$ ./gradlew assembleDebug


find ~/Documents/Android_projects/ -name "*.apk"

 
APK:

Android_projects//......../build/outputs/apk/......-debug.apk

ARC welder:

https://chrome.google.com/webstore/detail/arc-welder/emfinbmielocnlhgmfkkmkngdoccbadn


 

Android build by using GUI:

According to Android: Build Unsigned APK with Gradle you can simply build your application with gradle. In order to do that:

click on the drop down menu on the toolbar at the top (usually with android icon and name of your application)

> * -select Edit configurations
> * -click plus sign at top left corner
> * -select Gradle
> * -choose your module as Gradle project
> * -in Tasks: enter assemble
> * -press OK
> * -press play
> * After that you should find your unsigned 'apk' in directory ProjectName\app\build\outputs\apk



# Android build issues

I was facing the same issue "Error:Failed to capture snapshot of output files for task".

I saw further in Gradle Console for the specifics and it read as below:

Failed to capture snapshot of output files for task 'prepareComAndroidSupportAppcompatV72103Library' during up-to-date check.

Could not remove entry '/Users/..../.../.../..../build/intermediates/exploded-aar/com.android.support/appcompat-v7/21.0.3' from cache outputFileStates.bin (/Users/..../..../..../.gradle/2.2.1/taskArtifacts/outputFileStates.bin).

> **I resolved it by deleting the outputFileStates.bin file from the terminal and allowed Gradle to recreate it.**



#Transfer File to Android phone when using Mac computer

Need to use Android File Transfer

If you’d rather not use Wi-Fi to transfer files, then consider Android File Transfer, a simple wire-based file-transfer program. Install the application to your Mac desktop or laptop (running Mac OS X 10.5 or later), and connect it to your phone using the charger’s USB cable. When it’s ready, your phone will appear as a drive on your computer.

Follow these steps to start transferring files:

Download Android File Transfer to your computer.
Remove the USB wall charger adapter from your phone charger, so that you have just the USB cable.
Connect the phone to your computer’s USB port with the charging cable.
Open Mac Finder.
Look for the Android File Transfer on the list of drives.
Double click the Android drive icon.
A file will open with a complete list of applications. To open or view the files, simply drag them to your desktop, and then move them around as needed. Import videos to iMovie or pictures to iPhoto.

You can also use your phone as an external hard drive if you want to transfer files between, say, your work computer and your home computer. Of course, the receiving computer would also need to have an app like AirDroid or Android File Transfer installed.

Now you know how to connect an Android phone to a Mac. Easy peasy.

Android file transfer:
> https://www.android.com/filetransfer/#tips

Download the app.
Open androidfiletransfer.dmg.
Drag Android File Transfer to Applications.
Use the USB cable that came with your Android device and connect it to your Mac.
Double click Android File Transfer.
Browse the files and folders on your Android device and copy files up to 4GB.


In Android phone, there is an app called:   
**ES File Explorer**  
This app is very useful for managing files in Android Phone.






