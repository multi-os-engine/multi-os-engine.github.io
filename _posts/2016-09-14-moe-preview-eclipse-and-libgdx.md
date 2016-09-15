---
title: "MOE Preview: Eclipse & LibGDX"
excerpt: "iOS development comes to Eclipse; LibGDX updated to work with MOE 1.1.x"
author_profile: true
layout: single
comments: true
newproject:
  - image_path: features/eclipse-new-project.png
    image_width: 524px
launchconfig:
  - image_path: features/eclipse-launch-config.png
    image_width: 803px
runas:
  - image_path: features/eclipse-run-as.png
    image_width: 371px
---

Work on the MOE 1.2.x release is well underway, with a planned release date later this month. The highlight of this next release will be Eclipse and Maven support, along with various updates and bug fixes. 

We would like to get your early feedback with the preview version of the MOE Eclipse plugin. 

Eclipse support is especially important to the LibGDX users and developers. Luckily (thanks to the LibGDX developers), the development version of LibGDX already supports MOE 1.1.x. In the second half of this post we will walk through the process of creating a new LibGDX project, that works with MOE 1.1.x, and works with the new Eclipse plugin as well.

## Eclipse Support

Eclipse Support of the Multi-OS Engine is realized using an Eclipse plugin. To install it, follow the next steps:

 1. Open the ``Install New Software...`` menu item in the ``Help`` menu.
 1. Add the following update site:
 ```
 https://dl.bintray.com/multi-os-engine/eclipse-dev
 ```
 1. Install the ``Multi-OS Engine Developer Tools``
 1. Restart Eclipse when prompted

After the restart, you may create a new Multi-OS Engine project, or import an existing one, provided, that they were updated to work with Eclipse.

![New Project]({{ base_url }}/images/features/eclipse-new-project.png){: .align-center}

The MOE Eclipse plugin will work with any MOE Project, provided that the appropriate Eclipse Project Nature is added to the project. To do that, make sure that:

 * The ``eclipse`` plugin is applied to the project in the build.gradle file.
 * The following section is added to the ``eclipse`` plugin configuration in the build.gradle file:

```
    eclipse {
        // Set MOE natures and build commands
        project {
            natures 'org.moe.natures.project'
        }
    }
```

With these changes, the standard MOE sample projects should work fine with Eclipse. If you run into any issues, please report them on GitHub or on our forums.

## LibGDX with MOE and Eclipse

Support for the new MOE release (MOE 1.1.x) was already added in the libgdx master branch. Builds from these branch are accessible under the ``1.9.5-SNAPSHOT`` version.

The easiest way to create a new LibGDX project is the GDX Setup tool (``gdx-setup.jar``). For now, we will need the nightly build of the gdx-setup.jar, which includes support for the MOE 1.1.x version.

 1. Download the nightly build of the ``gdx-setup.jar`` from [here](http://libgdx.badlogicgames.com/nightlies/dist/gdx-setup.jar)
 1. Launch it as usual with ``java -jar gdx-setup.jar``
 1. Fill out the fields according to your needs, make sure you select the ``ios-moe`` backend, and generate the project.
 1. In the generated project's ``build.gradle`` file change the ``gdxVersion`` to ``1.9.5-SNAPSHOT``
 1. At this point, you can import the project into Android Studio and launch it with a Multi-OS Engine run configuration as usual
 1. To use the project with Eclipse, add the following block to the ``project(":ios-moe") {`` section in the project build.gradle file:

	```
	    eclipse {
	        // Set MOE natures and build commands
	        project {
	            natures 'org.moe.natures.project'
	        }
	    }
	```

 1. Now you are ready to import the LibGDX project into Eclipse as a ``Gradle Project``. Choose the "Smart" import option. The resulting workspace will include a project called ``ios-moe``. You may run / debug this project as a ``Multi-OS Engine Application``. 

![Run As]({{ base_url }}/images/features/eclipse-run-as.png){: .align-center}

![Launch Configuration]({{ base_url }}/images/features/eclipse-launch-config.png){: .align-center}

If you run into any issues (or just want to say hi), please join us on our [discussion forum](https://discuss.multi-os-engine.org). Stay tuned for more updates on Maven support and the upcoming MOE 1.2.0 release.
