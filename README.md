
# react-native-simple-share

## Getting started

`$ npm install react-native-simple-share --save`

### Mostly automatic installation

`$ react-native link react-native-simple-share`

### Manual installation


#### Android

1. Open up `android/app/src/main/java/[...]/MainActivity.java`
  - Add `import com.reactnativecommunity.modules.share.RNSimpleSharePackage;` to the imports at the top of the file
  - Add `new RNSimpleSharePackage()` to the list returned by the `getPackages()` method
2. Append the following lines to `android/settings.gradle`:
  	```
  	include ':react-native-simple-share'
  	project(':react-native-simple-share').projectDir = new File(rootProject.projectDir, 	'../node_modules/react-native-simple-share/android')
  	```
3. Insert the following lines inside the dependencies block in `android/app/build.gradle`:
  	```
      compile project(':react-native-simple-share')
  	```


## Usage
```javascript
import RNSimpleShare from 'react-native-simple-share';

// TODO: What to do with the module?
RNSimpleShare;
```
  