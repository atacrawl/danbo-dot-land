---
layout: layouts/post.njk
title: A better way to handle mobile accordion animation
date: 2020-07-18T21:20:22.663Z
tags:
  - accordion
---
Accordions can be an effective way to progressively disclose inline information in a compact manner, particularly on mobile devices.

But oftentimes a developer will get two requirements from a designer that seem at odds with each other:

1. Opening and closing a tab should have a slide animation.
2. Opening a tab simultaneously closes any previously open tab.

Hmm. The problem arises in the scenario when the user opens a tab _below_ the currently open tab. If the requirements are taken at face value, both tabs animate, creating an unpleasant, disorienting experience for our user. This is no good!

So how as developers can we get around these issues? If we add an additional common-sense requirement and tweak another accordingly, we can create a better way to handle mobile accordion animation:

1. The place the user taps to open or close a tab should not move at any time.
2. Opening a tab simultaneously closes any previously open tab.
3. Opening and closing a tab should have a slide animation, _unless it is in conflict with rule #1._

The secret to making this work lies in one of Javascript's most useful functions: `getBoundingClientRect()`.
