---
title: 'Content - Membership Plans'
---

This plugin displays selected subscription plans in a Joomla article or on another page that supports Joomla content plugins, such as a K2 item.

If you want to use this feature, please follow the instructions below:

1. Go to **System -> Plugins**, find the plugin **Content - Membership Plans**, click on it to edit. Choose the layout you want (default, columns or pricing table layout) in **Layout** parameter. Remember to change the Status to **Enabled**, then press Save button in the toolbar
2. Now, edit the article you want to display subscription plans, enter the syntax below:
* {membershipplans ids="*"} => it will display all published plans in the article.
* {membershipplans ids="cat-3"} => It will display all subscription plans from the category with ID = 3.
* {membershipplans ids="2,4,5"} => It will display all subscription plans with ID = 2, 4, OR 5.