#KVC Collection Operators

http://nshipster.com/kvc-collection-operators/



there is a more elegant way to remove duplicates in a NSArray if you don't care about the order:

	uniquearray = [yourarray valueForKeyPath:@"@distinctUnionOfObjects.fieldNameTobeFiltered"];
	
Example:
	
	  NSArray *arrUnique = [_pSessionArr valueForKeyPath:@"@distinctUnionOfObjects.self.title"];
    [_pSessionArr removeObjectsInRange:NSMakeRange(arrUnique.count, _pSessionArr.count-arrUnique.count )];