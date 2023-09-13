# FusionRNCLI
Setup the react-native - https://reactnative.dev/docs/getting-started

To create your own application using FusionCharts – with Expo
		1. Make sure you have Node.js and Git installed in your environment. Check the official Expo’s documentation for more details.
		https://docs.expo.dev/get-started/installation/
  
	2. Run the following command in Command Prompt to create a new application:
		npx create-expo-app 'AppName' e.g. - npx create-expo-app demoApp	
  
	3. Move to the previously created app folder: cd 'AppName' e.g.- demoApp
 
	4. Install needed libraries for the FusionCharts:
		npm i @unimodules/react-native-adapter
		npm i react-native-fusioncharts --force	
  
	5. Now create the "metro.config.js" in the root folder of the app and include the following code:
		const { getDefaultConfig } = require('@expo/metro-config');
		module.exports = (async () => {
			const {
			  resolver: { sourceExts, assetExts }
			} = await getDefaultConfig(__dirname)
			return {
			  transformer: {
				defaultConfig: async () => ({
				  transform: {
					experimentalImportSupport: false,
					inlineRequires: false
				  }
				})
			  },
			  resolver: {
				sourceExts,
				assetExts: [...assetExts, 'fcscript']
			  }
			}
		  })()
		  
	6. Replace the code in the "App.js" file to receive the desired chart. Example - https://github.com/fusioncharts/react-native-fusioncharts#quick-start
	7. Run the following command: expo start Expo should create a QR code in your Command Prompt window.
	8. Open the Expo Go application on your device – you should have installed it in order to run your FusionCharts app on this device.
	9. Make sure your device is on the same Wi-Fi network as the computer where you are executing Expo commands.
	10. Scan the QR code with the Expo Go scanner. The application will run on this device. It should display the charts properly.
	11. You can make changes to your code while running the application on your device: it should automatically reload after you save the changes.
 
