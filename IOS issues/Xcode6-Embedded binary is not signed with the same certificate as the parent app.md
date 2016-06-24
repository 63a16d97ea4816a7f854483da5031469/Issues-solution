#Xcode6:Embedded binary is not signed with the same certificate as the parent app

http://stackoverflow.com/questions/25927604/xcode6embedded-binary-is-not-signed-with-the-same-certificate-as-the-parent-app

Because the Extension target's Developer account is different with its parent's.


If your Xcode has been working fine but stopped working after you add an extension target to your project, most of the time is that your app was signed using a older certificate (still valid with your name etc.), while your extension is signed with a newer certificate with entitlement for the extension. This is why the error. In this case, you most likely have two certificates with the same name, and this what you can do:
1.Go to Xcode->Preference;
2. Select Accounts Tab;
3. Select your Apple ID then click on View Details;
4. Under signing Identities List Window, select IOS Development, then click on the little Configuration icon, and select Revoke;
5. Xcode will then try to download a new certificate.
You can do a clean build after this so both your app and extension will be signed using the new certificate.