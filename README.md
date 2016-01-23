# quickstart-parse-SDK
1.
Add the SDKs to your app
Drag the Parse.framework and Bolts.framework you downloaded into your Xcode project folder target.
Make sure the "Copy items to destination's group folder" checkbox is checked.

2.Add the dependencies
Click on Targets → Your app name → and then the 'Build Phases' tab.
Expand 'Link Binary With Libraries' as shown.
![image](https://www.parse.com/images/apps/quickstart/demo_ios_existing2.png?9b5c392)

Click the + button in the bottom left of the 'Link Binary With Libraries' section and add the following libraries:


AudioToolbox.framework<br>
CFNetwork.framework<br>
CoreGraphics.framework<br>
CoreLocation.framework<br>
QuartzCore.framework<br>
Security.framework<br>
StoreKit.framework<br>
SystemConfiguration.framework<br>
libz.tbd<br>
libsqlite3.tbd<br>

Note: This is a comprehensive list of dependencies for a typical app. You may be able to omit some of these if you are not using the -ObjC linker flag or if you do not plan to implement Location Services or In-App Purchases, for example.


3.
Connect your app to Parse
Before continuing, select your Parse app from the menu at the right. These steps are for your "loginTest" app.
Open up your AppDelegate.swift and update it like so:

```
import Parse
import Bolts
 
@UIApplicationMain
class AppDelegate: UIResponder, UIApplicationDelegate {
 
  func application(application: UIApplication, didFinishLaunchingWithOptions launchOptions: [NSObject: AnyObject]?) -> Bool {
    // [Optional] Power your app with Local Datastore. For more info, go to
    // https://parse.com/docs/ios/guide#local-datastore
    Parse.enableLocalDatastore()
 
    // Initialize Parse.
    Parse.setApplicationId("auCsZ2bzM7gS6YOsoU1pOULMgJHGSwtaJ1KW6oxR",
      clientKey: "6SXSEyvLGFnRXZAJYRJp5avdsKefuqJpUdoano6I")
 
    // [Optional] Track statistics around application opens.
    PFAnalytics.trackAppOpenedWithLaunchOptions(launchOptions)
 
    // ...
}
 
// ...
```

4.
<strong>Compile and run!</strong>
