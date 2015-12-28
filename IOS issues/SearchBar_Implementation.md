##Search Bar implementation.

##Change Search Bar place holder color:
KeyPath:  
		_searchField._placeholderLabel.textColor=[UIColor whiteColor];

//change the text color of searchBar:

    [[UITextField appearanceWhenContainedIn:[UISearchBar class], nil] setTextColor:[UIColor whiteColor]];
    
//change the search bar 'cancel' button's color:

	[[UIBarButtonItem appearanceWhenContainedInInstancesOfClasses:@[[UISearchBar class]]] setTintColor:[UIColor whiteColor]];
	
	
##Changing Icon Colors on UISearchBar and UITextField

http://www.tanryan.com/2015/05/changing-icon-colors-on-uisearchbar-and-uitextfield/	
	
	// Reference search display controller search bar's text field (in my case).
	UITextField *searchBarTextField = [self.searchDisplayController.searchBar valueForKey:@"_searchField"];
	
	// Magnifying glass icon.
	UIImageView *leftImageView = (UIImageView *)searchBarTextField.leftView;
	leftImageView.image = [LeftImageView.image imageWithRenderingMode:UIImageRenderingModeAlwaysTemplate];
	leftImageView.tintColor = [UIColor whiteColor];
	    
	// Clear button
	UIButton *clearButton = [searchBarTextField valueForKey:@"_clearButton"];
	[clearButton setImage:[clearButton.imageView.image imageWithRenderingMode:UIImageRenderingModeAlwaysTemplate] forState:UIControlStateNormal];
	clearButton.tintColor = [UIColor whiteColor];	
	

##After the filterContentForSearchText get the results but the tableview did not update the results:	
	
This is the offending line:

RestaurantsCell *cell = [tableView dequeueReusableCellWithIdentifier:cellIdentifier];
Should be:

RestaurantsCell *cell = [self.tableView dequeueReusableCellWithIdentifier:cellIdentifier];






##Implementation:
http://www.appcoda.com/search-bar-tutorial-ios7/


Like UITableView, the table view bundled in the search display controller adopts the same approach. According to the official documentation of UISearchDisplayController, here are the available delegates that let you interact with the search result and search bar:

The search results table view’s data source, which is needed to provide the data for search result table.
The search result table view’s delegate, which is used to respond to the user’s selection of a search item.
The search display controller’s delegate, which responds to the events such as when the search starts or ends and when the search interface is displayed or hidden.

The search bar’s delegate, which is responsible for responding to changes in the search criteria.