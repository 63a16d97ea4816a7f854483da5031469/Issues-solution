# indexpath row not getting in prepare for segue for detail disclosure

http://stackoverflow.com/questions/14813786/indexpath-row-not-getting-in-prepare-for-segue-for-detail-disclosure


It is workable:

If you have hooked up accessory action in your storyboard then the sender in prepareForSegue:sender: will be the cell that that was tapped. This means you can just do something like

	NSIndexPath *indexPath = [self.tableView indexPathForCell:sender];