---
title: 'Conflict With Helix Template Framework'
published: true
---

If you are using a template built base on Helix Template Framework from JoomShaper, you might get some issues when using Membership Pro on frontend of Joomla 4 websites. Below are details and solution:

1. Toolbar Buttons for frontend management do not work

- I reported to them few months ago and provided a temp solution https://github.com/JoomShaper/helix-ultimate/issues/243#issuecomment-976231375 . Sadly, until now, they still haven't fixed it yet

2. Edit a subscription record from frontend does not work

It causes by a bug from the template overriding Joomla User Form Field. The solution is removing the override at PATH_TO_TEMPLATE/html/layouts/joomla/form/field/user.php

3. Date Picker Field always show time and causes parse error

It causes by a bug from the template overriding Joomla Calendar Form Field. The solution is removing the override at PATH_TO_TEMPLATE/html/layouts/joomla/form/field/calendar.php
