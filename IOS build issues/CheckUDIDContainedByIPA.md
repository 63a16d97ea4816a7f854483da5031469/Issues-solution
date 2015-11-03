##Is there a way to see what UDID are included in a build?

We used crashlytics to build and release a new version to testers, but one user reported that he could not be able to install the app.

He said when he was trying to install the app:
The crashlytics said: the developer needs to add this device's UDID to a build.

The following script does the job for you, searching for and pulling out UDID numbers from an archive. It does so by looking for embedded.mobileprovision files in the archive and pulling out the data from there. All you need to do is run it:

	$ listudids /path/to/build.ipa

Download the listudids app from github:
https://github.com/duttski/listudids

*************************************************

# listudids
List udids found in an IPA file, without extracting the whole archive.

Works by searching for embedded.mobileprovision file(s) and selectively extracting them and printing a sorted, unique list of UDIDs.

## install

Put the script somewhere in your PATH, or just run it directly.

## use

> `listudids /path/to/build.ipa`

## options

`-all` will show a bit of extra information about where things were found.

> `listudids /path/to/build.ipa -all`
