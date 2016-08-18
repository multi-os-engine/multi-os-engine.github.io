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
        [<i class="fa fa-github"></i> Start Building]({{ site.data.links.github }}){: .btn .btn--large}&nbsp;
        '
---

{% include button_nav %}

# Installation

## Install Prerequisites

### On Mac

* Mac OSX 10.11 or later
* Xcode 7.3 or later
* Oracle Java JDK 8
* Android Studio 2.1.3 or later

### On Windows

* Windows 7 or later (only 64-bit Windows is supported)
* Oracle Java JDK 8
* Android Studio 2.1.3 or later

For Windows, you also have to set up the remote build, see below.

## Install Android Studio Plugin

* You may install the Multi-OS Engine plugin from the JetBrains plugin repository, right from Android Studio.

## That's it! Now Try a Sample

### Clone the samples repository from GitHub

```
https://github.com/multi-os-engine/moe-samples-java
```

### Import a sample into Android Studio

* As the Gradle project is synchronized into Android Studio, the Gradle plugin will automatically download the required MOE SDK version.
* Now you may launch the App as usual

# Remote Build Setup

## Build Server Requirements

- Apple OS X 10.11.+
- Apple Xcode 7.3+
- Root access to the remote server

## Setting Up Xcode & Keychain

Before any remote build can occur, we need to ensure the build server's Xcode is setup correctly.

### Prepare Xcode

- Go to `Xcode > Preferences > Accounts`.
- Click on the `+` icon and login with your Apple ID.
- Select your team.
- Create an iOS Development signing identity.
- Download all provisioning profiles.
- Connect a device to the system and make sure you can run an application on it.

### Prepare Keychain

- Open `Keychain Access`
- Create a new Keychain with `File > New Keychain...`
- Save as `moeremotebuild`
- Give it a password, ie.: `devpass`
- Move the iPhone development certificate and the corresponding private key from the `login` keychain to the new one.

## Setting Up OpenSSH

The Multi-OS Engine remote build system currently requires public-key authentication. For this we must create a private/public-key pair. GitHub has a great description on how to do this [here](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/). (Note: the `-C "your_email@example.com"` parameter is not required.)

### Build Server

We must setup OS X's Remote Login feature to use public keys instead of passwords.

- Login to your remote server.
- Go to `System Preferences > Sharing` and disable Remote Login.
- Open Terminal.
- Type `sudo nano /etc/ssh/sshd_config` and enter password to edit.
- Change the parameters to the following:

```
RSAAuthentication yes
PubkeyAuthentication yes
PasswordAuthentication no
ChallengeResponseAuthentication no
```

- Press `ctrl + O` to save and `ctrl + X` to exit.
- Type `mkdir -p ~/.ssh && nano ~/.ssh/authorized_keys`
- Add the contents of your `id_rsa.pub` file into a new line.
- Press `ctrl + O` to save and `ctrl + X` to exit.
- Go to `System Preferences > Sharing` and enable Remote Login.

# More Information

* [MOE Documentation]({{ site.data.links.docs }})
* [MOE Gradle Plugin README](https://github.com/multi-os-engine/moe-plugin-gradle)
* [MOE Source Code]({{ site.data.links.github }})
* [Join the Community Forum]({{ site.data.links.forum }})