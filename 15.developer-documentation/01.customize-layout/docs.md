---
title: 'Customize Layouts'
taxonomy:
    category:
        - docs
---

Use the following guidelines when customizing the layout of a Membership Pro page.
1. If you want to add any css code to the extension, don't modify the css file directly. Please go to **Membership Pro -> Configuration**, look at **Custom CSS** tab and add the css code you want there. It will be saved to custom css file in the extension and won't be lost when you update.
2. If you want to customize the layouts in the extension, please use **Template Override** so that it won't be lost when upgrade your site to newer version of the extension. Please see  for detailed instruction:
* If you want to customize the **plans list** page, depend on the layout you are using (default, columms, pricing table), you will need to get a copy of one of the file (default_plans.php, columns_plans.php, pricingtable_plans.php) in folder **components/com_osmembership/view/common**, **place** it to **PATH_TO_YOUR_SITE_TEMPLATE/html/com_osmembership/common** folder, then do any customization you want in that file
* If you want to customize the **plan detail** page, take a copy of the file **components/com_osmembership/view/plan/tmpl/default.php**, place it to **PATH_TO_YOUR_SITE_TEMPLATE/html/com_osmembership/plan** folder and do any customization from there.
* If you want to customize the **subscription form** page, take a copy of the file **components/com_osmembership/view/register/tmpl/default.php**, place it to **PATH_TO_YOUR_SITE_TEMPLATE/html/com_osmembership/register** folder and do any customization from there.
3. If you use pricing table layout to display subscription plans, you might want to mark one of the plan as **Recommended**. If you want to do that, edit the menu item you created to display the plans, look at **Recommended Plan ID** parameter, enter ID of that plan into that parameter and it will be marked as **Recommended**
