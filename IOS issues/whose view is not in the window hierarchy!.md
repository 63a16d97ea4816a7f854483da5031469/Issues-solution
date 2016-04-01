#whose view is not in the window hierarchy!

	2016-03-29 22:08:19.850 xxxx[5294:2297472] Unbalanced calls to begin/end appearance transitions for <UINavigationController: 0x12d820200>.



##solution:
Reason:
  
	     [self presentViewController:vc animated:YES completion:NULL];
     
The above sentence only can be used under navigation controller. 


 
##Another:
    UINavigationController* nav = [[UINavigationController alloc] init];
    xxxxxxController* vc = (xxxxxxController * )[self.storyboard instantiateViewControllerWithIdentifier:@"xxxxxVC"];
    [nav pushViewController:vc animated:FALSE];