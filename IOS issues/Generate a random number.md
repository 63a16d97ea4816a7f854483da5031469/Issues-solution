#How to generate a random number

	// Get random value between 0 and 99
	int x = arc4random() % 100;
	 
	// Get random number between 500 and 1000
	int y =  (arc4random() % 501) + 500;

If you need to generate a random number within your app, you have to push aside Objective-C, as there is no class with a built-in random number generator. The alternative is to use C, among the functions available are: rand(), srand(), random(), srandom() and arc4random().

arc4random() tends to be preferred as it does not require seeding, the function automatically initializes itself.