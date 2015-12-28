##ViewForAnnotation is not being called

http://stackoverflow.com/questions/3821515/viewforannotation-is-not-being-called


	I had the same problem which was not setting the MapView delegate to the File Owner.
	
	Open your nib
	Right click on the MapView
	Drag the delegate to the File's Owner
	



 
Make sure the map view's delegate property is set.

If the map is created in IB, right-click on it and hook up its delegate outlet to File's Owner.

If the map is created in code, set the delegate after creating the map view:

mapView.delegate = self;


@interface myViewController : UIViewController <MKMapViewDelegate> {
    MKMapView *_mapView;
}


- (MKAnnotationView *)mapView:(MKMapView *)theMapView viewForAnnotation:(id <MKAnnotation>)annotation
{
    NSLog(@"MKAnnotationView");
    return nil;
}