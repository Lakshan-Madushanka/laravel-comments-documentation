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
        @commenterStyles
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
        @commenterScripts
    </body>
</html>
```

#### Manually including Livewire's frontend assets <a href="#manually-including-livewires-frontend-assets" id="manually-including-livewires-frontend-assets"></a>

If you manually include livewire frontend ([documentation](https://livewire.laravel.com/docs/installation#manually-bundling-livewire-and-alpine)) assets make sure `@commenterStyles` is included before `@livewireStyles` and`@commenterScripts` is included before the `@livewireScripts`

```html
<html>
    <head>
        @commenterStyles
        @livewireStyles
    </head>
    <body>
        @commenterScripts
        @livewireScripts
    </body>
</html>
```

#### Manually bundling Livewire and Alpine <a href="#manually-bundling-livewire-and-alpine" id="manually-bundling-livewire-and-alpine"></a>

If you manually bundle livewire frontend ([documentation](https://livewire.laravel.com/docs/installation#manually-bundling-livewire-and-alpine)) assets make sure `@commenterStyles` is included before `@livewireStyles` and`@commenterScripts` is included before the script that includes livewire bundle.

```
<html>
<head>
    @commenterStyles
    @livewireStyles
    
    @commenterScripts
    @vite(['resources/js/app.js'])
</head>
<body>
    {{ $slot }}
 
    @livewireScriptConfig 
</body>
</html>
```

{% hint style="info" %}
To improve performance we recommend adding script at the end of the body tag.
{% endhint %}

Optionally you can publish the views using below command,

```bash
php artisan vendor:publish --tag=commenter-views
```
