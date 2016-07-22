# Call appDelegate's method in another viewcontroller

        AppDelegate *appDelegate=(AppDelegate*)[[UIApplication sharedApplication] delegate];
        
        [appDelegate beginUploadLogTimer];
        NSLog(@"begin to upload the log into Dropbox");
