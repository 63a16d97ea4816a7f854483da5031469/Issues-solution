#How to scroll UITableView to specific position

it should work:

	- (void)scrollToRowAtIndexPath:(NSIndexPath *)indexPath atScrollPosition:(UITableViewScrollPosition)scrollPosition animated:(BOOL)animated using it this way:

	NSIndexPath *indexPath = [NSIndexPath indexPathForRow:0 inSection:0];
	[yourTableView scrollToRowAtIndexPath:indexPath 
	                     atScrollPosition:UITableViewScrollPositionTop 
	                             animated:YES];
	atScrollPosition could take any of these values:
	
	typedef enum {
	UITableViewScrollPositionNone,
	UITableViewScrollPositionTop,
	UITableViewScrollPositionMiddle,
	UITableViewScrollPositionBottom
	} UITableViewScrollPosition;
	
