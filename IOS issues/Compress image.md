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