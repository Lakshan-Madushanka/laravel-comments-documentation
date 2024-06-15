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

# 😍 Reactions

You can enable any number of reactions on both sides, left and right.  By default following reactions have set.

* Like
* Dislike
* Happy
* Love
* Sad

### Defining Reactions

```
// comments.php

'reactions' => [
// Fill color is displayed after the current user reacted.
  'angry' => ['position' => 'left', 'fill' => 'yellow'];
]
```

### Set Icon

#### Publish views

```
php artisan vendor:publish --tag=comments-views
```

Create a blade file with the same name as the reaction name and include the icon in it in the following directory.

```
// Followig create the angry reaction

|--resources
   |--views 
      |--vendor
         |--comments
            |--components
               |--icons
                  |--angry.blade.php
```
