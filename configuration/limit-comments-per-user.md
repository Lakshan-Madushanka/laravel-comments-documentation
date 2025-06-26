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

# ⏲️ Limit comments per user

You can limit the number of comment per user.

### Set Global Limit

```php
// commenter.php

limit = 10; // now a user can make only 10 comments for a model. 
```

### Locally

```php
use LakM\Commenter\Concerns\Commentable;

class Post extends Model
{
    use Commentable;
    
    $commentLimit = 10;
}
```
