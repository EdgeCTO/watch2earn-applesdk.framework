# watch2earn-applesdk.framework
This is a complete Watch2Earn framework which has everything integrated including UIVIews and media resources. Just Import it in your apps and call its simple methods to implement the watch2earn feature of EdgeVideos into your streams. 

## Getting Started
To install Framework in your project, follow these steps:

- Download the [watch2earn-applesdk.framework](https://github.com/EdgeCTO/watch2earn-applesdk.framework) file from the GitHub repository.
- Drag and drop the watch2earn-applesdk.framework file into your Xcode project.
- In the "General" tab of your project's settings, scroll down to "Frameworks, Libraries, and Embedded Content".
- Click the "+" button and select the watch2earn-applesdk.framework file.
- In the "Build Phases" tab of your project's settings, add the .framework file to the "Link Binary with Libraries" section.

## Usage
### Importing Framework 
To use this Framework in your project, you'll first need to import it at the top of your main View Controller Swift file:
####swift　
```javascript
import watch2earn_applesdk
```
### Initializing Framework

Just need to call the basic functions of the Framework SDK into the app main class and initialize with your app logo link and wallets json file link into the W2EManager class which is responsible for all operations of it. It will establish all the connections with watch2earn servers. 

```swift
 let logo = URL(string: "Link to your logo")!
 let wallets = URL(string: "Link to the your get wallets api")!
 self.w2eManager = W2EManager(logoUrl:logo, jsonUrl: wallets );
```

### Use playerViewControl Method

Just call this method into your playerview and pass the AVPlayerViewController as a parameter to this method from the static w2eSdk object in the W2EManager. It is responsible for all the operations showing and overlay the ticker bar and updating its stats on your player view.

```swift
 self.avPlayerController.player = self.avPlayer
 W2EManager.w2eSdk.playerViewControl(avPlayerController: self.avPlayerController)
 self.addSubview(self.avPlayerController.view)
```
### Get W2E Setting Screen View

This function will return the W2E settings screen UIViewController you can use in your app where you want configure it. 

```swift
 let viewController = W2EManager.w2eSdk.getSettingScreen()
 view.insertSubview(viewController.view, at: 0)
 self.addChild(viewController)
 
```
