---
title: "Multi-OS Engine Release 1.1.0"
excerpt: "The first release to use Maven for the SDK distribution. Read on for the Release Highlights."
author_profile: true
layout: single
---

We are pleased to announce the Multi-OS Engine 1.1.0 release.

## What's New

This is the first release of the Multi-OS Engine that uses the new Gradle plugin and Maven based SDK distribution mechanism.

Apart from this major feature the release includes the following improvements:

* Android Studio / IDEA plugins are now distributed using the JetBrains plugin repositories.
* The MOE Gradle plugin is now on JCenter.
* The simulator launcher was replaced by a completely new implementation. It is much more stable and supports Xcode 7.3 or newer. ([Issue #4](https://github.com/multi-os-engine/multi-os-engine/issues/4))
* If the build process took too long during a debug launch, the JDWP connect timeout could be triggered. This is now fixed. ([Issue #5](https://github.com/multi-os-engine/multi-os-engine/issues/5))
* The documentation was updated ([Issue #7](https://github.com/multi-os-engine/multi-os-engine/issues/7)) 
* Various bugs with the ``Synchronize to Xcode`` function were fixed ([Issue #9](https://github.com/multi-os-engine/multi-os-engine/issues/9))
* We added the ``Keep Xcode project`` option to the Android Studio project wizard. This way, you can create new projects in a single step, where the Xcode project will be managed manually. 
* Also made some internal fixes to the project generation logic ([Issue #2](https://github.com/multi-os-engine/multi-os-engine/issues/2))

Enjoy! If you run into any issues, don't hesitate to contact us on the [MOE Forum]({{ site.data.links.forum }}).

## How to install

Please follow the instructions on the [Get Started page]({{ site.data.links.start }}).

## Where is the source code

The source code can be found on [GitHub]({{ site.data.links.github }}).

## Where to ask for help

The best place to ask for help is the [Multi-OS Engine Forum]({{ site.data.links.forum }}).

## Known Issues

### Stopping applications on device may freeze Android Studio for a few seconds. ([Issue #6](https://github.com/multi-os-engine/multi-os-engine/issues/6))

* **Workaround:** If Android Studio is seems to be completely stuck, force-quit the application.

### Launching an application on a device which was not previously trusted will fail.

* When a device is connected to a computer for the first time, the device asks whether to trust the computer or not. If the computer is not trusted at the time of launching, the launch will fail.
* **Workaround:** Trust the computer on the device and try again.

### When opening a project in Android Studio, whose run configuration is configured with special path variables, the IDE may display “xxx is undefined” fix-it.

* **Workaround:** Ignore this message.

### Starting a debug session on slower machines may fail to connect to the JDWP server. ([Issue #20](https://github.com/multi-os-engine/multi-os-engine/issues/20))

The build logic has been largely improved, and this issue now only affects a subset of users compared to earlier versions. If the launch process (installation onto device and application startup) takes up too much time then Android Studio’s JDWP connection attempts to the application may timeout.

* **Workaround:** Create a separate run configuration which connects to localhost:8000 (port 8000 is the default port as the MOE Application Run Configuration) and use that to connect to the application’s JDWP server.

### Samples and templates are missing @IBAction annotations on methods. ([Issue #15](https://github.com/multi-os-engine/multi-os-engine/issues/15))

* This annotation is needed for “Synchronize to Xcode” to work correctly.
* **Workaround:** Add annotations manually.

### Run Configurations on sample projects are not created automatically. ([Issue #16](https://github.com/multi-os-engine/multi-os-engine/issues/16))

* **Workaround:** Create them manually.

### “Synchronize to Xcode” adds stubs incorrectly ([Issue #17](https://github.com/multi-os-engine/multi-os-engine/issues/17))

* The function adds native files as “Generated/X.m” file instead of creating a “Generated” group which contains an “X.m” file. 

### Stopping applications on devices on Windows host is unsupported. ([Issue #19](https://github.com/multi-os-engine/multi-os-engine/issues/19))
