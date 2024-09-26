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

There are three modes available.

* Auth Mode
* Guest Mode
* Secured Mode

By default **Guest Mode** has enabled.

### Option 1 (Locally, Higher priority)

Set `$guestMode`, true in related model. This will effect to that model only.

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

### Secured Guest Mode (Recommended)

The default guest mode relies on user's IP address, which is not ideal for security. For a more secure guest mode, consider enabling the secured guest mode feature.

```bash
// comments.php

guest_mode => [
    'enabled' => true,
    'secured' => true,
]
```

#### How it works

Users are required to confirm their email address via a verification link before commenting. This system doesn't interact with the default `users` table or the `web` auth guard. Instead, it operates through a dedicated `guests` table and a custom `guest` guard. This ensures that your default authentication system remains unaffected, allowing the package to work seamlessly even on sites that already have an existing authentication setup.
