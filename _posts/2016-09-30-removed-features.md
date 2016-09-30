---
title: "Removed Features - Behind The Scenes"
excerpt: "Why did we remove features and what to expect in the future"
author_profile: true
layout: single
---

With today's release of [MOE 1.2.0](/blog/2016-09-30-moe-release-1.2.0/) we felt it was important to share the reasons behind our housecleaning decisions in more detail.

## UI Designer Removal

We decided to remove the MOE UI Designer from the release, and also from the Jetbrains Plugin Repository. It is recommended that you remove it from your Android Studio / IDEA installation before you upgrade to MOE 1.2, because we have seen compatibility issues between the 2 MOE plugins.

The plugin source code will [remain on GitHub](https://github.com/multi-os-engine/moe-ui-designer), so you are free to check it out and use it, if you are interested. 

There are multiple reasons why we believe this is the right move:

 * The functionality of the plugin is limited, and while it is possible to use it for simple prototypes, it is not (yet) suited for most real world applications.
 * No real projects are using it, that we know of. If you were using it in your project, please contact us, and we will help with the migration to using Storyboards directly.
 * There are known bugs in it, that we did not have the time to fix.
 * The maintenance of the plugin would pull away resources from more important features (e.g. upgrade to Android N, LLVM backend ... etc.)

We do think that a full-fledged cross-platform UI Designer for the Multi-OS Engine would be an important component in the future. We envision a tool, that: 

 * works directly with Storyboard files
 * provides access to all features supported in Storyboards
 * works with Android Studio and Eclipse on all supported host platforms

If you are interested in using such a UI Designer, please contact us, and we can discuss how to make it reality.

## Build-time Xcode Project Generation - To Be Removed in MOE 1.3

Starting with MOE 1.2, all newly generated MOE projects will use the persistent Xcode project setup (``Keep Xcode`` mode in MOE 1.1). Existing projects with build-time Xcode project generation will continue to work.

In MOE 1.3 the build-time Xcode project generation will be removed, so it is recommended to switch to persistent Xcode project mode as soon as possible. Please contact us, if you need assistance with the switch.

In MOE 1.1, newly created MOE projects were using build-time Xcode project generation by default. This basically meant, that when you launched a MOE project / module, Gradle would generate a new Xcode project in ``build/xcode`` and use it during the build. 

The downside of this solution was, that only a handful of parameters of this generated Xcode project could be specified in the build.gradle file, and this limitation could be reached very quickly. In fact, we don't know of any MOE project in production, that used build-time project generation. The MOE backend for LibGDX also uses a persistent Xcode project based setup.

The workaround was, that you could opt-out from this feature by a setting in build.gradle, and (since MOE 1.1) at project / module generation time in Android Studio.

However, there are legitimate use cases for this feature:

 * If you are working on Windows, then you might not have easy access to an Xcode GUI to make even the most basic changes. In such cases the build-time Xcode project generation is a functional stop-gap measure.
 * Some of the 3rd party library binding features only work with the build-time Xcode project generation correctly. 

To accommodate these use cases, we will introduce new features in MOE 1.3:

 1. We will include an editor for Xcode project files, so you can edit your Xcode project directly from Eclipse or Android Studio / IDEA.
 1. We will completely revamp the 3rd party library binding features to fix all current issues and support the persistent Xcode project setup.

## Looking into the Future

As you can see, we don't take the removal of existing features lightly.  We will do everything possible to make sure that existing features don't have to be removed in the future. That said, we will not shy away from removing features just for the sake of compatibility, if the removal moves the project forward with minimal side-effects.

The UI Designer and the Build-time Xcode project generation were ideal candidates for removal, because of their minimal user base and high maintenance costs.
