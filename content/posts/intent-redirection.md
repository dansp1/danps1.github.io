---
title: "Intent Redirection"
date: 2024-08-28
tags: ["Android"]
---

![banner](/images/intent-redir-banner.png)

## Overview

Hey fellow readers, welcome to today's blog post!

We are going to discuss some Android hacking topics. The goal is not to delve **too** deeply into general concepts, such as what an intent filter is.

The idea here is to practice a particular technique that can be used in your daily pentests and bug hunting in this beautiful world of Android hacking.

According to the official Android documentation:

> An intent redirection occurs when an attacker can partially or fully control the contents of an intent used to launch a new component in the context of a vulnerable app.

This definition seems quite straightforward and easy to understand if you already have a basic understanding of how the Android ecosystem works. For example:

- What exactly is a "component" in this scenario?
- How could an attacker gain partial or full control of an intent used to launch a new component?

Before we dive into the specifics of exploiting such a vulnerability, let's take a look at these questions.

### Defining Components

When the definitions talks about "Components" it references the app components that act as building blocks for each Android app.

- Activities
- Services
- Broadcast Receivers
- Content Providers

In this particular post we are going to use the `Activity` component to demonstrate the vulnerability, but the concept can be applied to the others.

### Controlling intents

I know, I know... I mentioned earlier that I wouldn’t delve into what an `Intent` is, but to understand the attack, we need some basic background on it. An `Intent` is a complex object, so I'll provide just enough information to follow this walkthrough. For more details, check the references at the bottom.

Think of an `Intent` as a box that you can use to store data and pass it around easily. It typically has several key attributes, such as the class name (for explicit intents), actions, extra fields, and so on. It can also holds another intent! How great is that??


