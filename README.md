
# @master_jacky/react-native-vpn-detect

> **⚠️ Important Notice**: This is a community-maintained backup of the original `react-native-vpn-detect` package. I am **NOT** the original author. This package is maintained for backup purposes with deep gratitude to the original author **leekuo**.

**Original Author**: [leekuo](https://github.com/leekuo)  
**Original Repository**: [react-native-vpn-detect](https://github.com/leekuo/react-native-vpn-detect)

A React Native library for detecting VPN and Proxy connections.

## Getting started

```bash
npm install @master_jacky/react-native-vpn-detect --save
```

or

```bash
yarn add @master_jacky/react-native-vpn-detect
```

### Mostly automatic installation (React Native < 0.60)

`$ react-native link @master_jacky/react-native-vpn-detect`

### Auto-linking (React Native >= 0.60)

For React Native 0.60 and above, the package will be automatically linked. Just run:

```bash
cd ios && pod install
```

### Manual installation


#### iOS

1. In XCode, in the project navigator, right click `Libraries` ➜ `Add Files to [your project's name]`
2. Go to `node_modules` ➜ `@master_jacky/react-native-vpn-detect` and add `RNNativeVpnDetect.xcodeproj`
3. In XCode, in the project navigator, select your project. Add `libRNNativeVpnDetect.a` to your project's `Build Phases` ➜ `Link Binary With Libraries`
4. Run your project (`Cmd+R`)

#### Android

1. Open up `android/app/src/main/java/[...]/MainActivity.java`
  - Add `import com.reactlibrary.RNNativeVpnDetectPackage;` to the imports at the top of the file
  - Add `new RNNativeVpnDetectPackage()` to the list returned by the `getPackages()` method
2. Append the following lines to `android/settings.gradle`:
  	```
  	include ':master_jacky_react-native-vpn-detect'
  	project(':master_jacky_react-native-vpn-detect').projectDir = new File(rootProject.projectDir, 	'../node_modules/@master_jacky/react-native-vpn-detect/android')
  	```
3. Insert the following lines inside the dependencies block in `android/app/build.gradle`:
  	```
      implementation project(':master_jacky_react-native-vpn-detect')
  	```


## Usage

```javascript
// Import Library
import Security from "@master_jacky/react-native-vpn-detect";

// Example Usage
async function checkSecurity() {
	try {
		const detectVPN = await Security.detectVPN();
		const detectProxy = await Security.detectProxy();
		
		console.log('VPN detected:', detectVPN);
		console.log('Proxy detected:', detectProxy);
	} catch (error) {
		console.error('Error detecting VPN/Proxy:', error);
	}
}

checkSecurity();
```

## API

### `detectVPN()`
Returns a Promise that resolves to a boolean indicating whether a VPN connection is detected.

### `detectProxy()`
Returns a Promise that resolves to a boolean indicating whether a Proxy connection is detected.

## License

MIT License - see the [LICENSE](LICENSE) file for details.

## Credits

**Original Author**: [leekuo](https://github.com/leekuo)  
**Original Repository**: [react-native-vpn-detect](https://github.com/leekuo/react-native-vpn-detect)

This package is maintained as a community backup with gratitude to the original author.
