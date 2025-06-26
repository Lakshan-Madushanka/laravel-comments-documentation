---
icon: table
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

# Migrations/Tables

Commenter publishes following three migrations/tables. When migrating these tables, name collisions may occur if your project already uses the same table names as Commenter's tables. This page provides guidance on how to avoid such collisions.

| Migration Name                                                                                                                                   | Table Name |
| ------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- |
| [create\_comments\_table](https://github.com/Lakshan-Madushanka/laravel-comments/blob/main/database/migrations/create_comments_table.php.stub)   | comments   |
| [create\_guests\_table](https://github.com/Lakshan-Madushanka/laravel-comments/blob/main/database/migrations/create_guests_table.php.stub)       | guests     |
| [create\_reactions\_table](https://github.com/Lakshan-Madushanka/laravel-comments/blob/main/database/migrations/create_reactions_table.php.stub) | reactions  |

Imagine your project already has a `comments` table, and you want to rename Commenter's `comments` table to `lakm_comments`.

#### Step-1

Create a model.&#x20;

```
php artisan make:model LakmComment
```

#### Step-2

Extend the model with the relevant base model. You can find the respective base models in the `config/commenter.php` configuration file. Then, define the table name in the `$table` property, with the public accessible.

```
 
 // config/commenter.php
 
 use LakM\Comments\Models\Comment;
 
 /**
   * Comment Model
   * Must extend base model LakM\Comments\Models\Comment
   */
  'model' => Comment::class,
```

```
// app/models/LakmComment.php

<?php

namespace App\Models;

use LakM\Comments\Models\Comment;

class LakmComment extends Comment
{
    public $table = 'lakm_comments'; // This line is a must have
}

?>
```

#### Step-3

Go to config/comment.php file and change the relevant model class.

```
// config/commenter.php
 
 use App\Models\LakmComment;
 
 /**
   * Comment Model
   * Must extend base model LakM\Comments\Models\Comment
   */
  'model' => LakmComment::class,
```

#### Step-4

Go to the relevant migration file and change the table name.

```
// database/migrations/{timestamp}_create_comments_table.php

 public function up(): void
    {
        Schema::create('lakm_comments', function (Blueprint $table) {
            ...
        });

        Schema::table('lakm_comments', function (Blueprint $table) {
            $table->foreign('reply_id')->references('id')->on('lakm_comments')->cascadeOnDelete();
        });
    }

    /**
     * Reverse the migrations.
     */
    public function down(): void
    {
        Schema::dropIfExists('lakm_comments');
    }
```

{% hint style="info" %}
Though it is not necessary, it is recommended to rename the migration file as well. In the above example, it can be renamed to `{timestamp}_create_lakm_comments_table.php`.
{% endhint %}
