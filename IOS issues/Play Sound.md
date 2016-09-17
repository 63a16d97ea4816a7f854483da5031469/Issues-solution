#Play Sound
 
There is a list posted to AudioServices - iPhone Development Wiki. I've not yet figured out if using this in the following way is grounds for rejection:

	AudioServicesPlaySystemSound(1103);
	
Don't forget to include:

	#import <AudioToolbox/AudioToolbox.h>