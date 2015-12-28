#ScrollView useage:

http://stackoverflow.com/questions/5883064/how-can-i-use-uiscrollview



	
Ensure that "Use Autolayout" is unchecked in the IB Document attributes. I had the exact same issue, setting the correct contentSize and all, but with this feature enabled, scrolling was always disabled.

Use Autolayout needs to be OFF

UPDATE To use Autolayout, explicitly set the width and height of the scrollView's content in the viewDidAppear method, like this:


	- (void)viewDidAppear:(BOOL)animated
	{
	    [super viewDidAppear:animated];
	
	    // set the scrollview to the specified size
	    CGRect screenRect = [[UIScreen mainScreen] bounds];
	    
	 // this sentence is very improtant:
	    [scrollView setContentSize:CGSizeMake(screenRect.size.width, 1100)];
	
	 //   [scrollView setBounds:CGRectMake(0, 0, screenRect.size.width, screenRect.size.height)];
	
	 //   [scrollView setScrollIndicatorInsets:UIEdgeInsetsFromString(@"{0,0,0,-1.0}")];
	
	}



After using autolayout, you should make sure that the 
ScrollView's contentSize's height larger than the actual scrollView's height. Otherwise, You cannot scroll the view.

	    [scrollView setContentSize:CGSizeMake(screenRect.size.width, 1100)];
	    
	    
	    
	    


http://www.tutorialspoint.com/ios/ios_ui_elements_scrollview.htm

##how to use it:

	This will get you an insight of the UIScrollView control:
	
	Learning the basics of UIScrollView
	
	Referenced from UIScrollView Tutorials
	
	Some good samples with the basic functionalities covered
	
	http://halmueller.wordpress.com/2008/10/08/a-very-simple-uiscrollview-demo/
	http://developer.apple.com/iphone/library/samplecode/Scrolling/index.html
	http://www.vimeo.com/1642150
	http://jonathanwatmough.com/2008/12/implementing-tap-to-zoom-in-uiscrollview-on-an-iphone/
	http://cocoawithlove.com/2009/01/multiple-virtual-pages-in-uiscrollview.html
	Not to mention:
	
	http://stackoverflow.com/search?q=UIScrollView