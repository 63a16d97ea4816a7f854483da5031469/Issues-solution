##Search Bar implementation.

##Change Search Bar place holder color:
KeyPath:  
		_searchField._placeholderLabel.textColor=[UIColor whiteColor];

//change the text color of searchBar:

    [[UITextField appearanceWhenContainedIn:[UISearchBar class], nil] setTextColor:[UIColor whiteColor]];
    
//change the search bar 'cancel' button's color:

	[[UIBarButtonItem appearanceWhenContainedInInstancesOfClasses:@[[UISearchBar class]]] setTintColor:[UIColor whiteColor]];

##Implementation:
http://www.appcoda.com/search-bar-tutorial-ios7/


Like UITableView, the table view bundled in the search display controller adopts the same approach. According to the official documentation of UISearchDisplayController, here are the available delegates that let you interact with the search result and search bar:

The search results table view’s data source, which is needed to provide the data for search result table.
The search result table view’s delegate, which is used to respond to the user’s selection of a search item.
The search display controller’s delegate, which responds to the events such as when the search starts or ends and when the search interface is displayed or hidden.

The search bar’s delegate, which is responsible for responding to changes in the search criteria.