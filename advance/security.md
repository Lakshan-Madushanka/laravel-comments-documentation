---
description: >-
  Security is one of the major factors we considered when developing this
  package. We have taken several actions to strengthen its security, which are
  described on this page.
---

# 🔏 Security

### XSS Protection

The package uses the  [Quill](https://quilljs.com/) editor to provide rich features such as headers, code blocks, and lists. Although the editor itself filters vulnerable inputs, we haven't relied on it solely. We also filter inputs using the [Graham-Campbell/Security](https://github.com/GrahamCampbell/Security-Core) package. We believe these two layers of security provide solid protection against XSS attacks.

### Spam Protection

Spam can cause significant damage to your commenting system by adding redundant, mutated comments, and it can also harm your site through attacks like DOS. We have used a [ spatie/laravel-honeypot](https://github.com/spatie/laravel-honeypot) package  to prevent spam invasion, but we cannot stop DOS attacks. For that, we recommend adding some robot checks.



{% hint style="warning" %}
Though we have taken some steps to mitigate security attacks we can never be perfect in security. If you found any vulnerability please don't use issue tracker instead send email to [epmadushanka@gmail.com](https://app.gitbook.com/u/nKij7pF9fHcrjwKjDmCetGQGTnZ2)
{% endhint %}
