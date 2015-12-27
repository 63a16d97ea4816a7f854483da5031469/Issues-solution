#Embed the navigationController the first row move down

http://stackoverflow.com/questions/18906919/remove-empty-space-before-cells-in-uitableview

###Soulution:

##Storyboard
Go to the attributes inspector of the View Controller by selecting the xib or the controller in Storyboard. Uncheck the Adjust Scroll View Insets in Layout. It will solve the problem.


## Programmatically

Add this to i.e. viewDidLoad (credits to Slavco Petkovski's answer and Cris R's comment)

// Objective-C
self.automaticallyAdjustsScrollViewInsets = NO;