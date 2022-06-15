# Quick start

Use this Quick start guide to set up a working chat hosted by your App.   

## System Requirements  

* [iOS 11 and above](https://developer.apple.com/library/archive/releasenotes/General/WhatsNewIniOS/Articles/iOS10.html#//apple_ref/doc/uid/TP40017084-SW1)

`platform :ios, '11.0'`

### Required resources:

* Automatic Reference Counting (ARC) is required in your project.
* [CocoaPods](https://guides.cocoapods.org/using/getting-started.html).


## Set up the SDK on your App.

Note: If you use CocoaPods on an existing Xcode project, it modifies the project file, so you may want to make a backup before doing this.

1 . Create a Podfile in the root directory of your project.

```sh
$ pod init
```

2 . Add Official CocoaPods PodSpecs repository to your Podfile:

```ruby
source 'https://github.com/CocoaPods/Specs.git'
```

3 . Add `GenesysCloud` PodSpecs repository to your Podfile:

>Note: Find the the source points to our pre-released environment below.

```ruby
source 'https://github.com/genesys/dx-sdk-specs-dev'
```

4 . Add `GenesysCloud` iOS SDK to your Podfile:
    
```ruby
pod 'GenesysCloud'
```

5 . Using *terminal*, with your project root directory as the *working path*, run:

```ruby
pod install
# pod update GenesysCloud (use this if you want to get the newly released version).
```

This action downloads all the necessary files which are required to integrate the `GenesysCloud` into your project.

> ! Now you are ready to integrate and create some chats.

---

## Create and start a basic chat 

Follow the next steps to have a basic working chat integrated to your App.

## Create new Project  

### Set Up a Project in Xcode  

1 . Open Xcode and click **start new Xcode Project**.

2 . Next, select **Single View Application** and click **Next**.

3 . In the dialog screen displayed, enter the relevant details.

### Import SDK

Go to the desired file (e.g., `ViewController.swift`) and add the line below:

```swift
import GenesysCloud
```

### Create Chat Account

Create a `MessengerAccount` and configure it with a predefined [`Messenger Deployment`](https://help.mypurecloud.com/articles/deploy-messenger/) details.

```swift
    let meesengerAccount = MessengerAccount()
    meesengerAccount.deploymentId = {DEPLOYMENT_ID}
    meesengerAccount.domain = {DOMAIN}
    meesengerAccount.tokenStoreKey = {TOKEN_STORE_KEY}
```

### Create ChatController instance

The `ChatController` is the interaction point with the SDK. You need it to create a chat.

```swift
    var chatController =  ChatController(account: meesengerAccount)
```

###  The `ViewController`should look as below.

```swift
class ViewController: UIViewController {

    var chatController: ChatController!
    var chatVC: UINavigationController!
    
    override func viewDidLoad() {
        super.viewDidLoad()
        let meesengerAccount = MessengerAccount()
        meesengerAccount.deploymentId = {DEPLOYMENT_ID}
        meesengerAccount.domain = {DOMAIN}
        meesengerAccount.tokenStoreKey = {TOKEN_STORE_KEY}

        self.chatController = ChatController(account: meesengerAccount)
        chatController.delegate = self
    }

    @objc func dismissChat(_ sender: UIBarButtonItem?) {
        self.chatController.terminate()
    }
}
```

### Display Chat View Controller by Implementing Delegate Methods  

```swift
extension ViewController: ChatControllerDelegate {
    func shouldPresentChatViewController(_ viewController: UINavigationController!) {
        viewController.modalPresentationStyle = .overFullScreen
        self.present(viewController, animated: true) { () -> Void in
            viewController.viewControllers.first?.navigationItem.leftBarButtonItem = UIBarButtonItem(title: "End Chat", style: .plain, target: self, action: #selector(ViewController.dismissChat(_:)))
        }
    }

    func didFailWithError(_ error: BLDError!) {
        print(error.error.debugDescription);
    }
}
```  

---

### Code Sample
[GenesysCloud samples](https://github.com/genesys/mobiledx-samples-ios)
