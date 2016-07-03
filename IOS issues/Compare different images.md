#Compare different images

Generate hash from UIImage

http://stackoverflow.com/questions/1684799/generate-hash-from-uiimage/1685319#1685319

I wound up using the following code to accomplish the task. Note that this requires that you import <CommonCrypto/CommonDigest.h>:

	unsigned char result[CC_MD5_DIGEST_LENGTH];
	NSData *imageData = [NSData dataWithData:UIImagePNGRepresentation(inImage)];
	CC_MD5([imageData bytes], [imageData length], result);
	NSString *imageHash = [NSString stringWithFormat:
	                       @"%02X%02X%02X%02X%02X%02X%02X%02X%02X%02X%02X%02X%02X%02X%02X%02X",
	                       result[0], result[1], result[2], result[3], 
	                       result[4], result[5], result[6], result[7],
	                       result[8], result[9], result[10], result[11],
	                       result[12], result[13], result[14], result[15]
	                       ];
	                       
	                       
The same function code:

	+(NSString *)MD5HexDigest:(NSData *)input {
	    unsigned char result[CC_MD5_DIGEST_LENGTH];
	
	    CC_MD5(input.bytes, (unsigned int)input.length, result);
	    NSMutableString *ret = [NSMutableString stringWithCapacity:CC_MD5_DIGEST_LENGTH*2];
	    for (int i = 0; i<CC_MD5_DIGEST_LENGTH; i++) {
	        [ret appendFormat:@"%02x",result[i]];
	    }
	    return ret;
	}