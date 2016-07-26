#Get the current running viewController from AppDelegate:

            UINavigationController * navigationController = (UINavigationController *)self.window.rootViewController;
            MainViewController * controller = (MainViewController *)[navigationController.viewControllers objectAtIndex:0];
            [controller SaveButtonAction:nil];
            
            
##Another method:

            
            -(void)application:(UIApplication *)application performFetchWithCompletionHandler:(void (^)(UIBackgroundFetchResult))completionHandler{
    
    NSDate *fetchStart = [NSDate date];
    
    ViewController *viewController = (ViewController *)self.window.rootViewController;
    
    [viewController fetchNewDataWithCompletionHandler:^(UIBackgroundFetchResult result) {
        completionHandler(result);
        
        NSDate *fetchEnd = [NSDate date];
        NSTimeInterval timeElapsed = [fetchEnd timeIntervalSinceDate:fetchStart];
        NSLog(@"Background Fetch Duration: %f seconds", timeElapsed);
        
    }];
}
