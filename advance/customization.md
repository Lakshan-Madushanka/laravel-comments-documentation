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

# 🛟 Customization

### &#x20;Views

You can customize all the views by publishing them using below commands,

```bash
php artisan vendor:publish --tag=comments-views
```

### Assets

Package install command `commenter:install`, publish assets to the `\public\vendor\lakm\laravel-comments` directory.

Here is the command to publish them manually.

```
    php artisan vendor:publish --tag=comments-assets
```

### Build assets

You can build assets using any assets building tool. By default, package has used laravel vite plugin. Make sure to use right build directory `public\vendor\lakm\laravel-comments\build`

{% hint style="warning" %}
When building assets the re should be only one input file and that is should be `app.js`. You can do that as following using vite.
{% endhint %}

```javascript
// vite.config.js

import { defineConfig } from 'vite';
import laravel from 'laravel-vite-plugin';

export default defineConfig({
   plugins: [
       laravel({
           hotFile: 'public/vendor/lakm/laravel-comments/comments.hot',
           buildDirectory: 'vendor/lakm/laravel-comments/build', // This is important
           input: ['resources/js/app.js'], // This is important
           refresh: true,
       }),
   ],
});
```
