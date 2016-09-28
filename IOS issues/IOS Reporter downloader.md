#IOS Reporter downloader

Setup

Before using Reporter, make sure you have Java 1.6 or later installed.

First, download Reporter and uncompress the ZIP file in the folder where you would like your reports downloaded. The package contains two files:

Reporter.jar

Reporter.properties

Next, open the properties file using a text editor, and change it to the Apple ID and password you use for iTunes Connect.

To use Reporter, open a command line in a tool like Terminal in OS X, and change to the directory of the Reporter.jar file. Then, use any of the commands described in this guide—like getReport—using the syntax below.

$ java -jar Reporter.jar p=[properties file] a=[account number] m=["Normal"|"Robot.XML"] Sales.[command]
$ java -jar Reporter.jar p=[properties file] a=[account number] m=["Normal"|"Robot.XML"] Finance.[command]
Commands for Sales and Trends begin with “Sales.” Commands for Payments and Financial Reports begin with “Finance.”

