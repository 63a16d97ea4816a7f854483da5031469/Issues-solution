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
	
	
##Another way:

	- (CGFloat)tableView:(UITableView *)tableView heightForRowAtIndexPath:(NSIndexPath *)indexPath
	{
	    
	    UIFont * font = [UIFont systemFontOfSize:15.0f];
	    NSString *text = [[_data.lists objectAtIndex:indexPath.row] listTitle];
	    CGFloat height = [text boundingRectWithSize:CGSizeMake(self.tableView.frame.size.width, 150) options:(NSStringDrawingUsesLineFragmentOrigin|NSStringDrawingUsesFontLeading) attributes:@{NSFontAttributeName: font} context:nil].size.height;
	    
	    return height + 60;
	}	
	