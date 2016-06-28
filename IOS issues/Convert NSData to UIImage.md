#Convert NSData to UIImage

Convert NSData to UIImage :

	NSData *data = ... // data that you received
	UIImage *image = [UIImage imageWithData:data];
	Convert UIImage to NSData (png) :
	
	UIImage *image = [UIImage imageNamed:@"imageName.png"];
	NSData *imageData = UIImagePNGRepresentation(image);
	Convert UIImage to NSData (jpg) :
	
	UIImage *image = [UIImage imageNamed:@"imageName.jpg"];
	NSData *imageData = UIImageJPEGRepresentation(image, 1.0);