#SDImageCache - imageFromMemoryCache returns nil

http://stackoverflow.com/questions/14749995/sdimagecache-imagefrommemorycache-returns-nil

When you use:

	- (void)storeImage:(UIImage *)image forKey:(NSString *)key

The image is also saved in the disk cache.

The implementation is something like:

	- (void)storeImage:(UIImage *)image forKey:(NSString *)key
	{
	    [self storeImage:image imageData:nil forKey:key toDisk:YES];
	}
	
So if you need to retreive the image from disk, you can use the following method instead:

	-(void)queryDiskCacheForKey:(NSString *)key done:(void (^)(UIImage *image, SDImageCacheType cacheType))doneBlock;

The default disk cache type will be SDImageCacheTypeNone, so if you need to specify cache type use the SDImageCacheType enum.

	enum SDImageCacheType
	{
	    /**
	* The image wasn't available the SDWebImage caches, but was downloaded from the web.
	*/
	    SDImageCacheTypeNone = 0,
	    /**
	* The image was obtained from the disk cache.
	*/
	    SDImageCacheTypeDisk,
	    /**
	* The image was obtained from the disk cache.
	*/
	    SDImageCacheTypeMemory
	};
	
	
http://www.jianshu.com/p/d6a2987ebf3e

http://blog.csdn.net/sqc3375177/article/details/7714573





###using:

    [[SDImageCache sharedImageCache] queryDiskCacheForKey:@"testImg" done:^(UIImage *image, SDImageCacheType cacheType) {
        NSLog(@"search for image from cache");
        if(image!=nil){
            NSLog(@"the image is not nil");
            
        }
    }];
    
    
     [[SDImageCache sharedImageCache] storeImage:image forKey:@"testImg"];