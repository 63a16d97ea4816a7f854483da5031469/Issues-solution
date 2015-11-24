##Xcode: Not on any development teams


http://stackoverflow.com/questions/16296617/xcode-not-on-any-development-teams



In Xcode > Preferences > Accounts, try deleting - the selected (problem) account and then adding + again. This quickly fixed the issue for me.

Background: I'm in both Mac & iOS Developer Programs. Unannounced, the Mac Developer side was no longer provisioned. Looking at Accounts, showed only iOS program signing identities and provisioning profiles. The above steps restored Xcode and my Mac apps.