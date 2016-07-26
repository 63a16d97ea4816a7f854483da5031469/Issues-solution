#Can I delete data from iOS DeviceSupport?

The ~/Library/Developer/Xcode/iOS DeviceSupport folder is basically only needed to symbolicate crash logs.

You could completely purge the entire folder. Of course the next time you connect one of your devices, Xcode would redownload the symbol data from the device.

I clean out that folder once a year or so by deleting folders for versions of iOS I no longer support or expect to ever have to symbolicate a crash log for.

http://stackoverflow.com/questions/29930198/can-i-delete-data-from-ios-devicesupport