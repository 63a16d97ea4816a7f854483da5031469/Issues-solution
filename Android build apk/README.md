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
