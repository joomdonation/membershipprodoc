---
title: 'Coupon is not available on subscription form'
visible: true
---

After creating coupon codes in Membership Pro, you go to frontend of your site, try to sign up but still don't see coupon input available for you to enter coupon code to receive discount. That might hapen because:

1. You haven't enabled coupon feature yet. Go to Membership Pro -> Configuration, check and make sure **Enable Coupon** parameter set to Yes
2. You will also check and make sure there is at least one valid coupon code is available for the plan you subscribed for:
- Check the Plan setting, make sure it set to All Plans or have the plan you are subscribing for selected
- Make check and make sure current date is between **Valid From Date** and **Valid To Date** setting of the coupon. Better, leave the two settings empty
