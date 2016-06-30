#How to scroll UICollectionViewCell programmatically in IOS?

	NSArray *visibleItems = [self.collectionView indexPathsForVisibleItems];
	  NSIndexPath *currentItem = [visibleItems objectAtIndex:0];
	  NSIndexPath *nextItem = [NSIndexPath indexPathForItem:currentItem.item + 1 inSection:currentItem.section];
	  [self.collectionView scrollToItemAtIndexPath:nextItem atScrollPosition:UICollectionViewScrollPositionTop animated:YES];
	  
	  
These parameters:
<font color=red>
UICollectionViewScrollPositionCenteredHorizontally </font> This one is the same with your finger to touch to scroll the cell.


	  
	      UICollectionViewScrollPositionNone                 = 0,
    
    // The vertical positions are mutually exclusive to each other, but are bitwise or-able with the horizontal scroll positions.
    // Combining positions from the same grouping (horizontal or vertical) will result in an NSInvalidArgumentException.
    UICollectionViewScrollPositionTop                  = 1 << 0,
    UICollectionViewScrollPositionCenteredVertically   = 1 << 1,
    UICollectionViewScrollPositionBottom               = 1 << 2,
    
    // Likewise, the horizontal positions are mutually exclusive to each other.
    UICollectionViewScrollPositionLeft                 = 1 << 3,
    UICollectionViewScrollPositionCenteredHorizontally = 1 << 4,
    UICollectionViewScrollPositionRight                = 1 << 5