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
3. Before build, you need to commit the change for Version Number and build number.
4. Choose the related Provisioning Profile,Team and Code Signing Identity for the "Target".
5. Begin to build.
6. Export the AdHoc IPA or submitting to Apple Store.
7. Do the testing and write the testing excel file. Especially for the JIRA tickets appeared in Release Note
8. Inform project manager of the testing result by using email.
9. Wait for project manager's command to publish the release by using Crashlytics
10. After releasing the apps, I need to check the links sent out to make sure it is right(version is right and can be download).
11. Report the release result.
12. After build, you need to add tag/branch for this release in SVN.


Send release information to internal team.

update to alpha, send email notification
update to beta, send email notification


If someone added new bugzilla:

(1) Update the release note
(2) Upload the latest one to related JIRA release master ticket.
(3) Link the new tickets into JIRA release master ticket.
(4) Send the latest release note to all.


