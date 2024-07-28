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

### Define authorization logics locally

You can define authorization logics model-wise using the following methods. These methods take priority for the relevant model, disregarding global policies.

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
