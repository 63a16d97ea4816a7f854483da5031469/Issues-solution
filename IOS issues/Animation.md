#Animation

	[UIView animateWithDuration:20.0
	delay:0.0
	options: UIViewAnimationOptionAllowUserInteraction + UIViewAnimationOptionRepeat +UIViewAnimationOptionCurveLinear
	animations:^{imageView.frame = CGRectMake(0, 0, 12000, 768); 
	}
	completion:nil];