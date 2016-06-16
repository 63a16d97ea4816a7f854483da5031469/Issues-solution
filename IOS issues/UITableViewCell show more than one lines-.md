#UITableViewCell show more than one lines:

You can use the existing UILabel views in the UITableViewCell for this. The secret is to do the following:   

	cell.textLabel.numberOfLines = 0;
	cell.textLabel.lineBreakMode = UILineBreakModeWordWrap;


	\#define HEIGHT_CELL_NORMAL 80

Adjust the height of the row:  

		- (CGFloat)tableView:(UITableView *)tableView heightForRowAtIndexPath:(NSIndexPath *)indexPath
		{
		    
		    return HEIGHT_CELL_NORMAL;
		}