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

* Android Studio / IDEA plugins are now distributed using the JetBrains plugin repositories.
* The MOE Gradle plugin is now on JCenter.
* The simulator launcher was replaced by a completely new implementation. It is much more stable and supports Xcode 7.3 or newer. ([Issue #4](https://github.com/multi-os-engine/multi-os-engine/issues/4))
* If the build process took too long during a debug launch, the JDWP connect timeout could be triggered. This is now fixed. ([Issue #5](https://github.com/multi-os-engine/multi-os-engine/issues/5))
* The documentation was updated ([Issue #7](https://github.com/multi-os-engine/multi-os-engine/issues/7)) 
* Various bugs with the ``Synchronize to Xcode`` function were fixed ([Issue #9](https://github.com/multi-os-engine/multi-os-engine/issues/9))
* We added the ``Keep Xcode project`` option to the Android Studio project wizard. This way, you can create new projects in a single step, where the Xcode project will be managed manually. 
* Also made some internal fixes to the project generation logic ([Issue #2](https://github.com/multi-os-engine/multi-os-engine/issues/2))

Enjoy! If you have any questions, don't hesitate to contact us on the [MOE Forum](https://discuss.multi-os-engine.org/).

## How to install

Please follow the instructions on the [Get Started page](/start/).

## More Information

* [MOE 1.1.0 Release Notes](/moe-1.1.0-release-notes/)
* [Multi-OS Engine Documentation](https://doc.multi-os-engine.org)
* [Multi-OS Engine Source Code](https://github.com/multi-os-engine/multi-os-engine)
* [Join the Community Forum](https://discuss.multi-os-engine.org)
