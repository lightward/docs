# mechanic task code

Hey Isaac,

Sure, I'll write a review tomorrow 😄

Thanks for helping me out! I have a question though.

An external app creates discount codes in Shopify, and then I need to create a specific discount type which we will use. How would you make it that the discountCodeBxgyCreate only happens after the discountCodeDelete is completed.

```
{% comment %} Delete the triggered Shopify discount {% endcomment %} {% log 'Deleting Discount based on the given discount_id' %} {% action "shopify" %} mutation { [snip]
```

***

Hey ████! :) Excellent question. I can help by showing you where help's available:

* https://learn.mechanic.dev/techniques/responding-to-action-results — Platform documentation on the kind of mechanism you'll need here
* https://slack.mechanic.dev/ — Our community Slack workspace! This is the right spot to work through code development questions, with folks who've seen it all. :)

I can't get into the code-level work with you, but I'm here with you as you're navigating resources. Let me know if you've got questions?

Cheers,

\=Isaac

***

(An internal Lightward note on this one: we always route each need to the place that can serve that need with the most elastic availability. That's why we don't do custom code, or even _consult_ on custom code. The probability of a knowledgeable developer being awake and available is much more favorable in our community spaces, so we save a lot of probable grief by just routing needs like this over in those directions immediately.)
