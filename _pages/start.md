---
layout: splash
permalink: /start/
date:
title: Get Started
header:
  overlay_color: "#0071c5"
#  overlay_image: mm-home-page-feature.jpg
// excerpt: 'Everything you need'
buildsrc:
  - title: Build from Source
    image_path: wet_surface.png
    excerpt: 'We are working hard to get an easy to use installation method ready. In the meantime you can build MOE from source.<br /><br />
        [<i class="fa fa-github"></i> Start Building](https://github.com/multi-os-engine/multi-os-engine){: .btn .btn--large}&nbsp;
        '
---

{% include button_nav %}

## Installation

### Prerequisites for an Apple macOS host

*   A computer running macOS 10.11 or higher
*   4 GB RAM (recommended 8 GB) or higher
*   Apple Xcode* 7.3 or higher
*   Xcode Command Line Tools
*   iOS* 8 SDK or higher
*   Oracle Java* Development Kit (JDK) version 8
*   Google Android Studio* IDE 2.1 or higher
*   Android SDK with API level 9 or higher
*   Enrollment in the Apple Developer Program (required for Apple iOS* device support)

### Prerequisites for a Windows* host

*   A computer running Windows 7* OS x64 edition or higher
*   4 GB RAM (recommended 8 GB) or higher
*   Oracle Java* Development Kit (JDK) version 8
*   Google Android Studio 2.1 or higher
*   Android SDK with API level 9 or higher
*   Apple iTunes* for Windows
*   Enrollment in the Apple Developer Program (required for iOS device support)
*   Remote SSH Access to a computer running macOS 10.11 that meets the prerequisites above

### Option 1: Install Android Studio / IDEA Plugin

![image-center](/images/features/android-studio-install.png){: .align-center}

* You may install the Multi-OS Engine plugin from the JetBrains plugin repository, right from Android Studio (or IntelliJ IDEA).

### Clone the samples repository from GitHub


```
git clone https://github.com/multi-os-engine/moe-samples-java
```

### Import a sample into Android Studio / IntelliJ or Eclipse

* Use the ``Import Project (Eclipse ADT, Gradle, etc.)`` option in Android Studio / IDEA
* Or import your project as ``Gradle Project`` in Eclipse
* As the Gradle project is synchronized into your IDE, the Gradle plugin will automatically download the required MOE SDK version
* Now you may launch the App on the iOS Simulator as usual
* For on device execution, read on.

### Set up Code Signing for On Device Execution in Xcode 8

Code signing in Xcode 8 is different from Xcode 7. For ease of use we recommend you create a `default.properties` file in your `~/.moe` directory. This file should contain you Apple Developer Team ID in the following form:

```text
developmentTeam=ABCDEFGHIJ
```

For more information on code signing, visit the [installation documentation](/docs/multi-os-engine/3_getting_started/1_installation/installation.html) and the [Multi-OS Engine Gradle Plugin](https://github.com/multi-os-engine/moe-plugin-gradle/blob/master/README.md#code-signing) on GitHub.

### That's it! 

* Now you have set up (and tested) MOE on your system.

## More Information

* [Multi-OS Engine Documentation](/docs/)
* [Multi-OS Engine Source Code](https://github.com/multi-os-engine/multi-os-engine)
* [Join the Community Forum](https://discuss.multi-os-engine.org)
* [Join the Discord Server](https://discord.gg/m5t3qNXTWj)
