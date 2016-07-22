#iOS9 This application is modifying the autolayout engine from a background thread, which can lead to engine corruption and weird crashes


The first error you note doesn't look like it's related to your drawRect: code. Your drawRect: looks fine. It isn't doing anything particularly complicated. If your path were more complex, you'd probably want to cache it, but it's probably fine as-is. More likely you're trying to modify the UI somewhere else on a background thread. It may only spring up when you override drawRect: because that changes how the UI update happens (without a custom drawRect:, the system may be able to apply simple transforms). You need to look for where you're making a UIKit call on a background thread.

When in doubt, if it starts with UI, you probably can't use it on a background thread. That's not completely true (you can create a UIBezierPath on a background thread, and you can even draw it into a non-screen context), but as a first approximation, it's a good thing to look for.

This code is simply incorrect:

	  dispatch_async(dispatch_get_main_queue(), ^{
		    buttonBox.fill()
		});
		
The call to drawRect: had better already be on the main queue (so dispatching to the main queue is not helpful). If it's not, see above. By the time this block executes, the draw cycle is over, so there's no context to draw into any more.


http://stackoverflow.com/questions/17490286/does-dispatch-asyncdispatch-get-main-queue-wait-until-done