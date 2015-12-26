# How can I set CG_CONTEXT_SHOW_BACKTRACE environmental variable?

Error:

<Error>: CGContextSaveGState: invalid context 0x0. 
If you want to see the backtrace, please set 
CG_CONTEXT_SHOW_BACKTRACE environmental variable.

Solution:

Go to your info.plist of your app

find UIViewControllerBasedStatusBarAppearance

Remove that row