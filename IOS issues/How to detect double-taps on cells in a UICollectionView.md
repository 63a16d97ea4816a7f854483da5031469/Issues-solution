#How to detect double-taps on cells in a UICollectionView

	UITapGestureRecognizer *doubleTapFolderGesture = [[UITapGestureRecognizer alloc] initWithTarget:self action:@selector(processDoubleTap:)];
	[doubleTapFolderGesture setNumberOfTapsRequired:2];
	[doubleTapFolderGesture setNumberOfTouchesRequired:1];
	[self.view addGestureRecognizer:doubleTapFolderGesture];
	
	
Then, this:

	- (void) processDoubleTap:(UITapGestureRecognizer *)sender
	{
	    if (sender.state == UIGestureRecognizerStateEnded)
	    {
	        CGPoint point = [sender locationInView:collectionView];
	        NSIndexPath *indexPath = [collectionView indexPathForItemAtPoint:point];
	        if (indexPath)
	        {
	            NSLog(@"Image was double tapped");
	        }
	        else 
	        {
	            DoSomeOtherStuffHereThatIsntRelated;
	        }
	    }
	}