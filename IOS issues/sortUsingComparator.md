#sortUsingComparator

	[persons sortUsingComparator:
	      ^NSComparisonResult(id obj1, id obj2){
	
	             Person *p1 = (Person*)obj1;
	             Person *p2 = (Person*)obj2;
	             if (p1.personAge > p2.personAge) {
	                return (NSComparisonResult)NSOrderedDescending;
	            }
	
	            if (p1.personAge < p2.personAge) {
	                return (NSComparisonResult)NSOrderedAscending;
	            }
	            return (NSComparisonResult)NSOrderedSame;
	    }
	];