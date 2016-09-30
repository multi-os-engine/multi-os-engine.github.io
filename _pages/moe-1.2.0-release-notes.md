---
layout: splash
permalink: /moe-1.2.0-release-notes/
date:
title: Multi-OS Engine 1.2.0 Release Notes
header:
  overlay_color: "#0071c5"
#  overlay_image: mm-home-page-feature.jpg
// excerpt: 'Everything you need'
buildsrc:
  - title: Build from Source
    image_path: wet_surface.png
    excerpt: 'We are working hard to get an easy to use installation method ready. In the meantime you can build MOE from source.<br /><br />
        [<i class="fa fa-github"></i> Start Building]({{ site.data.links.github }}){: .btn .btn--large}&nbsp;
        '
---

This is the Release Notes for the Multi-OS Engine 1.2.0 release.

## What's New


## How to install

Please follow the instructions on the [Get Started page]({{ site.data.links.start }}).

## Where is the source code

The source code can be found on [GitHub]({{ site.data.links.github }}).

The release was marked with the tag ``moe-1.2.0``.

## Known Issues

### Linking 3rd party libraries, frameworks and CocoaPods is not always working as intended. ([Issue #21](https://github.com/multi-os-engine/multi-os-engine/issues/21))

* Binding generation may fail. There is no workaround for this, but we aim to address this issue in Multi-OS Engine 1.3.

### Some samples are not working as intended. ([Issue #15](https://github.com/multi-os-engine/multi-os-engine/issues/15))

* Documentation, UI and usability issues. We aim to address this in Multi-OS Engine 1.3.

### Launching an application on a device which was not previously trusted will fail.

* When a device is connected to a computer for the first time, the device asks whether to trust the computer or not. If the computer is not trusted at the time of launching, the launch will fail.
* **Workaround:** Trust the computer on the device and try again.

### When opening a project in Android Studio, whose run configuration is configured with special path variables, the IDE may display “xxx is undefined” fix-it.

* **Workaround:** Ignore this message.

### Starting a debug session on slower machines may fail to connect to the JDWP server. ([Issue #20](https://github.com/multi-os-engine/multi-os-engine/issues/20))

The build logic has been largely improved, and this issue now only affects a subset of users compared to earlier versions. If the launch process (installation onto device and application startup) takes up too much time then Android Studio’s JDWP connection attempts to the application may timeout.

* **Workaround:** Create a separate run configuration which connects to localhost:8000 (port 8000 is the default port as the MOE Application Run Configuration) and use that to connect to the application’s JDWP server.

### “Synchronize to Xcode” adds stubs incorrectly ([Issue #17](https://github.com/multi-os-engine/multi-os-engine/issues/17))

* The function adds native files as “Generated/X.m” file instead of creating a “Generated” group which contains an “X.m” file. 

### Stopping applications on devices on Windows host is unsupported. ([Issue #19](https://github.com/multi-os-engine/multi-os-engine/issues/19))

### Maven Support in Android Studio ([Issue #47](https://github.com/multi-os-engine/multi-os-engine/issues/47))

The Android Studio / IntelliJ plugin does not support the Maven build yet.

### JUnit Runner Support in Maven projects in Eclipse ([Issue #52](https://github.com/multi-os-engine/multi-os-engine/issues/52))

Running JUnit tests in Maven projects is not yet supported in the Eclipse plugin.

## More Information

* [Multi-OS Engine Documentation]({{ site.data.links.docs }})
* [Multi-OS Engine Source Code]({{ site.data.links.github }})
* [Join the Community Forum]({{ site.data.links.forum }})
