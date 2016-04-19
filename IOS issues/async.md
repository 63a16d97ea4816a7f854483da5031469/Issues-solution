#async

http://stackoverflow.com/questions/2708776/async-call-objective-c-iphone

dispatch_async(dispatch_get_global_queue(DISPATCH_QUEUE_PRIORITY_DEFAULT, 0), ^{
    // No explicit autorelease pool needed here.
    // The code runs in background, not strangling
    // the main run loop.
    [self doSomeLongOperation];
    dispatch_sync(dispatch_get_main_queue(), ^{
        // This will be called on the main thread, so that
        // you can update the UI, for example.
        [self longOperationDone];
    });
});