
# iOS Messenger SDK Release Notes


<details open markdown="block">
<summary> Version 4.0.2 </summary>

# Version 4.0.2
#### `pre-release`   
Release date:  14 Jun 2022
___

### What's new 

- Messenger configurations maintenance improvements. Separated logic settings from UI related configurations.
- Loaded messenger chat configurations and applied basic UI configurations on displayed messages.
- Messenger chat engine creation and support.
- Integration with Transport SDK version 1.2.1.

### Breaking changes
- From now on, `ChatHandler` manages the messenger configurations with `ConfigurationRepository`.
- Transport SDK is now accessed from new `GenesysCloudMessengerSDK` and not directly from `MessengerHandler`.

---

### Dependencies 

👉 To get the latest version:

- Update Podfile with:

```
source 'https://github.com/genesys/dx-sdk-specs-dev'
source 'https://github.com/CocoaPods/Specs'
```

- Run:
  
```ruby
pod update 
```

</details>

---

</details>
<details close markdown="block">
<summary> Version 4.0.1 </summary>

# Version 4.0.1
#### `pre-release`
Release date: 20 Feb 2022

### What's new 
- Removed static links and linked to public CocoaPods specifications.
- UI layer was moved into container.
- Integration with Transport SDK version 1.1.14.
- Optimized Error Handling.

--- 

### Dependencies 

👉 To get the latest version:

- Update Podfile with:

```
source 'https://github.com/genesys/dx-sdk-specs-dev'
source 'https://github.com/CocoaPods/Specs'
```

- Run:
  
```ruby
pod update 
```

</details>

---

<details close markdown="block">

<summary> Version 4.0.0 </summary>

# Version 4.0.0
#### `pre-release`
Release date: 18 Feb 2022

### What's new 
- Full bitcode support.
- Initial messenger creation. 

### Breaking Changes
- Namespacing modules and packages were renamed with `GenesysCloud` prefix.

---

### Dependencies 

👉 To get the latest version:

- Update Podfile with:

```
source 'https://github.com/genesys/dx-sdk-specs-dev'
source 'https://github.com/CocoaPods/Specs'
```

- Run:
  
```ruby
pod update 
```

</details>