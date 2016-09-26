#KERN_INVALID_ADDRESS at 0x0000000000000000

Exception Type:  EXC_BAD_ACCESS (SIGSEGV)
Exception Subtype: KERN_INVALID_ADDRESS at 0x0000000000000000
Triggered by Thread:  0



EXC_BAD_ACCESS usually happens because you are sending an Obj-C message to an invalid memory address, what means that you probably are trying to access some deallocated object.

It may be working on other devices because this object is not being released at the same time.

I recently had a similar crash that happened because there was a timer not being invalidated on dealloc, and when the target method was called, that object did no longer exist.

You could try to enable NSZombie objects and see if you find which object is being deallocated. In xCode 6, you can enable them in Product > Scheme > Edit scheme > Diagnostics > Enable Zombie Objects.

Also, there are lots of these kind of errors that NSZombieEnabled can't detect. Unfortunately there is nothing magical to solve it. The second option would be to run your app with instruments (memory leaks specifically) and see if you can get something. If this doesn't work you will have to review your code and check that there are no possibilities that you are trying to access a deallocated object. Hope it helps.



#0
Crashed: com.apple.networking.connection.0x15ef7860
EXC_BAD_ACCESS KERN_INVALID_ADDRESS 0x0000000000000000
 Raw Text
0
libobjc.A.dylib	
objc_msgSend + 21
8
libsystem_network.dylib	
tcp_connection_cancel + 116
9	CFNetwork	
SocketStream::close(void const*) + 260
10
CoreFoundation	
_CFStreamClose + 78
20
libsystem_pthread.dylib	
start_wqthread + 8


