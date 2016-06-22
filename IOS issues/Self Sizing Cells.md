#Self Sizing Cells

http://www.cocoachina.com/ios/20140922/9717.html

For iOS 8, I found out that you cannot do the same strategy as for Dynamic Table View Cell.

To automatically adjust the height of static cells, I implement these two UITableViewDelegate methods:

	-(CGFloat)tableView:(UITableView *)tableView heightForRowAtIndexPath:(NSIndexPath *)indexPath
	{
	    return UITableViewAutomaticDimension;
	}
	
	-(CGFloat)tableView:(UITableView *)tableView estimatedHeightForRowAtIndexPath:(NSIndexPath *)indexPath
	{
	    return 44;
	}