Appium Platform Support
======

Appium supports a variety of platforms and testing modalities (native, hybrid, web, real devices, simulators, etc...). This document is designed to make explicit the level of support and requirements for each of these.

iOS Support
------
See [Running on OS X: iOS](running-on-osx#ios) for iOS requirements and setup instructions.

* Versions: 6.1, 7.0, and 7.1
* Devices: iPhone Simulator, iPad Simulator, and real iPhones and iPads
* Native app support: Yes, with debug version of .app (simulator), or correctly-signed .ipa (real devices). Underlying support is provided by Apple's [UIAutomation](https://developer.apple.com/library/ios/documentation/DeveloperTools/Reference/UIAutomationRef/_index.html) framework.
* Mobile web support: Yes, via automation of mobile Safari. For real devices, ios-webkit-remote-debugger is required, and automation of native aspects of the Safari interface is not possible. See the [mobile web doc](mobile-web) for instructions.
* Hybrid support: Yes. For real devices, ios-webkit-remote-debugger is required. See the [hybrid doc](hybrid) for instructions.
* Support for automating multiple apps in one session: No
* Support for automating multiple devices simultaneously: No
* Support for automating vendor-provided or third-party apps: Only vendor-provided apps (Preferences, Maps, etc...), and only on the simulator

Android Support
------
See [Running on OS X: Android](running-on-osx#android), [Running on Windows](running-on-windows), or [Running on Linux](running-on-linux) for Android requirements and setup instructions.

* Versions: 2.3 and up
  * Versions 4.2 and up are supported via Appium's own [UiAutomator](http://developer.android.com/tools/help/uiautomator/index.html) libraries. This is the default automation backend.
  * Versions 2.3 through 4.3 are supported via Appium's bundled version of [Selendroid](http://selendroid.io), which utilizes [Instrumentation](http://developer.android.com/reference/android/app/Instrumentation.html). Selendroid has a different set of commands than the default Appium (though this is rapidly being minimized) and a different support profile. To access this automation backend, use the `automationName` capability with the value `Selendroid`.
* Devices: Android emulators and real Android devices
* Native app support: Yes
* Mobile web support: Yes (but not when using Selendroid backend). Automation is effected using a bundled [Chromedriver](https://code.google.com/p/selenium/wiki/ChromeDriver) server as a proxy. With 4.2 and 4.3, automation works on official Chrome browser or Chromium only. With 4.4+, automation also works on the built-in "Browser" app. Chrome/Chromium/Browser must already be installed on the device under test. See the [mobile web doc](mobile-web) for instructions.
* Hybrid support: Yes. See the [hybrid doc](hybrid) for instructions.
  * With default Appium automation backend: versions 4.4 and up
  * With Selendroid automation backend: versions 2.3 and up
* Support for automating multiple apps in one session: Yes (but not when using the Selendroid backend)
* Support for automating multiple devices simultaneously: Yes, though Appium must be started using different ports for the server parameters `--port`, `--bootstrap-port` (or `--selendroid-port`) and/or `--chromedriver-port`. See the [server args doc](server-args) for more information on these parameters.
* Support for automating vendor-provided or third-party apps: Yes (but not when using the Selendroid backend)
