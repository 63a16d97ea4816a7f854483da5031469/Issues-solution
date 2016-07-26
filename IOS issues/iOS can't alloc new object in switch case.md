#iOS can't alloc new object in switch case

I had same problem before, simply add a {} in your case, all your problem will be solved.

Such as:

	switch ([weatherCode intValue]) {
	   case 1:
	   {
	      ...
	   }
	       break;
	   case 2:
	   {
	      ...
	   }          
	   break;
	}