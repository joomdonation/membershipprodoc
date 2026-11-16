---
title: 'Restrict access to part of article'
---

This method can be used if you want to **show intro text** of a Joomla article and only allow subscribers from certain subscription plans read the full article. You can see an example on our demo site at http://membershippro.joomservices.com/articles-restriction/9-months-membership-article-restriction. Basically, when a user access to the article:

1. If he has an active subscription of a plan which is allowed to access the article, he can read the full article.
2. If he doesn't have an active subscription of the plan, he will just show a small part of the article. The remaining part of the article (admin can decide which part he want to hide) will be hided and a message will display to users ask them to sign up for the plans if they want to access the full article.

To restrict access to articles using this method, you can use the Content - Membership Pro Content Restriction plugin in Membership Pro. The steps are:

1. Go to Extensions -> Plugins Manager, find and publish the plugin **Content - Membership Pro Content Restriction**
2. Use this syntax **{mprestriction ids="1"}**_The text you want to hide must be inserted between here_**{/mprestriction}** to restrict access to the article to subscribers of the plan you want. Below is the explanation of the syntax:
* ids="1" mean only users have active subscription of Plan with ID = 1 can see the text. You can change 1 to ID of any plans you want
* You can allow subscribers from different subscription plans to see this text, just separate the plan ids by comma. For example, If you enter ids="1,3" for example, subscribers from plan with ID = 1 or ID = 3 will be able to see the text and so on....
* ids="*"  mean users can see the text if they sign up for any plans in your system.
3. Use this syntax **{mprestriction ids="!1"}**_The text you want to hide must be inserted between here_**{/mprestriction}** to restrict access to the article to subscribers of the plan you want. Below is the explanation of the syntax:
* ids="!1" mean users will see the text if he has not signed up for the plan with ID = 1.
* ids="!1,2,3" mean users will see the text if has has not signed up for any of these plans (ID = 1 or = 2 or =3)
* ids="!*"  mean users will see the text if they has not signed up for any plans in your system