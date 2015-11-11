##Missing from working copy

Xcode: issue “file xxx.png is missing from working copy” at project building
or
Xcode: issue “file xxx.h is missing from working copy” at project building

In XCode -> SoureControl:

Update + Update All.

In my case, Xcode had somehow found old .svn directories that referenced the missing files. After did the operation above, everything is fine.