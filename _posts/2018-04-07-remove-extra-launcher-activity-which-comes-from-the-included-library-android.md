---
published: true
layout: post
category: android
title: Remove extra launcher activity which comes from the included library android
---
ProgressWheel's example activity has launcher intent-filter so it creates two app icons in the applications drawer which is quite ugly. 

To eliminate this we need to remove the intent-filter from the example activity. We are going to use manifest merger of Android which is pretty cool. Android merges all of the manifest files and at the end creates one manifest file.

It's under intermediates -> manifests -> 

Don't remove module name from .idea -> modules.xml it breaks everything. Bad bad bad. There is one solution in SO. Don't do it.

<activity
    android:name="com.todddavies.components.progressbar.main"
    android:label="@string/app_name" >
    <intent-filter tools:node="remove">
        <action android:name="android.intent.action.MAIN" />

        <category android:name="android.intent.category.LAUNCHER" />
    </intent-filter>
</activity>