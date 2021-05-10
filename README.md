
# react-native-custom-select-text

## Demo

### Android

<img src="https://github.com/Astrocoders/react-native-selectable-text/raw/master/Demo/demo_android.gif" width="350px" />

### iOS

<img src="https://user-images.githubusercontent.com/16995184/54835973-055e7480-4ca2-11e9-8d55-c4f7a67c2847.gif" width="350px" />

## Usage

```javascript
import { SelectableText } from "react-native-custom-select-text";

<SelectableText
  menuItems={['View', 'Edit', 'Delete']}
  onSelection={({ eventType, content, selectionStart, selectionEnd }) => {
    // call your function
  }}
  highlights={[{id: 'lov', start: 2, end: 6}, {id: 'Cha', start: 11, end: 15}]}
  onHighlightPress={id => {
    console.log('id : ', id);
    // call your function
  }}
  highlightColor={'yellow'}
  value="I love Bao Chau"
/>;
```

## Getting started

`$ npm install @astrocoders/react-native-selectable-text --save`

### Mostly automatic installation

`$ react-native link @astrocoders/react-native-selectable-text`

### Manual installation

#### iOS - Binary Linking (Alternative 1)

1. In XCode, in the project navigator, right click `Libraries` ➜ `Add Files to [your project's name]`
2. Go to `node_modules` ➜ `@astrocoders/react-native-selectable-text` and add `RNSelectableText.xcodeproj`
3. In XCode, in the project navigator, select your project. Add `libRNSelectableText.a` to your project's `Build Phases` ➜ `Link Binary With Libraries`
4. Run your project (`Cmd+R`)<

#### iOS - Pods (Alternative 2)

1. Add `pod 'RNSelectableText', :path => '../node_modules/@astrocoders/react-native-selectable-text/ios/RNSelectableText.podspec'` to your projects podfile
2. run `pod install`

#### Android

1. Open up `android/app/src/main/java/[...]/MainActivity.java`

- Add `import com.astrocoders.selectabletext.RNSelectableTextPackage;` to the imports at the top of the file
- Add `new RNSelectableTextPackage()` to the list returned by the `getPackages()` method

2. Append the following lines to `android/settings.gradle`:
   ```
   include ':react-native-selectable-text'
   project(':react-native-selectable-text').projectDir = new File(rootProject.projectDir, 	'../node_modules/@astrocoders/react-native-selectable-text/android')
   ```
3. Insert the following lines inside the dependencies block in `android/app/build.gradle`:
   ```
     compile project(':react-native-selectable-text')
   ```

## Props
| name | description | type | default |
|--|--|--|--|
| **value** | text content | string | "" |
| **onSelection** | Called when the user taps in a item of the selection menu | ({ eventType: string, content: string, selectionStart: int, selectionEnd: int }) => void | () => {} |
| **menuItems** | context menu items | array(string) | [] |
| **style** | additional styles to be applied to text | Object | null |
| **highlights** | array of text ranges that should be highlighted with an optional id | array({ id: string, start: int, end: int }) | [] |
| **highlightColor** | highlight color |string | null |
| **onHighlightPress** | called when the user taps the highlight  |(id: string) => void | () => {} |
| **appendToChildren** | element to be added in the last line of text | ReactNode | null |
| **TextComponent** | Text component used to render `value` | ReactNode | <Text> |
| **textValueProp** | text value prop for TextComponent. Should be used when passing TextComponent. Defaults to 'children' which works for <Text> | string | 'children' |
| **textComponentProps** | additional props to pass to TextComponent | object | null |

