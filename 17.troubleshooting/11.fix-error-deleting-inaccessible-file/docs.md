---
title: 'Fix Error Deleting Inaccessible File'
visible: true
---

Sometime, when you update Membership Pro extension, you will receive an error like below and cause update error

> Joomla\Filesystem\File::delete: Failed deleting inaccessible file autoload.php

This issue causes by some changes in Joomla 3.9.0 API, see [https://github.com/joomla/joomla-cms/issues/23504](https://github.com/joomla/joomla-cms/issues/23504) for more detailed information if needed.

To solve this issue, please follow the instructions below:

1. Open the file libraries/vendor/joomla/filesystem/src/File.php

2. Find this line of code:

```php
if (!Path::canChmod($file))
```

Change it to:

```php
if (!Path::canChmod($file) && false)
```
Then try again, upgrade should work well.