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

# ⚡ Events

Commenter triggers the following events for your handlers to listen to:

{% hint style="info" %}
Consult Laravel documentation to learn more about [event and handlers](https://laravel.com/docs/11.x/events).
{% endhint %}

<table data-full-width="true"><thead><tr><th width="365">Event Name</th><th>Properties</th><th>Description</th></tr></thead><tbody><tr><td><pre><code>LakM\Comments\Events\CommentCreated
</code></pre></td><td><pre><code>public LakM\Comments\Models\Comment $model
</code></pre></td><td>After a comment is created successfully.</td></tr><tr><td><pre><code>LakM\Comments\Events\CommentDeleted
</code></pre></td><td><pre><code>public LakM\Comments\Models\Comment $model
</code></pre></td><td>After a comment is deleted.</td></tr><tr><td><pre><code>LakM\Comments\Events\CommentUpdated
</code></pre></td><td><pre><code>public LakM\Comments\Models\Comment $model
</code></pre></td><td>After a comment is updated.</td></tr><tr><td><pre><code>LakM\Comments\Events\CommentReplyCreated
</code></pre></td><td><pre><code>public LakM\Comments\Models\Comment $model,
public LakM\Comments\Models\Reply $reply
</code></pre></td><td>After a reply is created.</td></tr><tr><td><pre><code>LakM\Comments\Events\CommentReplyDeleted
</code></pre></td><td><pre><code>public LakM\Comments\Models\Reply $model
</code></pre></td><td>After a reply is deleted.</td></tr><tr><td><pre><code>LakM\Comments\Events\CommentReplyUpdated
</code></pre></td><td><pre><code>public LakM\Comments\Models\Reply $model
</code></pre></td><td>After a reply is updated.</td></tr></tbody></table>
