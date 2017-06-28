# React Native: A Guide

### No bundle URL present
Keep simulator and packager open
```
$ yarn / npm install (sometimes necessary)
$ react-native run-ios/android
```
### Simulator shows blanks screen

Keep simulator and packager open.
```
$ react-native run-ios/android
```
### Print: Entry, ":CFBundleIdentifier", Does Not Exist
There's an issue open in the react-native tracker [which has a bunch of suggestions.](https://github.com/facebook/react-native/issues/7308)
```
$ lsof -n -i4TCP:8081
$ kill - 9 7601 // (or whichever one is listed)
```
```
$ react-native-upgrade
```

### The request was denied by service delegate (SBMainWorkspace) for reason: NotFound ("Application "com.myDomain.MyApp" is unknown to FrontBoard").
Here on [some solutions on StackOverflow](https://stackoverflow.com/questions/37939749/xcode-8-messages-template-application-error-on-ios-simulator). 
This error occurs when MyApp is deleted (manually) in the simulator.
**Make sure your code is stored in a remote repo**
* Delete your local repo, clone it from the remote repo
* Run `yarn / npm install`
* `react-native run-ios`