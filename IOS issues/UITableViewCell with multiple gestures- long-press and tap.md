#UITableViewCell with multiple gestures: long-press and tap


http://stackoverflow.com/questions/3924446/long-press-on-uitableview

In your cellForRowAtIndexPath method, you can add tap gesture and long press gesture separately and then implement them. By this your didselect function will not be required and you wont have to deSelect anything.

UITapGestureRecognizer *tapGestureRecognizer = [[UITapGestureRecognizer alloc] initWithTarget:self action:@selector(cellTapped:)];
    tapGestureRecognizer.numberOfTapsRequired = 1;
    tapGestureRecognizer.numberOfTouchesRequired = 1;
    cell.tag = indexPath.row;
    [cell addGestureRecognizer:tapGestureRecognizer];


UILongPressGestureRecognizer *lpgr = [[UILongPressGestureRecognizer alloc]
                         initWithTarget:self action:@selector(handleLongPress:)];
        lpgr.minimumPressDuration = 1.0; //seconds
        [cell addGestureRecognizer:lpgr];

cell.selectionStyle = UITableViewCellSelectionStyleNone;
Now,

-(void)handleLongPress:(UILongPressGestureRecognizer *)longPress
{
    // Your code here
}

-(void)cellTapped:(UITapGestureRecognizer*)tap
{
    // Your code here
}
 
hi this is working for me,, but its going to execute this handleLongpress method two times,, I create the gesture and added it into the cell withing cellAtIndex method – user2889249 Mar 11 '14 at 10:30
  	 		
For UILongPressGestureRecognizer you should always check the status property because otherwise you may get numerous calls. e.g.: recognizer.state==UIGestureRecognizerStateBegan





#My way:

Added the 

	UILongPressGestureRecognizer *lpgr = [[UILongPressGestureRecognizer alloc]
	                         initWithTarget:self action:@selector(handleLongPress:)];
	        lpgr.minimumPressDuration = 1.0; //seconds
	        [cell addGestureRecognizer:lpgr];
	
	cell.selectionStyle = UITableViewCellSelectionStyleNone;
	
	Add below code outside the cellForRowAtIndexPath method:
	
	-(void)handleLongPress:(UILongPressGestureRecognizer *)longPress
	{
	    // Your code here
	}



into :
	
	- (UITableViewCell *)tableView:(UITableView *)tableView cellForRowAtIndexPath:(NSIndexPath *)indexPath
	