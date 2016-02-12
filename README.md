OneSignal iOS Push Notification Plugin
====================================

## Requirements

- iOS 8.0+ / Mac OS X 10.9+ / tvOS 9.0+ / watchOS 2.0+
- Xcode 7.2+

## Installation

### Carthage

[Carthage](https://github.com/Carthage/Carthage) is a decentralized dependency manager that builds your dependencies and provides you with binary frameworks.

You can install Carthage with [Homebrew](http://brew.sh/) using the following command:

```bash
$ brew update
$ brew install carthage
```

To integrate OneSignalKit into your Xcode project using Carthage, specify it in your `Cartfile`:

```ogdl
github "drajak/OneSignalKit" ~> 2.0
```

Run `carthage update` to build the framework and drag the built `OneSignalKit.framework` into your Xcode project.

### Manually

If you prefer not to use either of the aforementioned dependency managers, you can integrate OneSignalKit into your project manually.

#### Embedded Framework

- Open up Terminal, `cd` into your top-level project directory, and run the following command "if" your project is not initialized as a git repository:

```bash
$ git init
```

- Add OneSignalKit as a git [submodule](http://git-scm.com/docs/git-submodule) by running the following command:

```bash
$ git submodule add https://github.com/drajak/OneSignalKit.git
```

- Open the new `OneSignalKit` folder, and drag the `OneSignalKit.xcodeproj` into the Project Navigator of your application's Xcode project.

    > It should appear nested underneath your application's blue project icon. Whether it is above or below all the other Xcode groups does not matter.

- Select the `OneSignalKit.xcodeproj` in the Project Navigator and verify the deployment target matches that of your application target.
- Next, select your application project in the Project Navigator (blue project icon) to navigate to the target configuration window and select the application target under the "Targets" heading in the sidebar.
- In the tab bar at the top of that window, open the "General" panel.
- Click on the `+` button under the "Embedded Binaries" section.
- You will see two different `OneSignalKit.xcodeproj` folders each with two different versions of the `OneSignalKit.framework` nested inside a `Products` folder.

    > It does not matter which `Products` folder you choose from, but it does matter whether you choose the top or bottom `OneSignalKit.framework`. 
    
- Select the top `OneSignalKit.framework` for iOS and the bottom one for OS X.

    > You can verify which one you selected by inspecting the build log for your project. The build target for `OneSignalKit` will be listed as either `OneSignalKit iOS` or `OneSignalKit OSX`.

- And that's it!

> The `OneSignalKit.framework` is automagically added as a target dependency, linked framework and embedded framework in a copy files build phase which is all you need to build on the simulator and a device.

---
## Usage 
### Setup

In AppDelegate
```swift
import OneSignalKit
```
```
    func application(application: UIApplication, didFinishLaunchingWithOptions launchOptions: [NSObject: AnyObject]?) -> Bool {
        // Override point for customization after application launch.
        let oneSignal = OneSignal(launchOptions: launchOptions, appId: "#YOUR_APP_ID_HERE", handleNotification: nil)
        oneSignal.enableInAppAlertNotification(true)
        return true
    }
```

## Additional Information

For bridgin information and more please read the documentation below.

- See http://documentation.onesignal.com/v2.0/docs/using-onesignal-in-your-ios-app for documentation.
- See http://documentation.onesignal.com/v2.0/docs/ios-sdk-api for OneSignal API documentation.

## License
OneSingalKit is released under the MIT license. See LICENSE for details.

