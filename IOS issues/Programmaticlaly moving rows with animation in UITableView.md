#Programmaticlaly moving rows with animation in UITableView


###Method 1:
        [self.tableView beginUpdates];
        [self.tableView moveRowAtIndexPath:indexPath toIndexPath:[NSIndexPath indexPathForRow:0 inSection:0]];
        // update your dataSource as well.
        [self.tableView endUpdates];



###Method 2:

	[tableView beginUpdates];
	[tableView deleteRowsAtIndexPaths:[NSArray arrayWithObject:rowToMove]
	                 withRowAnimation:UITableViewRowAnimationLeft];
	         
	         
	      //update the source Date at the same time:           
	     [_data.lists removeObjectAtIndex:indexPath.row];
        [_data.lists insertObject:selectedItem atIndex:0];              
	                 
	[tableView insertRowsAtIndexPaths:[NSArray arrayWithObject:indexPathToMoveTo]
	                 withRowAnimation:UITableViewRowAnimationLeft];
	// update your dataSource as well.
	[tableView endUpdates];