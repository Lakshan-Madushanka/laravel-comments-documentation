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
import LakM\Comments\Concerns\Commentable;
import LakM\Comments\Contracts\CommentableContract;

class Post extends Model implements CommentableContract{
    use Commentable;
}
```

### Implement <mark style="color:purple;">CommenterContract</mark> and import <mark style="color:purple;">Commenter</mark> trait in commenter model.

```php
import LakM\Comments\Concerns\Commenter;
import LakM\Comments\Contracts\CommenterContract;

class Post extends Model implements CommenterContract{
    use Commenter;
}
```

### Then simply include component in your blade file

```html
<x-comments :model="$post" />
```

or you can use components seperatly,

```html
<div x-cloak x-data class="space-y-8">
    <livewire:comments-list :model="$model" />
    <hr class="text-gray-400" />
    <livewire:comments-create-form :model="$model" />
</div>

```
