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

### Views

You can customize all the views by publishing them using below commands,

```bash
php artisan vendor:publish --tag=commenter-views
```

### Assets

Package install command `commenter:install`, publish assets to the `\public\vendor\lakm\commenter` directory.

Here is the command to publish them manually.

```
    php artisan vendor:publish --tag=commenter-assets
```

### Build assets

You can build assets using any assets building tool. By default, package has used laravel vite plugin. Make sure to use right build directory `public\vendor\lakm\commenter\build`

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
           hotFile: 'public/vendor/lakm/commenter/commenter.hot',
           buildDirectory: 'vendor/lakm/commenter/build', // This is important
           input: ['resources/js/app.js'], // This is important
           refresh: true,
       }),
   ],
});
```
