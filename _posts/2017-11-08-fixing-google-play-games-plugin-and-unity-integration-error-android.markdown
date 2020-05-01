---
layout: post
title:  "Fixing Google Play Games plugin and Unity integration error - Android"
categories: Programming
tags: Unity3D
---

Recently i was having multiple issues with google play games plugin integration in Unity. It was not working at all. After spending the couple of hours in it, i was able to fix the issue. This is a note to myself as well for others who are having trouble with the integration.

I was using <a href="https://github.com/googleads/googleads-mobile-unity/releases">Admob plugin</a> along with Google <a href="https://github.com/playgameservices/play-games-plugin-for-unity/tree/master/current-build">Play Games plugin</a>. In the process of fixing the error i got different kinds of error. Some error was due to the import while some was due to the Authentication issues from the play game service. I will discuss about these both.

First of all we have to be sure that the plugin is well integrated in our project. This means that the plugin is working well and there is no error in integration.

First of all, I would recommend you to use the latest version of Unity and all the plugins you use in your project. This will fix the errors that arise due to different version of SDK issues. For instance i was having the following issue and when i deleted the plugins and re-imported the latest version, the error was fixed.

```
11-06 14:28:17.000 22817-4757/? W/GamesServiceBroker: Client connected with SDK 11411000, Services 11745448, and Games 52250048
```

Secondly, always give a closer look to the error message

```
Error building Player: CommandInvokationFailure: Failed to re-package resources. See the Console for details.
```

It takes me more time than usual to fix the error if i do not read the error message well. Read it until you understand it. There is always the solution in this error. For example: There might be colliding with the two files of different version if you are using multiple plugins in single project along with the Google Play Game plugin.

Finally if you are able to build and run the project without any error and still it is not working then we need to see the "logcat". For example you have a button and when the button is clicked you want to open the Leaderboard, but the leaderboard is not working then in this case we have to see the logcat for the error. Logcat is very handy tool to observe the error message thrown during the runtime.

First of all open your app and then click on the leaderboard button or achievement whichever you are having issue with and then extract the logcat of your android device

Visit to <a href="https://developer.android.com/studio/command-line/logcat.html">Logcat Command-Line tool</a> page or alternatively you can watch the error in real-time from the <a href="https://developer.android.com/studio/debug/am-logcat.html">Android Studio</a>.

The logcat will have a error message which will lead you to the solution.

<h3>Error due to Authentication issue</h3>
Let us talk about the error occurring due to the Authentication issue. This issue normally occur due to the SHA-1 hash code not matching that of your app and the one you've authorized in the developer console.

First of all visit <a href="https://play.google.com/apps/publish/">Google Play Developers</a>, select the App and goto <span style="color:#008000;">Release Management</span> &gt;&gt; <span style="color:#008000;">App signing</span> and note the SHA-1 certificate for both the App Signing and Upload certificate. The app signing certificate works while you build and run app on your mobile device and the upload certificate works for the apk which is downloaded from the playstore. So, you need to create OAuth 2.0 client ID for both.

Next, visit <a href="https://console.developers.google.com/">Developer Console</a>. Select the app and click on <span style="color:#008000;">Create credentials</span> &gt;&gt; <span style="color:#008000;">OAuth client ID</span> and select <span style="color:#008000;">Android</span>.

Give any name to it and paste the SHA-1 Signing certificate from the Google Play Console and enter the package name. Similarly repeat this step for SHA-1 upload certificate. We are providing both certificate because we need to test the app before uploading to Google Play. Also note that if you are provided with the "Duplicate Fingerprint" message then you have already set up, you can skip that certificate.

Lastly, you have to Link the app to Google Play Console. Goto <a href="https://console.developers.google.com/">Developer Console</a>, Click <span style="color:#008000;">Game services</span>. Select the app and click on <span style="color:#008000;">Linked apps</span>. Next click on <span style="color:#008000;">Link another app</span> and select <span style="color:#008000;">Android</span>, enter the details and click on <span style="color:#008000;">Save and continue</span>.

You may repeat this steps in some cases. But if it says already authorized then no need to authorize/link your app again.

So, i hope reading this post have helped you to fix the google play game service plugin integration issue in Unity for your android app.
