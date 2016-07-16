#CocoaPods with XCode 6.0.1 - How can I fix Pods Frameworks appearing in red?


http://stackoverflow.com/questions/26246805/cocoapods-with-xcode-6-0-1-how-can-i-fix-pods-frameworks-appearing-in-red

####Right solution:

	I had the same problem. It turns out I just need to run a pod update with
	
	sudo gem install cocoapods
	
	
	
	I unlocked the pod file and removed the issues existed lines.