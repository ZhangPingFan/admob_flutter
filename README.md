# admob_flutter
[![Build Status](https://app.bitrise.io/app/aab4844dfe687df4/status.svg?token=0rKyF3lAc5Q73hC9f3H0EQ)](https://app.bitrise.io/app/aab4844dfe687df4)
[![version](https://img.shields.io/badge/Awesome-Flutter-blue.svg?longCache=true&style=flat-square)](https://github.com/Solido/awesome-flutter/)
[![version](https://img.shields.io/pub/v/admob_flutter.svg?style=flat-square)](https://pub.dartlang.org/packages/admob_flutter)
[![GitHub stars](https://img.shields.io/github/stars/kmcgill88/admob_flutter.svg?style=social&label=Star)](https://github/kmcgill88/admob_flutter)
[![GitHub forks](	https://img.shields.io/github/forks/kmcgill88/admob_flutter.svg?style=social&label=Forks)](https://github/kmcgill88/admob_flutter)
[![GitHub issues](	https://img.shields.io/github/issues/kmcgill88/admob_flutter.svg?style=social&label=Issues)](https://github/kmcgill88/admob_flutter)



![Demo](https://i.imgur.com/zJC41es.gif)

A Flutter plugin that uses native platform views to show Admob banner ads!

This plugin also has support for Interstitial and Reward ads.

# Installation

- Add this to your package's pubspec.yaml file:

```yaml
dependencies:
  admob_flutter: "^1.0.0-beta.3"

```

- Install it - You can install packages from the command line:

```sh
flutter pub get
```

## Android Specific Setup
### Update your AndroidManifest.xml

Add your AdMob App ID to your app's AndroidManifest.xml file by adding the `<meta-data>` tag shown below. You can find your App ID in the AdMob UI. For android:value insert your own AdMob App ID in quotes, as shown below.

You can use these test App ID's from Admob for development:
```
Android: ca-app-pub-3940256099942544~3347511713
iOS: ca-app-pub-3940256099942544~1458002511
```

```xml
<manifest>
  <application>
    <meta-data
      android:name="com.google.android.gms.ads.APPLICATION_ID"
      android:value="ca-app-pub-3940256099942544~3347511713"/>
  </application>
</manifest>
```

## iOS Specific Setup
Update your `Info.plist` per [Firebase instructions](https://developers.google.com/admob/ios/quick-start#update_your_infoplist).
```xml
<key>GADApplicationIdentifier</key>
<string>ca-app-pub-3940256099942544~1458002511</string>
```
and add
```xml
<key>io.flutter.embedded_views_preview</key>
<true/>
```

### Initialize the plugin

First thing to do before attempting to show any ads is to initialize the plugin. You can do this in the earliest starting point of your app, your `main` function:

```dart
import 'package:admob_flutter/admob_flutter.dart';

void main() {
  WidgetsFlutterBinding.ensureInitialized();
  // Initialize without device test ids
  Admob.initialize();
  // Or add a list of test ids.
  // Admob.initialize(testDeviceIds: ['YOUR DEVICE ID']);
}
```

### Supported Platforms
- `0.3.0` >= iOS
- `0.2.0` >= AndroidX

### Supported Admob features
- Banner Ads
- Interstitial Ads
- Reward Ads
- Native Ads (Coming soon)

### Check out the [repository Wiki](https://github.com/kmcgill88/admob_flutter/wiki) for more info!

# FAQ
- Why doesn't the Admob Banner class have a dispose method?
    - TL;DR - It's called automatically for you. Longer reason see [94](https://github.com/kmcgill88/admob_flutter/issues/94)
- failed to load ad : 3
    - TL;DR - Things are working correctly, Admob didn't give you an ad. If the app id + ad unit is new, give it 24/48 hours. See:[161](https://github.com/kmcgill88/admob_flutter/issues/161) [stackoverflow](https://stackoverflow.com/questions/33566485/failed-to-load-ad-3)
- Ads are not loading
    - TL;DR - Make sure you have the correct combination of id's per platform. See:[161](https://github.com/kmcgill88/admob_flutter/issues/161)

# Pull Requests

I welcome and encourage all pull requests. Here are some basic rules to follow to ensure timely addition of your request:

1.  Match the document style as closely as possible.
2.  Please keep PR titles easy to read and descriptive of changes, this will make them easier to review/merge.
3.  Pull requests _must_ be made against `master` branch for this repository.
4.  Check for existing [issues](https://github.com/kmcgill88/admob_flutter/issues) first, before filing an issue.
5.  Have fun!
