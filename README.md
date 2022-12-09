# ZebraProfileManagerCommand
A class that executes EMDK's profile manager commands.... I needed to refactor some code used in different projects... so why not ?

Add Jitpack repository to your dependencies:
```javascript
allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
```

add dependency to your project build.gradle:
```javascript
dependencies {
          ...
	        implementation 'com.github.ltrudu:ZebraProfileManagerCommand:+'
          ...
	}
```

Update your manifest to add permissions, query and use library (in the application element):

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">
    <uses-permission android:name="com.zebra.provider.READ"/>
    <queries>
        <package android:name="com.symbol.emdk.emdkservice" />
    </queries>

    <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.MyApplication"
        tools:targetApi="31" >
        <uses-library android:name="com.symbol.emdk"/>
    </application>

</manifest>
```

See Critical Permission Helper for usage:
https://github.com/ltrudu/CriticalPermissionsHelper
