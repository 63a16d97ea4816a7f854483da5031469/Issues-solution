##No matching provisioning profiles found for application”

> Failed to locate or generate matching signing assets:
Xcode attempted to locate or generate matching signing assets and failed to do so because of the following issues:  
No matching provisioning profiles found for "Applications/MyApp.app”  
None of the valid provisioning profiles allowed the specified entitlements: application-identifier, beta-reports-active, keychain-access-groups.  



If you are sure you have valid certificate and provisioning profile, then you may need to do the following:

I would suggest people to refresh the link between xCode and developer account by doing the following:

Go to Xcode -> Preferences -> Account -> View details -> (Refresh icon)

Otherwise you may not be able to see the provisioning profile as an option in the build settings (You may only see old profiles)

A lot of times it gives me connection error, you may need to retry.

Do this refresh every time you edit the provisioning profile or certificate online on apple developer member center