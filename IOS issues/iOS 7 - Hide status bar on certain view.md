#iOS 7 - Hide status bar on certain view

####Below one is tested in IOS9, it works:

Implement this method in your View Controller,

-(BOOL)prefersStatusBarHidden
{
    return YES;
}
and call this method where you want,

[self prefersStatusBarHidden];