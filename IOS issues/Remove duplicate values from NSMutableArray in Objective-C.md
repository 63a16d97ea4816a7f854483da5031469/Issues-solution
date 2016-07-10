#Remove duplicate values from NSMutableArray in Objective-C


	NSOrderedSet *orderedSet = [NSOrderedSet orderedSetWithArray:yourArray];
	NSArray *arrayWithoutDuplicates = [orderedSet array];
	
If you are worried about the order and you're running on iOS 4 or earlier, loop over a copy of the array:

	NSArray *copy = [mutableArray copy];
	NSInteger index = [copy count] - 1;
	for (id object in [copy reverseObjectEnumerator]) {
	    if ([mutableArray indexOfObject:object inRange:NSMakeRange(0, index)] != NSNotFound) {
	        [mutableArray removeObjectAtIndex:index];
	    }
	    index--;
	}
	


there is a more elegant way to remove duplicates in a NSArray if you don't care about the order:

	uniquearray = [yourarray valueForKeyPath:@"@distinctUnionOfObjects.fieldNameTobeFiltered"];
	
Example:
	
	  NSArray *arrUnique = [_pSessionArr valueForKeyPath:@"@distinctUnionOfObjects.self.title"];
    [_pSessionArr removeObjectsInRange:NSMakeRange(arrUnique.count, _pSessionArr.count-arrUnique.count )];