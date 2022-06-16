
# iOS Chat SDK Release Notes


<details open markdown="block">
<summary> Version 4.0.2 </summary>

# Version 4.0.2
#### `pre-release`   
Release date:  14 Jun 2022
___

### What's new 

- Chat configurations maintenance improvements. Separated logic settings from UI related configurations.
- Loaded messenger chat configurations and applied basic UI configurations on displayed messages.
- Messenger chat engine creation and support.
- Integration with Transport SDK version 1.2.1.

### Breaking changes
- ChatHandler manages the chat configurations with `ConfigurationRepository`.
- Accessing Transport SDK from new Messenger SDK and not directly from `MessengerHandler`.

---

### Dependencies 

👉 To get latest version:

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
- Static links remove and pointing to public cocoapods spec.
- UI layer was moved into container.
- Integration with Transport SDK version 1.1.14.
- Error Handling Optimizations.

--- 

### Dependencies 

👉 To get latest version:

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
- Full bitcode support support.
- Initial chat creation. 

### Breaking Changes
- Modules namespacing and packages were renamed with `GenesysCloud` prefix.

---

### Dependencies 

👉 To get latest version:

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