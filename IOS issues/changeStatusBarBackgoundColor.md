#change status bar background color    
    
    UIView *statusBarView =  [[UIView alloc] initWithFrame:CGRectMake(0, 0, ScreenWidth, 22)];
    statusBarView.backgroundColor  =  [UIColor colorWithRed:19.0f/255.0f green:158.0f/255.0f blue:234.0f/255.0f alpha:1];
    [self.view addSubview:statusBarView];
    
    
    
##change the status bar font color:
 
http://stackoverflow.com/questions/33103831/how-to-change-status-bar-text-color-in-ios-9    
    Solved:

First set

[[UIApplication sharedApplication] setStatusBarStyle:UIStatusBarStyleLightContent];

in app delegate in

- (BOOL)application:(UIApplication *)application  didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
method

- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {

[[UIApplication sharedApplication] setStatusBarStyle:UIStatusBarStyleLightContent];

}
and then set View controller-based status bar appearance equal to NO in plist.

Enjoy :)

