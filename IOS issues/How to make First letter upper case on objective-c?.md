#How to make First letter upper case on objective-c?

If there is only one word-NSString, then use the method

-capitalizedString

	NSString *capitalizedString = [myStr capitalizedString]; // capitalizes every word
	
Otherwise, for multi word strings, you have to extract first character and make only that character upper case.