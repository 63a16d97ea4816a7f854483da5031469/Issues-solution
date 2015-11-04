#How to start an Application on startup?

>http://developer.android.com/training/scheduling/alarms.html#boot

>http://stackoverflow.com/questions/6391902/how-to-start-an-application-on-startup  

That is how to enable an activity start running after android device reboot:

Insert that code on your AndroidManifest.xml

    <uses-permission android:name="android.permission.RECEIVE_BOOT_COMPLETED" />

    <receiver android:enabled="true" android:exported="true" 
    android:name="package.yourActivityrRunOnStartup"
    android:permission="android.permission.RECEIVE_BOOT_COMPLETED">
    <intent-filter>
            <action android:name="android.intent.action.BOOT_COMPLETED" />
            <action android:name="android.intent.action.QUICKBOOT_POWERON" />
            <category android:name="android.intent.category.DEFAULT" />
    </intent-filter>
    </receiver>
    
And then insert that code on the activity you want to start first:

if (intent.getAction().equals(Intent.ACTION_BOOT_COMPLETED)){


        Intent i = new Intent(context, MainActivity.class);
        i.addFlags(Intent.FLAG_ACTIVITY_NEW_TASK);

        context.startActivity(i);
    }
Note: The call i.addFlags(Intent.FLAG_ACTIVITY_NEW_TASK); is important because the activity is launched from a context outside the activity. Without this, the activity will not start.

Also, the values android:exported and android:permission in the <receiver> tag do not seem mandatory. The app receives the event without these values. 

See the example here: 
http://developer.android.com/training/scheduling/alarms.html#boot  



    