#Tableview Section

Only take note here.

###Secion header and title:

	- (nullable UIView *)tableView:(UITableView *)tableView viewForHeaderInSection:(NSInteger)section{
	    UIView *view=[UIView new];
	    
	    UILabel *hLabel=[[UILabel alloc] initWithFrame:CGRectMake(13,0,[[UIScreen mainScreen] bounds].size.width,21)];
	    
	    hLabel.backgroundColor=[UIColor clearColor];
	    hLabel.shadowColor = [UIColor whiteColor];
	    hLabel.shadowOffset = CGSizeMake(0.5,1);
	    hLabel.textColor = [UIColor blackColor];
	    hLabel.font = [UIFont boldSystemFontOfSize:17];
	    if(section==0){
	        hLabel.text = @"section 1";
	    }else{
	        hLabel.text=@"section 2";
	    }
	    
	    [view addSubview:hLabel];
	    
	    view.backgroundColor=[UIColor whiteColor];
	    
	    return view;
	}

###height of section:

	- (CGFloat)tableView:(UITableView *)tableView heightForHeaderInSection:(NSInteger)section{
	    
	    return 20;
}    

###Number of section:

	-(NSInteger)tableView:(UITableView *)tableView numberOfRowsInSection:(NSInteger)section
	{
	
	}




###Non-Selection style:
        cell.selectionStyle=UITableViewCellSelectionStyleNone;