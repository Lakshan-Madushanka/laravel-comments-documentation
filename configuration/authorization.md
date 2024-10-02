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

# 🔐 Authorization

All the policies used by the package globally are defined in the `permission` array. You are free to define your own [policies](https://laravel.com/docs/11.x/authorization).

### Define global policies

```php
// comments.php

 'permissions' => [
    'create-comment' => [CommentPolicy::class, 'create'],
    'update-comment' => [CommentPolicy::class, 'update'],
    'delete-comment' => [CommentPolicy::class, 'delete'],
    'create-reply' => [ReplyPolicy::class, 'create'],
    'update-reply' => [ReplyPolicy::class, 'update'],
    'delete-reply' => [ReplyPolicy::class, 'delete'],
    ],
```

### Define authorization logic locally

You can define authorization logic model-wise using the following methods. These methods take priority for the relevant model, disregarding global policies.

```php
use LakM\Comments\Concerns\Commentable;

class Post extends Model
{
    use Commentable;
    
    // Create comment
    public function commentCanCreate(): bool
    {
        return true;
    }
    
    // Edit comment
    public function commentCanEdit(): bool
    {
        return true;
    }
    
    // Delete comment
    public function commentCanDelete(): bool
    {
        return true;
    }
}
```
