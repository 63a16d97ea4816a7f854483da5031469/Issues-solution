#Get the current running viewController from AppDelegate:

            UINavigationController * navigationController = (UINavigationController *)self.window.rootViewController;
            MainViewController * controller = (MainViewController *)[navigationController.viewControllers objectAtIndex:0];
            [controller SaveButtonAction:nil];