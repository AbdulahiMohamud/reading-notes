# Android Fundementals

- Andoird app languages : Kotlin, Java, C++
- .apk is the suffix for an android package
- .aab is the suffix for an android bundle
- android OS is an multi user Linux system each app is a different user
- Each app is assigned a new user id
- Each app runs on its own VM
- Apps can have the same user ID to share files and signed with the same cert

### App components

- 4 types of App Components:

- Activities - an entry point for interacting with user
- Services - is a general purpose entry point for keeping an app running in the background
- Bound services run because some other app (or the system)
- Broadcast receivers
- Content Providers - manages a shared set of app data that you can store in the file system

### Activating Components

- Activities, services, broadcasts receivers are activated asynchronously message called intent
- Intent is an object which defines a message to activate either a specific component
- Intent defines whether to view or send something
- Content Providers are not activiated by intent
- Content rpoviders use Content Resolvers
- Each activity has its own method to 


### Manifest File

- AndroidManifest.xml
- All components must be declared in the manifest file
- <activity> elements for activities.
- <service> elements for services.
- <receiver> elements for broadcast receivers.
- <provider> elements for content providers.

````Java
//Example of intent and activity
<manifest ... >
        ...
<application ... >
    <activity android:name="com.example.project.ComposeEmailActivity">
        <intent-filter>
            <action android:name="android.intent.action.SEND" />
            <data android:type="*/*" />
            <category android:name="android.intent.category.DEFAULT" />
        </intent-filter>
    </activity>
</application>
</manifest>
````
[Credit](https://developer.android.com/guide/components/fundamentals
)

### Declaring App Requirements

- Values for minSdkVersion and targetSdkVersion are set in your app module's build.gradle file
````Java
android {
  ...
  defaultConfig {
    ...
    minSdkVersion 26
    targetSdkVersion 29
  }
}

<manifest ... >
<uses-feature android:name="android.hardware.camera.any"
        android:required="true" />
        ...
</manifest>
````
[Credit](https://developer.android.com/guide/components/fundamentals
)

### App Resources

- Anything seperate from source file is in app resources
-  images, audio files.



## Reference and Citation

> ## Reference and Citation

> Joshua McCluskey