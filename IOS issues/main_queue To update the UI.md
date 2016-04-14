#main_queue To update the UI


http://stackoverflow.com/questions/28302019/getting-a-this-application-is-modifying-the-autolayout-engine-error

Objective-C Version
dispatch_async(dispatch_get_main_queue(), ^{
    // code here
});


