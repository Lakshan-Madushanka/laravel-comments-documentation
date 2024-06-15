---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# 🧠 Concept

Package provides two commenting modes as below:

* Authentication/Auth mode.
* Guest mode.

### Auth Mode

This mode is enabled for authenticated users, so your project must have a built-in authentication system.

### Guest Mode

This mode is for non-authenticated users.

{% hint style="info" %}
These two modes are mutually exclusive, meaning you can't use both simultaneously for a model. It must be either auth mode or guest mode.
{% endhint %}
