#Attempted to create a task in a session that has been invalidated

The reason is that:

Have not release the strong reference the task variable.


So changed it to the weak reference. ===> issue is solved.