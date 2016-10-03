---
title: "MOE 1.2 Support Landed in LibGDX"
excerpt: "Read on to find out how to test it"
author_profile: true
layout: single
comments: true
---

Our Pull Request to update the Multi-OS Engine backend in LibGDX was already merged (Thanks Tom-Ski!), and it should be available in the latest nightly build.

To try it out, just follow these steps:
* [Install MOE 1.2]({{ site.data.links.start }}) into your IDE of choice (Android Studio / IntelliJ or Eclipse)
* Download the nightly build of [gdx-setup.jar](https://libgdx.badlogicgames.com/nightlies/dist/gdx-setup.jar)
* Generate a new GDX project with gdx-setup
 * Make sure that you select the ``ios-moe`` backend
* In the generated build.gradle file change the ``gdxVersion`` to ``1.9.5-SNAPSHOT``
* Import the project as Gradle project into your IDE
* Create a run / launch configuration and start the app
* Enjoy!

**Note:** If you want to run your app on a real device with Xcode 8, you need to configure code signing correctly. For more details, please refer to our [documentation]({{ site.data.links.start }}).
