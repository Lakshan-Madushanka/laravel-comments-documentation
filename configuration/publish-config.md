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

# 📜 Publish Config

### Publish config file

```bash
php artisan vendor:publish --tag=commenter-config
```

{% hint style="info" %}
You don't need to explicitly execute the above command, as the package publishes it when you run the [commenter:install](../basics/installation.md#step-2) command during installation.
{% endhint %}

The above command publishes the package's config file, named **commenter.php**, into the project's config directory.
