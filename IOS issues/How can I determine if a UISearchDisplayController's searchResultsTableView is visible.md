#How can I determine if a UISearchDisplayController's searchResultsTableView is visible?


[self.searchDisplayController isActive]





How about using the delegate methods for UISearchDisplayController?

searchDisplayController:willShowSearchResultsTableView:
searchDisplayController:didShowSearchResultsTableView:
searchDisplayController:willHideSearchResultsTableView:
searchDisplayController:didHideSearchResultsTableView:
Any reason these won't work for you?
