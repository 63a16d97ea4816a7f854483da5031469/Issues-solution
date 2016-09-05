#Change navigationbar back btn:


    UIImage* backBtnImg = [UIImage imageNamed:@"back.png"];
    CGRect frameimg = CGRectMake(15,0, 16,25);
    
    UIButton *leftBackButton = [[UIButton alloc] initWithFrame:frameimg];
    [leftBackButton setBackgroundImage:backBtnImg forState:UIControlStateNormal];
    [leftBackButton addTarget:self action:@selector(pressBackAction:)
             forControlEvents:UIControlEventTouchUpInside];
    [leftBackButton setShowsTouchWhenHighlighted:YES];
    
    UIBarButtonItem *leftTmpBtn =[[UIBarButtonItem alloc] initWithCustomView:leftBackButton];
    self.navigationItem.leftBarButtonItem =leftTmpBtn;
    
    
##While Back Button
<img src="white.png"/> 

##Blue Back Button
<img src="blue.png"/>

##Black Back Button
<img src="black.png"/>