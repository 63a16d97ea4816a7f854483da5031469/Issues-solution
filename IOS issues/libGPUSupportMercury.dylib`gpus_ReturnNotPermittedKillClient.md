#libGPUSupportMercury.dylib`gpus_ReturnNotPermittedKillClient:

https://developer.apple.com/library/ios/qa/qa1766/_index.html

Actually, the WebView is using the GPUSupport.

solution:
When view will disappear:
webView=nil;

