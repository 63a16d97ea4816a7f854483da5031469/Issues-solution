#Navigation bar left button and title

##Navigation bar left button:

    UIImage* backBtnImg = [UIImage imageNamed:@"back.png"];
    CGRect frameimg = CGRectMake(15,5, 16,25);
    
    UIButton *leftBackButton = [[UIButton alloc] initWithFrame:frameimg];
    [leftBackButton setBackgroundImage:backBtnImg forState:UIControlStateNormal];
    [leftBackButton addTarget:self action:@selector(pressBackAction:)
         forControlEvents:UIControlEventTouchUpInside];
    [leftBackButton setShowsTouchWhenHighlighted:YES];
    
    UIBarButtonItem *leftTmpBtn =[[UIBarButtonItem alloc] initWithCustomView:leftBackButton];
    self.navigationItem.leftBarButtonItem =leftTmpBtn;
    
    self.navigationItem.title=@"Licenses";

	-(void)pressBackAction:(id)sender{
	    NSLog(@"press back btn");
	      [self.sideMenuViewController presentLeftMenuViewController];
	}
	
	
##Title:
The correct way to change the title font (and color) is:
	
    NSShadow* shadow = [NSShadow new];
    shadow.shadowOffset = CGSizeMake(0.0f, 0.0f);
    shadow.shadowColor = [UIColor blackColor];
    [self.navigationController.navigationBar setTitleTextAttributes: @{
                                                            NSForegroundColorAttributeName: [UIColor blackColor],
                                                            NSFontAttributeName: [UIFont fontWithName:@"Helvetica-bold" size:28.0f],
                                                            NSShadowAttributeName: shadow
                                                            }];
	
	
http://stackoverflow.com/questions/19791762/ios-7-change-navigation-bar-title-font