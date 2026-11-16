---
title: 'Enable Captcha'
---

If you want to enable Captcha to protect subscription form in Membersip Pro from spams, please follow the instructions below:

1. Configure your site to use captcha, see instructions from Joomla documentation at [https://docs.joomla.org/J3.x:Google_ReCaptcha](https://docs.joomla.org/J3.x:Google_ReCaptcha). Keep in mind that you can use any captcha plugin you want. Remember to set **Default Captcha** config option in global configuration of your site to the captcha plugin you want to use. 
2. Go to **Membership Pro** -> **Configuration**, look at **Enable Captcha** config option and change it to one of the following value:
* **Yes**: The system will show captcha protection on subscription form for both Public and Logged in users.
* **Only For Public Users**: The system will only show captcha on subscription form for Public users only.