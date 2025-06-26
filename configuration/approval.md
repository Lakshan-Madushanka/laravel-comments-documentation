---
description: >-
  When enabled only approved comments will be displayed. To approve a comment
  "approved" column must be set to true (by default false) in comments table.
---

# ⛔ Approval

### Enable/Disable Comments Approval

#### Locally

Set `approvalRequired` property true to enable.

```php
use LakM\Commenter\Concerns\Commentable;

class Post extends Model
{
    use Commentable;
    
    $approvalRequired = true; // This will enable comments approval
}
```

#### Globally

Set `approval_required` true to globally enable.

```php
// commenter.php
"approval_required" => true,
```

### Enable/Disable replies approval

Set `reply.approval_required` true to globally enable.

```php
// commenter.php
"reply" => [
    "approval_required" => true,
],
```
