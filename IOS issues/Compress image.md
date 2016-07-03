#Compress image

	NSData *UIImageJPEGRepresentation(UIImage *image, CGFloat compressionQuality);

OR
	
	NSData *image_Data=UIImageJPEGRepresentation(image_Name,compressionQuality);
	return image as JPEG. May return nil if image has no CGImageRef or invalid bitmap format. compressionQuality is 0(most) & 1(least).
	
	
##Control the image size:
	    NSData *data = UIImageJPEGRepresentation((UIImage *)image,0.3);
	    NSData *anotherData = UIImageJPEGRepresentation((UIImage *)image,0.7);
	    
	    
	    if((data.length/1024>150.0f)&& (anotherData.length/1024<=150.0f)){
	          data = UIImageJPEGRepresentation((UIImage *)image,0.7);
	    }else if((data.length/1024>150.0f) && (anotherData.length/1024>150.0f)){
	        data=UIImageJPEGRepresentation((UIImage *)image,0.4);
	    }	
	
	
##PNG image:
	  NSData *data = UIImagePNGRepresentation((UIImage *)image);
	  
	  
	  
	  
#Image to Data || Data to Image

Use JPEG Compression in two simple steps:

1) Convert UIImage to NSData

	UIImage *rainyImage =[UImage imageNamed:@"rainy.jpg"];
	NSData *imgData= UIImageJPEGRepresentation(rainyImage,0.1 /*compressionQuality*/);
this is lossy compression and image size is reduced.

2) Convert back to UIImage;

	UIImage *image=[UIImage imageWithData:imgData];