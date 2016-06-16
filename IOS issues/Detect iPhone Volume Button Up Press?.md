#Detect iPhone Volume Button Up Press?

@import AVFoundation;
	
	- (void)viewWillAppear:(BOOL)animated {
	
	    AVAudioSession* audioSession = [AVAudioSession sharedInstance];
	
	    [audioSession setActive:YES error:nil];
	    [audioSession addObserver:self
	                    forKeyPath:@"outputVolume"
	                       options:0
	                       context:nil];
	}
	
	-(void) observeValueForKeyPath:(NSString *)keyPath ofObject:(id)object change:(NSDictionary *)change context:(void *)context {
	
	    if ([keyPath isEqual:@"outputVolume"]) {
	        NSLog(@"volume changed!");
	    }
	}
	
	
http://www.jianshu.com/p/7f2ddff12c3f