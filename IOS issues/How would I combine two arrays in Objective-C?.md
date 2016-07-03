#How would I combine two arrays in Objective-C?

NSArray's arrayByAddingObjectsFromArray: is more-or-less equivalent to Javascript's .concat() method:

	NSArray *newArray=[firstArray arrayByAddingObjectsFromArray:secondArray];
If you want to strip-out duplicates:

	NSArray *uniqueEntries = [[NSSet setWithArray:newArray] allObjects];