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

# ✈️ Usage

### <mark style="color:purple;">Commentable</mark> Model

Model that the comment belongs to.

### <mark style="color:purple;">Commenter</mark> Model

Model that the user belongs to.

### Implement <mark style="color:purple;">CommentableContract</mark> and import <mark style="color:purple;">Commentable</mark> trait in commentable model.

```php
use LakM\Comments\Concerns\Commentable;
use LakM\Comments\Contracts\CommentableContract;

class Post extends Model implements CommentableContract
{
    use Commentable;
}
```

### Implement <mark style="color:purple;">CommenterContract</mark> and import <mark style="color:purple;">Commenter</mark> trait in commenter model.

```php
use LakM\Comments\Concerns\Commenter;
use LakM\Comments\Contracts\CommenterContract;

class User extends Model implements CommenterContract
{
    use Commenter;
}
```

### Include styles in your layout.

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

### Include scripts in your layout

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

### Then simply include component in your blade file

```html
<x-comments:index :model="$post" />
```

{% hint style="danger" %}
You can omit the index part but make sure to include the double colon. Otherwise Laravel will search for the component in project instead of the package.

```html
<x-comments:: :model="$post" />
```
{% endhint %}

or you can use components separately,

```html
<div x-cloak x-data class="space-y-8">
    <livewire:comments-list :model="$model" />
    <hr class="text-gray-400" />
    <livewire:comments-create-form :model="$model" />
</div>

```
