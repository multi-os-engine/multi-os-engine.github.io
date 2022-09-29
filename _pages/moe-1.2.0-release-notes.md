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
        [<i class="fa fa-github"></i> Start Building](https://github.com/multi-os-engine/multi-os-engine){: .btn .btn--large}&nbsp;
        '
---

This is the Release Notes for the Multi-OS Engine 1.2.0 release.

## What's New

### Eclipse Support

The Multi-OS Engine now provides an Eclipse plugin, that can be used for iOS App development. The plugin works with Gradle and Maven, and supports the Mars and Neon Eclipse releases. 

### Maven Build Support

We now have a Maven plugin as well, so if you prefer to use Maven instead of Gradle, it is possible as well. The Maven plugin is integrated with M2E in Eclipse, which results in a smooth experience.

### Xcode 8 Support

This release adds support for building with Xcode 8. 

Note: Xcode 8 changed the way how signing works. To build on Xcode 8, your Development Team's identifier has to be configured. Please refer to the [documentation](/docs/) or the [Get Started](/start/) page for more details.

### iOS 10 Support

The iOS bindings were updated to iOS 10, so you can now use the new iOS 10 APIs in MOE applications.

### Binding packages renamed from ``ios.*`` to ``apple.*``

In preparation to support other Apple OSes besides iOS in a future release, we renamed the ``ios.*`` packages to ``apple.*`` . We realize that such renamings are always inconvenient, but it was inevitable, so we decided to do it as soon as possible.

We created a pull request for LibGDX, so the MOE backend should be updated to use MOE 1.2 shortly.

## Removed Features

It is always a hard decision to remove existing features from a software package. We thought long and hard about this decision, but ultimately we believe that these changes will make the Multi-OS Engine better for the developers who rely on it.

We published a [separate blog post](/blog/2016-09-30-removed-features/) to explain our reasoning behind the removal of these features. Be sure to read that post as well for more details.

### MOE Designer Removed from the Release

We decided to remove the MOE UI Designer from the release, and also from the Jetbrains Plugin Repository. It is recommended that you remove it from your Android Studio / IDEA installation before you upgrade to MOE 1.2, because we have seen compatibility issues between the 2 MOE plugins.

The plugin source code will [remain on GitHub](https://github.com/multi-os-engine/moe-ui-designer), so you are free to check it out and use it, if you are interested. We are open to including it again in a future release, when [the current issues with it](/blog/2016-09-30-removed-features/) are fixed.

### Deprecated Build-time Xcode Project Generation - To Be Removed in MOE 1.3

Starting with MOE 1.2, all newly generated MOE projects will use the persistent Xcode project setup (``Keep Xcode`` mode in MOE 1.1). Existing projects with build-time Xcode project generation will continue to work.

In MOE 1.3 the build-time Xcode project generation will be removed, so it is recommended to switch to persistent Xcode project mode as soon as possible. Please [contact us](https://discuss.multi-os-engine.org), if you need assistance with the switch.

You may read more details on the background of this decision in our [Behind The Scenes post](/blog/2016-09-30-removed-features/).

##  Other Changes

You may check out the other changes and bugfixes [on GitHub](https://github.com/multi-os-engine/multi-os-engine/issues?q=is%3Aissue%20milestone%3A1.2.0).


## How to install

Please follow the instructions on the [Get Started page](/start/).

## Where is the source code

The source code can be found on [GitHub](https://github.com/multi-os-engine/multi-os-engine).

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

### JUnit Runner Support in Maven projects in Eclipse ([Issue #52](https://github.com/multi-os-engine/multi-os-engine/issues/52))

Running JUnit tests in Maven projects is not yet supported in the Eclipse plugin.

## More Information

* [Multi-OS Engine Documentation](/docs/)
* [Multi-OS Engine Source Code](https://github.com/multi-os-engine/multi-os-engine)
* [Join the Community Forum](https://discuss.multi-os-engine.org)
