#Switch	
	- (IBAction)changeSwitch:(id)sender{
	
	    if([sender isOn]){
	        NSLog(@"Switch is ON");
	    } else{
	        NSLog(@"Switch is OFF");
	    }
	
	}