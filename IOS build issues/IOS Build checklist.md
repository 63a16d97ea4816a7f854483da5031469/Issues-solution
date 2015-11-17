##IOS build checklist:

-->Before the build, I need to create the release and sent out to the whole team.

==>check whether the release note is sent out to users already. 

If yes, then do the following steps:

Go to https://jira.xxx.com/browse/MDSRE-xx

create sub-task according to previous :

upload the release note by using the "Select files" button.

Issue Links:
connect to all the related fixed JIRA ticket. (only JIRA)  To this created sub-task.


1. Refresh specific market's Provisioning Profile and check the keychain.
2. Choose the related "Target" of market, to modify the Version number and build number.
3. Choose the related Provisioning Profile,Team and Code Signing Identity for the "Target".
4. Begin to build.
5. Export the AdHoc IPA or submitting to Apple Store.
6. Do the testing and write the testing excel file.
7. Inform project manager of the testing result.
8. Wait for project manager's command to publish the release by using Crashlytics
9. After releasing the apps, I need to check the links sent out to make sure it is right(version is right and can be download).
10. Report the release result.