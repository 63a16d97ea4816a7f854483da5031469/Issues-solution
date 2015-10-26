
##HTTP Strict Transport Security

HTTP Strict Transport Security (HSTS) is a web security policy mechanism which helps to protect secure HTTPS websites against downgrade attacks and cookie hijacking. It allows web servers to declare that web browsers (or other complying user agents) should only interact with it using secure HTTPS connections,[1] and never via the insecure HTTP protocol. HSTS is an IETF standards track protocol and is specified in RFC 6797.

The HSTS Policy[2] is communicated by the server to the user agent via a HTTP response header field named "Strict-Transport-Security". HSTS Policy specifies a period of time during which the user agent shall access the server in a secure-only fashion.



HSTS mechanism overview[edit]
A server implements an HSTS policy by supplying a header over an HTTPS connection (HSTS headers over HTTP are ignored).[12] For example, a server could send a header such that future requests to the domain for the next year (max-age is specified in seconds, 31536000 is approximately one year) use only HTTPS: Strict-Transport-Security: max-age=31536000; includeSubDomains;.

When a web application[13] issues HSTS Policy to user agents, conformant user agents behave as follows:[14]

Automatically turn any insecure links referencing the web application into secure links. (For instance, http://example.com/some/page/ will be modified to https://example.com/some/page/ before accessing the server.)
If the security of the connection cannot be ensured (e.g. the server's TLS certificate is not trusted), show an error message and do not allow the user to access the web application.[15]
The HSTS Policy helps protect web application users against some passive (eavesdropping) and active network attacks.[16] A man-in-the-middle attacker has a greatly reduced ability to intercept requests and responses between a user and a web application server while the user's browser has HSTS Policy in effect for that web application.

This is the cache file's contain which I got from real app's cache file:

// !!! BINARY PROPERTY LIST WARNING !!!  
//  
// The pretty-printed property list below has been created  
// from a binary version on disk and should not be saved as  
// the ASCII format is a subset of the binary representation!  
//

	{	"HSTS Content Version" = 7;
	"HSTS Preload Entries Signature" = "1686dd20b5f446499628e11b34ed8b56dd26b8ceb8051a062551d8efd57622ddb";
	"HSTS Store Schema Version" = 3;
	com.apple.CFNetwork.defaultStorageSession = {
		accounts.google.com = {
			"Create Time" = 466237831;
			Expiry = 9223372036854775808;
			"HSTS Host" = :true;
			"Include Subdomains" = :true;
		};
		aclu.org = {
			"Create Time" = 466237831;
			Expiry = 9223372036854775808;
			"HSTS Host" = :true;
		};
		activiti.alfresco.com = {
			"Create Time" = 466237831;
			Expiry = 9223372036854775808;
			"HSTS Host" = :true;
		};

		.......


				};
		zenpayroll.com = {
			"Create Time" = 466237831;
			Expiry = 9223372036854775808;
			"HSTS Host" = :true;
		};
		zh.search.yahoo.com = {
			"Create Time" = 466237831;
			Expiry = 9223372036854775808;
			"HSTS Host" = :true;
		};
		"zoo24.de" = {
			"Create Time" = 466237831;
			Expiry = 9223372036854775808;
			"HSTS Host" = :true;
			"Include Subdomains" = :true;
		};
	};
	}

