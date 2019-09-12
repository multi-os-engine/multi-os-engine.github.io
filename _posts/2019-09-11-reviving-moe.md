---
title: "MOE Update #1: Reviving the Multi-OS Engine Project"
excerpt: "It is time to upgrade."
author_profile: true
layout: single
comments: true
---

Dear MOE Community,

after almost 1.5 years since the last release (MOE 1.4.4) we are reviving the Multi-OS Engine project. We started working on MOE in 2013 (back then it was called Migeran for iOS), and it will always have a special place in my professional life. Therefore it is my great personal sorrow, that we have left the project without maintenance for so long. I don't want to delve into the past why and how this could happen. Instead let's look into the future, and see how we can make sure that this does not happen again.

But first, I want to express my deepest gratitude towards you, the MOE Community who kept using MOE and demanded updates. You are a big part of MOE and a huge inspiration to continue this journey. I would like to thank especially NoisyFox, who even created community builds to make sure MOE works with newer versions of the Apple and Android tools.

Now let's see what are the next steps for MOE.

## September 2019: Release MOE 1.5.0 with XCode 11 and iOS 13 Support

We already started working on the next release, that will make MOE functional again on current XCode and iOS versions. This release will include:

 * Updated tools to work on MacOS Mojave and Catalina
 * Updated plugin with Android Studio 3.5 support
 * Support for building with XCode 11

It will most probably not include any new APIs (except for those that the generator can pick up without any changes).

## October 2019: MOE 1.6 with iPadOS Support

In October we plan to release the next update that will include:

 * New iOS and iPadOS APIs
 * Improvements to the Nat/J Generator to handle currently unsupported features (e.g. vector types in the AR API)

## Turning MOE into a True Community Project

We are committed to turning MOE into a true Community Project. This means multiple things:

 * We are going to invite external MOE contributors as committers into the project.
 * We are also going to improve our response time with reviewing pull requests.
 * We will also move the current website code into a public repository, so anyone can send us pull requests for the website contents as well.
 * And last but not least: We are planning much more frequent communication with the members of the community (e.g. weekly updates). 

## In the Next Project Update: Longer Term Plans of MOE

We have way more plans and ideas for the future, that we are going to share in future updates. In the next update I will take a look at different components of MOE (the runtime, Nat/J and the generator ... etc.), and what you can expect in the foreseeable future.

As always, feedback is very welcome here in the comments or [on the forum]({{ site.data.links.forum }}).

Looking forward to hearing from you.

Gergely Kis<br>
MOE Project Lead

