---
title: 'Credit-card payment option is not available on PayPal'
---

Sometimes, you might find that your customers were not able to pay with their credit card when they are being redirected to PayPal. You might think that it causes by Membership Pro. However, it is actually all handled by PayPal and out of our control, we can only redirect customers to PayPal with correct payment amount, all the process happens on PayPal website is handled by PayPal and we won't have any control over it.

## Conditions to have credit card option available
It's related to how your Account is set up.

* Your account must be either Premier or Business.
* PayPal Account Optional is turned on - this enables non PP Members to pay by Credit Card
* The email address you use to log into your PayPal Account must be verified.
* The "business" variable value in your button code must be a verified email address or your Business ID.
* Bank account registered and verified/tested - so you can transfer funds
* Credit card registered - (not required but a good idea)

To turn on the PayPal Account Optional feature:
Log in to your PayPal Account, select "Edit Profile", under "Selling Preferences", select "Website Payment Preferences", scroll down to "PayPal Account Optional".

## There are specific reasons the Credit Card Option may not be available.
* You are using the wrong email address, an unverified email address or Business ID for your "business" variable value.
* The country you reside in. Not all countries have all the PayPal features available.
* The country your customers reside in. Not all countries have all PayPal features available.
* The IP address of your hosted site is on a blocked list.

Check out this [link](https://www.paypal.com/us/cgi-bin/webscr?cmd=_display-country-functionality-outside&dispatch=5885d80a13c0db1fca8cb0621aa94a5f6fa451543ea8737723e84f3b2eb6e293), it can tell you what features are available to the individual counties.

## It might related to cookie
Last, you have your PayPal Account setup properly but, still don't see the Credit Card Option or only see a small link to the Credit Card Option.

It's all about the cookies. The PayPal Screens are designed to be displayed in a specific way and what you see is based on the cookies and/or your PayPal Account configuration.

PayPal relies on the use of cookies to track what's in your cart and retain other info about you and therefore the screen that is displayed may not be the screen you expect to see. If you are a new customer visiting PayPal for the first time, the Credit Card Option will be clearly displayed.

If this is your second or third visit to PayPal and your previous cookie has not expired, PayPal now views you as a returning customer. You will get a screen with a small link to the Credit Card Option. Although this is not as obvious to the customer, the Credit Card Option is still available. For example, the cookie that holds the cart info will retain that info for up to 21 days. The only way it will change is if you remove the items selected from the cart or delete the cookie.

If you are testing your web pages, creating new code or making changes, etc., simply delete your web browser's cookies, then close your web browser, reopen it and try your web pages again. When you view the PayPal Screens, you will now get the screen with the Credit Card Option because PayPal views you as a new visitor.

Other reasons for deleting cookies. Let's say you changed your business email address or business graphic logo. If you don't delete the cookies before you test, you will still see the old information.

## Still could not see credit card option
As I mentioned at the beginning, it is all handled by PayPal, so if all the above conditions are OK but you still could not see credit card option, then the best thing you can do is contact PayPal, ask them to check it for you. Please remember to mention that we use **Paypal Website Payment Standard** integration method so that they can check it easier and faster. Hopefully, they will be able to figure out the reason and guide you to change it




