# Nearby-Places Android

This repo provides an example app called Nearby Places for Android devices built with the [ArcGIS Runtime SDK for Android](https://developers.arcgis.com/android/).  With some minor customization, you can change the types of places displayed or simply use the app as is.

## Features
 * Geocoding with categories
 * Device location
 * Calculating bearing and distance
 

## Development Instructions
This Nearby-Places repo is an Android Studio Project and App Module that can be directly cloned and imported into Android Studio. In addition, you'll need to follow the steps below to obtain your client id and redirect uri. Both are required for leveraging all the features of the app.

* Login to [ArcGIS for Developers](https://developers.arcgis.com/) and [register](https://developers.arcgis.com/applications/#/) your app.  

![](Register1.png)
* Once you've registered your version of the maps-app, grab a copy of the client id from the registration and set the client id in the applications your nearby-android/gradle.properties file.  Set the redirect uri in the nearby-android/gradle.properties file to `my-ags-app://auth`.  This redirect uri is the default redirect for `https://www.arcgis.com`.

```
CLIENT_ID = YOUR_CLIENT_ID;
OAUTH_REDIRECT_ID = "my-ags-app://auth"
```
* As part of the registration process, you will need to add a redirect uri for your app.  Navigate to the Redirect URIs section at the bottom of the registration page and 

![](Register2.png)
* Note that the scheme for the `DefaultOAuthIntentReceiver` in the Android Manifest file is derived from the redirect uri.
```xml
        <activity
            android:name="com.esri.arcgisruntime.security.DefaultOAuthIntentReceiver"
            android:label="OAuthIntentReceiver"
            android:launchMode="singleTask">
            <intent-filter>
                <action android:name="android.intent.action.VIEW"/>
                <category android:name="android.intent.category.DEFAULT"/>
                <category android:name="android.intent.category.BROWSABLE"/>
  
                <data android:scheme="my-ags-app"/>
            </intent-filter>
        </activity>
 ```

### Fork the repo
**Fork** the [Nearby Places Android](https://github.com/Esri/nearby-android/fork) repo.

### Clone the repo
Once you have forked the repo, you can make a clone

#### Command line Git
1. [Clone the Nearby Places repo](https://help.github.com/articles/fork-a-repo#step-2-clone-your-fork)
2. ```cd``` into the ```nearby-android``` folder
3. Make your changes and create a [pull request](https://help.github.com/articles/creating-a-pull-request)

### Configuring a Remote for a Fork
If you make changes in the fork and would like to [sync](https://help.github.com/articles/syncing-a-fork/) those changes with the upstream repository, you must first [configure the remote](https://help.github.com/articles/configuring-a-remote-for-a-fork/). This will be required when you have created local branches and would like to make a [pull request](https://help.github.com/articles/creating-a-pull-request) to your upstream branch.

1. In the Terminal (for Mac users) or command prompt (fow Windows and Linus users) type ```git remote -v``` to list the current configured remote repo for your fork.
2. ```git remote add upstream https://github.com/Esri/nearby-android.git``` to specify new remote upstream repository that will be synced with the fork. You can type ```git remote -v``` to verify the new upstream.

If there are changes made in the Original repository, you can sync the fork to keep it updated with upstream repository.

1. In the terminal, change the current working directory to your local project
2. Type ```git fetch upstream``` to fetch the commits from the upstream repository
3. ```git checkout master``` to checkout your fork's local master branch.
4. ```git merge upstream/master``` to sync your local `master' branch with `upstream/master`. **Note**: Your local changes will be retained and your fork's master branch will be in sync with the upstream repository.

## Requirements
* [JDK 6 or higher](http://www.oracle.com/technetwork/java/javase/downloads/index.html)
* [Android Studio](http://developer.android.com/sdk/index.html)

## Resources
* [Nearby Places](https://github.com/Esri/nearby-android/blob/nearby-app/README.md)
* [ArcGIS Runtime SDK for Android Developers Site](https://developers.arcgis.com/android/)
* [ArcGIS Mobile Blog](http://blogs.esri.com/esri/arcgis/category/mobile/)
* [ArcGIS Developer Blog](http://blogs.esri.com/esri/arcgis/category/developer/)
* [Google+](https://plus.google.com/+esri/posts)
* [twitter@ArcGISRuntime](https://twitter.com/ArcGISRuntime)
* [twitter@esri](http://twitter.com/esri)

## Issues
Find a bug or want to request a new feature enhancement?  Let us know by submitting an issue.

## Contributing
Anyone and everyone is welcome to [contribute](https://github.com/Esri/nearby-android/blob/master/CONTRIBUTING.md). We do accept pull requests.

1. Get involved
2. Report issues
3. Contribute code
4. Improve documentation

## Licensing
Copyright 2016 Esri

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.

A copy of the license is available in the repository's [license.txt](https://github.com/Esri/nearby-android/blob/master/license.txt) file.

For information about licensing your deployed app, see [License your app](https://developers.arcgis.com/android/guide/license-your-app.htm).

[](Esri Tags: ArcGIS Android Mobile)
[](Esri Language: Java)​