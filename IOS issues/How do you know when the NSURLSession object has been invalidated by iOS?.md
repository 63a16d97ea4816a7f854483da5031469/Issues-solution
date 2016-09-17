#How do you know when the NSURLSession object has been invalidated by iOS?
 
When you create your NSURLSession object use the sessionWithConfiguration:(NSURLSessionConfiguration *)configuration delegate:(id <NSURLSessionDelegate>)delegate delegateQueue:(NSOperationQueue *)queue; method and specify yourself as the delegate.

You will then get a callback in: - (void)URLSession:(NSURLSession *)session didBecomeInvalidWithError:(NSError *)error; when the session is invalidated.

You cannot trust that invalidateAndCancel will instantly stop all tasks since it is up to the tasks to handle the cancel-call.

From the header of NSURLSession:

/* -invalidateAndCancel acts as -finishTasksAndInvalidate, but issues
* -cancel to all outstanding tasks for this session.  Note task 
* cancellation is subject to the state of the task, and some tasks may
* have already have completed at the time they are sent -cancel. 
*/