# React Native: A Guide
Contributions always welcome!

## Table of contents
- [General Issues](#general-issues)
- [Build fails](#build-fails)
- [Credits](#credits)

---

## General Issues

#### Print: Entry, ":CFBundleIdentifier", Does Not Exist
There's an issue open in the react-native tracker [which has a bunch of suggestions.](https://github.com/facebook/react-native/issues/7308)
```
$ lsof -n -i4TCP:8081
$ kill - 9 YOUR_PID_HERE // (or whichever one is listed)
```
```
$ react-native upgrade
```

---

#### No bundle URL present
Keep simulator and packager open
```
$ yarn / npm install (sometimes necessary)
$ react-native run-ios/android
```
---

#### Simulator shows blank screen

Keep simulator and packager open.
```
$ react-native run-ios/android
```

---

#### Simulator getting a black screen
Go to simulator - `Hardware > Erase all content and settings`


---

## Build Fails

#### PhaseScriptExecution Bundle\ React\ Native\ code\ and\ images build/Build/Intermediates/myApp.build/Debug-iphonesimulator/myApp.build/Script-00DD1BFF1BD5951E006B06BC.sh

In Build Phases > Bundle React Native code and images > change `../node_modules/react-native/packager/react-native-xcode.sh` to `../node_modules/react-native/scripts/react-native-xcode.sh`

In case you've initiated a project with react-native 0.46, and then downgraded react-native to 0.45, change in your `ios/${Project}.xcodeproj/project.pbxproj` next lines:
* from `export NODE_BINARY=node\n../node_modules/react-native/scripts/react-native-xcode.sh`
* to `export NODE_BINARY=node\n../node_modules/react-native/packager/react-native-xcode.sh`
https://github.com/facebook/react-native/issues/14935

---

#### The request was denied by service delegate (SBMainWorkspace) for reason: NotFound ("Application "com.myDomain.MyApp" is unknown to FrontBoard").**
Here on [some solutions on StackOverflow](https://stackoverflow.com/questions/37939749/xcode-8-messages-template-application-error-on-ios-simulator). 
This error occurs when MyApp is deleted (manually) in the simulator.
* Delete ios/build folder
* `$ react-native run-ios`

## Credits

This repository is maintained by [oliviachang29](https://github.com/oliviachang29). 
