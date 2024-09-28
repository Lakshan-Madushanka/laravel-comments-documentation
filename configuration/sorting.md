---
icon: arrow-down-wide-short
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

# Sorting

### Sorting Comments

Available Options: All the options in [`LakM\Comments\Enums\Sort`](https://github.com/Lakshan-Madushanka/laravel-comments/blob/main/src/Enums/Sort.php) class.

* `Sort::TOP` - Sort by custom algorithm (default).
* `Sort::LATEST` - Sort by latest comments.
* `Sort::OLDEST` - Sort by oldest comments.
* `Sort::REPLIES` - Sort by replies count &#x20;

#### Overwrite default sort order

#### **Globally**

Change the `default_sort` option in `comments.config` file.

```
// comments.config

use LakM\Comments\Enums\Sort;

return [
    // Default comments sort order, See Sort::class for available values
    'default_sort' => Sort::TOP,
];
```

#### **Model-wise (Higher priority)**

Define variable `$commmentsSortOrder` and set the value in [`commentable`](../basics/usage.md#commentable-model) model.

```
use Illuminate\Database\Eloquent\Model;
use LakM\Comments\Concerns\Commentable;
use LakM\Comments\Contracts\CommentableContract;
use LakM\Comments\Enums\Sort;

class Post extends Model implements CommentableContract
{
    use Commentable;

    $commmentsSortOrder = Sort::TOP;
}
```

### Sorting Replies

Available Options: Following options in [`LakM\Comments\Enums\Sort`](https://github.com/Lakshan-Madushanka/laravel-comments/blob/main/src/Enums/Sort.php) class.

* `Sort::LATEST` - Sort by latest comments.
* `Sort::OLDEST` - Sort by oldest comments.

#### Overwrite default sort order

#### Globally

Change the `reply.default_sort` option in `comments.config` file.

```
// comments.config

use LakM\Comments\Enums\Sort;

return [
    'reply' => [
        // Default comments sort order, available values: Sort::LATEST, Sort::OLDEST
        'default_sort' => Sort::LATEST,
    ],
];
```

#### **Model-wise (Higher priority)**

Define variable `$repliesSortOrder` and set the value in [`commentable`](../basics/usage.md#commentable-model) model.

```
use Illuminate\Database\Eloquent\Model;
use LakM\Comments\Concerns\Commentable;
use LakM\Comments\Contracts\CommentableContract;
use LakM\Comments\Enums\Sort;

class Post extends Model implements CommentableContract
{
    use Commentable;

    $repliesSortOrder = Sort::TOP;
}
```
