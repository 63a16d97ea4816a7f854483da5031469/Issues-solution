##MKMapView

Could not instantiate class named MKMapView


http://stackoverflow.com/questions/3522066/could-not-instantiate-class-named-mkmapview


**Terminating app due to uncaught exception 'NSInvalidUnarchiveOperationException', reason: 'Could not instantiate class named MKMapView'**

solution:
Add the MapKit framework to the project. (Control + Click Frameworks folder -> Add -> Existing Frameworks)
