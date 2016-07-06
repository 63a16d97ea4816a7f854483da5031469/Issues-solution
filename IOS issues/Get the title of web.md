#Get the title of web

	- (void)webViewDidFinishLoad:(UIWebView *)webView
	{
	    NSString* title = [webView stringByEvaluatingJavaScriptFromString: @"document.title"];
	    navbar.title = title;
	}