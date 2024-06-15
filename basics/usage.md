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

### Import <mark style="color:purple;">Commentable</mark> trait in commentable model.

```
import LakM\Comments\Concerns\Commentable;

class Post extends Model {
    use Commentable;
}
```

### Import <mark style="color:purple;">Commenter</mark> trait in commenter model.

```
import LakM\Comments\Concerns\Commenter;

class Post extends Model {
    use Commenter;
}
```

### Then simply include component in your blade file

```
<x-comments :model="$post" />
```

or you can use components seperatly,

```
<div x-cloak x-data class="space-y-8">
    <livewire:comments-list :model="$model" />
    <hr class="text-gray-400" />
    <livewire:comments-create-form :model="$model" />
</div>

```
