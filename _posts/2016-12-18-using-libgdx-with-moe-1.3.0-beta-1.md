---
title: "Using LibGDX with MOE 1.3.0 beta 1"
excerpt: "Enjoy the best of MOE also for game development"
author_profile: true
layout: single
comments: true
---

We just released the first beta of MOE 1.3 with [tons of new features](/blog/2016-12-16-moe-1.3.0-beta-1-released/).

As mentioned in the release announcement, MOE 1.3 includes a tool to upgrade the Xcode part of a MOE 1.2 project without manual intervention.

In this blog post we will look at how a project created by the [LibGDX](https://libgdx.badlogicgames.com) 1.9.5 setup tool can be upgraded to use MOE 1.3. If you already have a MOE 1.2 based LibGDX project, you may follow the following guide to upgrade it as well.

This guide assumes, that you already installed the MOE 1.3 versions of your IDE plugins.

## Create your MOE based LibGDX project

1. Download the latest setup tool from the [LibGDX project website](https://libgdx.badlogicgames.com).
1. Create your new LibGDX project by running the tool from the command line.

    ```
    java -jar gdx-setup.jar
    ```
1. Follow the instructions of the setup tool. Make sure you select the ``ios-moe`` platform to create the MOE based iOS module.

## Edit the Gradle project files

1. In the top level build.gradle file change the ``moe-gradle`` plugin version to ``1.3.0-beta-1``
1. In the ``ios-moe`` module change the moe section in the build.gradle file as follows:

```groovy
moe {
    xcode {
      project 'xcode/ios-moe.xcodeproj'
      mainTarget 'ios-moe'
      testTarget 'ios-moe-Test'
    }
}
```

## Update the Xcode project

1. Import the updated project into your favorite IDE
1. Right click on the ``ios-moe`` module and use the ``Multi-OS Engine Actions > Inject/Refresh Xcode Project Settings``

## Ready to Run

Now your project should be ready for MOE 1.3. Launch from your IDE and Enjoy!

**Note:** If you have not used MOE before, then you will need to set up code signing. Follow the instructions on the [MOE Website](/start/) on how to set the default team for developer signing.

## Request for Comments

 We designed MOE 1.3 based on the requests and reports from the MOE Community. We hope, that you will like these new features, and they will make your life easier as a developer.

As always, leave your comments below, so we will know your opinion on all the changes and plans. The development of MOE is based on the requirements of the community, so we are open to discuss any changes in direction or features for future releases.

If you need a specific feature in MOE, you may consider contracting  [Migeran](https://migeran.com), the core developers and project lead of the MOE project to develop it.

Also, if you are working on a commercial project with MOE, [Migeran](https://migeran.com) offers commercial support, including live online support with Migeran's top engineers. [Contact Migeran](https://migeran.com/contact/) for more details.
