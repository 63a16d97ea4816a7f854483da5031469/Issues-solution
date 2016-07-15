#How to monitor NSSystemClockDidChangeNotification in iPhone SDK

http://stackoverflow.com/questions/6369385/how-to-monitor-nssystemclockdidchangenotification-in-iphone-sdk



http://justsee.iteye.com/blog/1969932



Network Time Protocol for iPhone

http://stackoverflow.com/questions/2269532/network-time-protocol-for-iphone


https://github.com/huynguyencong/NHNetworkTime


NHNetworkTime

A network time protocol (NTP) client.

About

The clock on the oldest iPhone, iTouch or iPad is not closely synchronized to the correct time. In the case of a device which is obtaining its time from the telephone system, there is a setting to enable synchronizing to the phone company time, but that time has been known to be over a minute different from the correct time.

In addition, users may change their device time and severely affect applications that rely on correct times to enforce functionality, or may set their devices clock into the past in an attempt to dodge an expiry date.

This project contains code to provide time obtained from standard time servers using the simple network time protocol (SNTP: RFC 5905). The implementation is not a rigorous as described in that document since the goal was to improve time accuracy to tens of milliSeconds, not to microseconds.

Computers using the NTP protocol usually employ it in a continuous low level task to keep track of the time on a continuous basis. A background application uses occasional time estimates from a set of time servers to determine the best time by sampling these values over time. iOS applications are different, being more likely to want a one-time, quick estimate of the time.

Compatible

iOS 7 and later.
Objective C, and Swift with bridge header (read below guide)