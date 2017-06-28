## React Native: A Guide

### No bundle URL present
Steps to reproduce: 
```
$ react-native run-ios/run-android
```
Solution:

Keep simulator and packager open
```
$ yarn / npm install (sometimes necessary)
$ react-native run-ios/android
```
### Simulator shows blanks screen

Solution:

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