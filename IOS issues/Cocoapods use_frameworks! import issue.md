#Cocoapods use_frameworks! import issue

http://stackoverflow.com/questions/34429793/cocoapods-use-frameworks-import-issue

Issue:  
I want to use some Swift pods in my Objective-C app, so I need to use frameworks instead of static libraries. But enabling use_frameworks! in my Podfile causes tones of #import errors.

Solution:

I have finally figured out it! The problem was fixed by removing Pods.framework from Link Binary With Libraries and adding them again manually.