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

# ⚖️ Change Mode

By default **Guest Mode** has enabled.

### Option 1  (Locally, Higher priority)

Set $guestMode, true in related model. This will effect to that model only.

```php
use Illuminate\Database\Eloquent\Model;
use LakM\Comments\Concerns\Commentable;
use LakM\Comments\Contracts\CommentableContract;

class Post extends Model implements CommentableContract
{
    use Commentable;

    $guestMode = false; // Auth mode
}
```

### Option 2 (Globally)

You can set guest mode enabled variable true in the config file. This will globally enabled the guest mode.

```php
// comments.php

guest_mode => [
    'enabled' => false, // Auth Mode
]
```
