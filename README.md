#Realtime Messaging iOS example for React-Native

This example is a simple app that allows you to send and receive messages between devices using React Native and the Realtime Messaging React Native SDK.
 
[Realtime Cloud Messaging](http://framework.realtime.co/messaging) is a highly-scalable pub/sub message broker, allowing you to broadcast messages to millions of users, reliably and securely. It's all in the cloud so you don't need to manage servers.

[React Native](http://facebook.github.io/react-native/) enables you to build world-class application experiences on native platforms using a consistent developer experience based on JavaScript and React.


##How to test this demo application

*	Create a new react-native project using the following command `react-native init RealtimeRCT`

*	Replace index.ios.js for the one provided in this repository.

*	Install RCTRealtimeMessaging plugin as instructed below: 
	*	On the terminal, go to `PROJECT_DIR/node_modules/react-native`

	* Execute

		 `npm install --save react-native-realtimemessaging-ios`

	* Drag `RCTRealtimeMessaging.xcodeproj` from the `node_modules/react-native-realtimemessaging-ios` folder into your XCode project. Click on the project 	in XCode, goto Build Phases then Link Binary With Libraries and add 	`libRCTRealtimeMessaging.a`

	* Drag `RCTRealtimeMessaging.js` to the root of your project.
	
* 	To configure your react-native project to receive push notifications you must follow [this guide](http://messaging-public.realtime.co/documentation/starting-guide/mobilePushAPNS.html) for the iOS platform.
After this process you must drag `AppDelegate+RealtimeRCTPushNotifications(.m, .h)` category from RCTRealtimeMessaging plugin folder to your project, where AppDelegate class is, and you are ready to go.

##Testing the custom push notifications delivery

To test the Realtime Custom Push Notifications you need to use the Realtime Mobile Push REST API to send a custom push with the following POST to `https://ortc-mobilepush.realtime.co/mp/publish`

	{
	   "applicationKey": "[INSERT YOUR APP KEY]",
	   "privateKey": "[INSERT YOUR APP PRIVATE KEY]",
	   "channel" : "[INSERT CHANNEL TO SEND PUSH]",
	   "message" : "[INSERT ALERT TEXT]",
	    "payload" : "{
	     \"sound\" : \"default\",
	     \"badge\" : \"1\",
	     \"name\" : \"Joe\",
	     \"age\" : \"48\"
	    }"
	}

Have fun pushing!

	
## Authors
Realtime.co
	

