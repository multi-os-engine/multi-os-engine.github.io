---
title: "Multi-OS Engine Release 1.2.0"
excerpt: "Eclipse, Maven, Xcode 8, iOS 10 ... what more could you want? Read on to find out!"
author_profile: true
layout: single
---

We are pleased to announce the Multi-OS Engine 1.2.0 release. This release includes a many major updates since MOE 1.1. Please note, that due to the renaming of the iOS binding packages you will also need to migrate your projects. Read on for the details.

## What's New

### Eclipse Support

The Multi-OS Engine now provides an Eclipse plugin, that can be used for iOS App development. The plugin works with Gradle and Maven, and supports the Mars and Neon Eclipse releases. 

### Maven Build Support

We now have a Maven plugin as well, so if you prefer to use Maven instead of Gradle, it is possible as well. The Maven plugin is integrated with M2E in Eclipse, which results in a smooth experience.

### Xcode 8 Support

This release adds support for building with Xcode 8. 

Note: Xcode 8 changed the way how signing works. To build on Xcode 8, your Development Team's identifier has to be configured. Please refer to the [documentation]({{ site.data.links.docs }}) or the [Get Started]({{ site.data.links.start }}) page for more details.

### iOS 10 Support

The iOS bindings were updated to iOS 10, so you can now use the new iOS 10 APIs in MOE applications.

### Binding packages renamed from ``ios.*`` to ``apple.*``

In preparation to support other Apple OSes besides iOS in a future release, we renamed the ``ios.*`` packages to ``apple.*`` . We realize that such renamings are always inconvenient, but it was inevitable, so we decided to do it as soon as possible.

We created a pull request for LibGDX, so the MOE backend should be updated to use MOE 1.2 shortly.

## Removed Features

It is always a hard decision to remove existing features from a software package. We thought long and hard about this decision, but ultimately we believe that these changes will make the Multi-OS Engine better for the developers who rely on it.

We published a [separate blog post](/blog/2016-09-29-housecleaning/) to explain our reasoning behind the removal of these features. Be sure to read that post as well for more details.

### MOE Designer Removed from the Release

We decided to remove the MOE UI Designer from the release, and also from the Jetbrains Plugin Repository. It is recommended that you remove it from your Android Studio / IDEA installation before you upgrade to MOE 1.2, because we have seen compatibility issues between the 2 MOE plugins.

The plugin source code will [remain on GitHub](https://github.com/multi-os-engine/moe-ui-designer), so you are free to check it out and use it, if you are interested. We are open to including it again in a future release, when [the current issues with it](/blog/2016-09-29-housecleaning/) are fixed.

### Deprecated Build-time Xcode Project Generation - To Be Removed in MOE 1.3

Starting with MOE 1.2, all newly generated MOE projects will use the persistent Xcode project setup (``Keep Xcode`` mode in MOE 1.1). Existing projects with build-time Xcode project generation will continue to work.

In MOE 1.3 the build-time Xcode project generation will be removed, so it is recommended to switch to persistent Xcode project mode as soon as possible. Please [contact us]({{ site.data.links.forum }}), if you need assistance with the switch.

You may read more details on the background of this decision in our [Housecleaning post](/blog/2016-09-29-housecleaning/).

## Major Bug Fixes

## How to install

Please follow the instructions on the [Get Started page]({{ site.data.links.start }}).

## More Information

* [MOE 1.2.0 Release Notes](/moe-1.2.0-release-notes/)
* [Multi-OS Engine Documentation]({{ site.data.links.docs }})
* [Multi-OS Engine Source Code]({{ site.data.links.github }})
* [Join the Community Forum]({{ site.data.links.forum }})
