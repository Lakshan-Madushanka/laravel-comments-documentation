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

# 🚧 Validations

All the validation rules can be found in the `ValidationRules.php` file located in the root directory.

### Overwrite Validation Rules

You can define your own rules using the `createCommentUsing(callable $callable)` and `updateCommentUsing(callable $callable)` properties in the `boot` method of a service provider.

```
// AppServiceProvider.php

use LakM\Comments\ValidationRules;

public function boot()
{
    // Related commentable model will be injected to callable.
    ValidationRules::createCommentUsing(function (Model Post) {
        return [
            'guest_email' => [
                new RequiredIf($model->guestModeEnabled() && config('comments.guest_mode.email_enabled')),
                'nullable',
                'email',
                Rule::unique($commentTableName, 'guest_email')->ignore(request()->ip(), 'ip_address')
            ],
            'guest_name' => [
                new RequiredIf($model->guestModeEnabled()),
                Rule::unique($commentTableName, 'guest_name')->ignore(request()->ip(), 'ip_address')
            ],
            'text' => ['required'],
        ];
    })
}
```

