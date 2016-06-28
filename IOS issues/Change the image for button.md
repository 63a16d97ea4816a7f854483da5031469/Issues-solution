#Change the image for button

	-(void)buttonTouched:(id)sender
	{
	 UIButton *btn = (UIButton *)sender;
	
	 if( [[btn imageForState:UIControlStateNormal] isEqual:[UIImage imageNamed:@"icon-Locked.png"]])
	    {
	       [btn setImage:[UIImage imageNamed:@"icon-Unlocked.png"] forState:UIControlStateNormal];
	       // other statements
	    }
	 else
	   {
	       [btn setImage:[UIImage imageNamed:@"icon-Locked.png"] forState:UIControlStateNormal];
	       // other statements
	   }
	}