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

# 🔨 Installation

#### Step 1 :

```bash
composer require lakm/laravel-comments -W
```

#### Step 2 :

```bash
php artisan commenter:install
```

#### Step 3 :

Include styles in your layout.

```html
<html>
    <head>
        @commentsStyles
    </head>
</html>
```

{% hint style="info" %}
To avoid CSS name conflicts, we recommend adding your styles to the end of the head tag.
{% endhint %}

Include scripts in your layout

```html
<html>
    <body>
        @commentsScripts
    </body>
</html>
```

{% hint style="info" %}
To improve performance we recommend adding script at the end of the body tag.
{% endhint %}

Optionally you can publish the views using below command,

```bash
php artisan vendor:publish --tag=comments-views
```
