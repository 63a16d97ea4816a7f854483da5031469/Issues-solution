#A background URLSession with identifier ObjectiveDropboxSession already exists!



think you already have an URLSession with identifier backgroundSession. First Call

- (void)invalidateAndCancel
on that. and then try with your code.




https://www.raywenderlich.com/110458/nsurlsession-tutorial-getting-started

