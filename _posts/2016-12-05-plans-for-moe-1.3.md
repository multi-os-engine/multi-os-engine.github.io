---
title: "What is planned for MOE 1.3"
excerpt: "More flexible than ever"
author_profile: true
layout: single
comments: true
---

In this blog post we are going into the details of what you can expect from the upcoming MOE 1.3 release.

For a general overview of our roadmap, check out our [MOE Roadmap](/blog/2016-12-05-moe-roadmap/) post.

## Redesigned Xcode Project Layout

One of the main design goals of the Multi-OS Engine is to be a versatile, flexible tool for professional developers. This means, that when we design our tools and solutions, we try to accommodate the requirements of even the most complex projects and provide solutions for them.

Up to MOE 1.2, our build system required some specific settings in an Xcode project, including a ``build.xcconfig`` file. These requirements made it difficult to add MOE to an existing Xcode project. Working with a CocoaPods enabled Xcode project was not possible.

Starting with MOE 1.3, we will only require a few custom build phases and build settings in your main Xcode project. The build system will also work with Xcode workspaces.

MOE 1.3 will include a tool that can upgrade an MOE 1.2 Xcode project to MOE 1.3. This tool can also apply the required MOE settings to an existing Xcode project, similar to ``pod install`` in CocoaPods. This way it way be straightforward to add Java code to any iOS project.

## Support for native dependency management frameworks

The main goal of the Xcode project layout redesign was, that MOE should work together with any dependency management framework like [CocoaPods](https://cocoapods.org/) or [Carthage](https://github.com/Carthage/Carthage).

Our solution is basically to get out of the way of these frameworks, and only require minimal changes to the Xcode project.

Starting with MOE 1.3 you can add your native libraries to your MOE project the same way you would do in an Objective-C / Swift only iOS project, e.g. call ``pod install`` and ``pod update`` the same way you would do it on any other CocoaPods enabled project.

## Redesigned native library binding handling

Up to MOE 1.2 we included a few custom actions in the IDE plugins, like ``Link third party framework / library`` or ``Link CocoaPods``. With these features MOE *promised* that you could take any native library, and generate bindings for it with the click of a button.

There was only one slight problem with this: it only worked for simple cases. In more complex situations things failed with cryptic error messages.

The new method goes into a different direction, and introduces **MOE Binding Projects**. These projects are mostly regular MOE projects, where the native library was already imported into the Xcode project using the most convenient native dependency management method.

For Example the Google Play Services library for iOS is also distributed using CocoaPods, that can be used in the Binding Project as well.

The Binding Project also includes the Nat/J Generator configuration, that can be used to regenerate the Java bindings whenever a new version is released, and any handwritten convenience methods and classes to provide a smooth developer experience.

Finally, the Binding Project has a Gradle task to regenerate the binding and publish it as a Maven artifact in the Maven repository of your choosing.

These bindings can be reused in your MOE projects by simply adding them as a build dependency (and of course by adding the native counterparts to the associated Xcode project using the preferred method).

## Standard MOE Bindings

We are also creating a central repository of MOE bindings for the most frequently used iOS libraries. The binding projects will be hosted on GitHub with the rest of MOE, and the generated bindings will be added to JCenter and Maven Central for your convenience.

We already have a few bindings created (e.g. the already Google Play Services for iOS library).

Contributions of additional bindings are very welcome!


## Redesigned Storyboard integration

For productive app development Storyboard integration is crucial.

There are 2 options for working with Storyboards and MOE. These 2 options are not mutually exclusive, you may mix them in a single project, as you need.

### ViewControllers created in Java

In this case the ViewController classes are created manually in your favorite Java IDE. You have to make sure to add the correct ``@Selector`` annotations on your action methods and the ``@Property`` annotations on the properties that you want to make accessible from Objective-C. Then, the ``Synchronize to Xcode`` menu action will create the Objective-C stubs that correspond to your ViewController classes.

Up to MOE 1.2 the implementation of this function had several issues:

 * the stub generation worked with the Java source code, so alternative languages, like Kotlin, could not be supported.
 * the generated stubs were added to the Xcode project in a way that could cause issues with building from Xcode and with accessing them from Storyboards.
 * the function only worked with the build-time generated Xcode project mode, which was deprecated in MOE 1.2 and will be removed from MOE 1.3.

In MOE 1.3 the complete implementation was replaced with a new one:

 * the Objective-C stubs are generated from Java bytecode, so alternative languages can be supported. Kotlin support will be included in MOE 1.3.
 * the contents of the generated stub classes are only visible to the Storyboards but not to the build process (with the use of the appropriate ``#if`` preprocessor guards)
 * designed to work with the persistent Xcode project setup

### ViewController stubs created in Objective-C

In this case ViewController stubs are created in Objective-C, and used with Storyboards directly to connect the properties and actions. The ``Synchronize to Java`` action can be used to generate the Java bindings for these ViewController stubs. These Java classes can be extended with the action implementations, as usual.

Up to MOE 1.2 this action could only be executed on a single header file.

MOE 1.3 will allow the creation of a custom binding generation configuration (similar to binding projects), so you can easily generate Java bindings for your ViewController and other classes in complex situations as well.

## Release Schedule

MOE 1.3 will be a huge update, but these changes took time to develop. They are also closely connected to each other, so an incremental release strategy (adding new features one by one while keeping the old features functional) would have been even more difficult.

We will release a beta version of MOE 1.3 before the end of 2016. It will have a lot of the functionality already in place, so you can try out some of the new features. We are already using it for our own projects, so it should be relatively stable, if you are not afraid of hard edges, and some bugs here and there.

The final, polished release of MOE 1.3 will arrive in January 2017.

## Subsequent MOE Releases

While MOE 1.3 will lay the stable foundations that we can build on, there will be features that simply won't fit into this release. A few examples:

 * A user friendly editor for Nat/J Generator configurations (it is JSON based, so you can do it by hand already, but it would be nice to have a real GUI)
 * Full featured, platform-independent editor for Xcode projects: with the removal of the build-time Xcode project generation
 * Linux based development host: this is a low hanging fruit, but with all the planned changes, we have to postpone it to MOE 1.4

 Also, MOE 2.x is in the works with the Android 7 based runtime and LLVM based compiler backend updates. While a lot is changing under the hood, it will be mostly a drop-in replacement / incremental upgrade from the app developer's point of view, so every new MOE 1.x feature will still be available in MOE 2.x.

## Request for Comments

 We designed MOE 1.3 based on the requests and reports from the MOE Community. We hope, that you will like these new features, and they will make your life easier as a developer.

As always, leave your comments below, so we will know your opinion on all the changes and plans. The development of MOE is based on the requirements of the community, so we are open to discuss any changes in direction or features for future releases.

If you need a specific feature in MOE, you may consider contracting  [Migeran](https://migeran.com), the core developers and project lead of the MOE project to develop it.

Also, if you are working on a commercial project with MOE, [Migeran](https://migeran.com) offers commercial support, including live online support with Migeran's top engineers. [Contact Migeran](https://migeran.com/contact/) for more details.
