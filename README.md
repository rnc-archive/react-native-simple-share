# react-native-simple-share

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
import React, { Component } from "react";
import { View, Button } from "react-native";
import SimpleShare from "react-native-simple-share";

export default class ShareExample extends Component {
  onShare = async () => {
    try {
      const result = await SimpleShare.share({
        message:
          "React Native | A framework for building native apps using React"
      });

      if (result.action === SimpleShare.sharedAction) {
        if (result.activityType) {
          // shared with activity type of result.activityType
          console.log("result", result);
        } else {
          // shared
          console.log("result", result);
        }
      } else if (result.action === SimpleShare.dismissedAction) {
        // dismissed
        console.log("dismissed");
      }
    } catch (error) {
      console.log("error", error.message);
    }
  };

  render() {
    return (
      <View
        style={{
          backgroundColor: "white",
          flex: 1,
          justifyContent: "center",
          alignItems: "center"
        }}
      >
        <Button title="Share" onPress={this.onShare}>
          Share
        </Button>
      </View>
    );
  }
}
```
