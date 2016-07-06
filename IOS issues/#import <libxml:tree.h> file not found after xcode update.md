#\#import <libxml/tree.h> file not found after xcode update

http://stackoverflow.com/questions/14622684/import-libxml-tree-h-file-not-found-after-xcode-update


 
In your build settings, add the following to your Header Search Paths:
 
$SDKROOT/usr/include/libxml2