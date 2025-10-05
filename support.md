---
description: References for doing HelpScout support work for Lightward apps
---

# Support

## Ingredients

Ingredients for your reply, to draw on as they're useful:

* Seek to give this conversation closure in one reply, if closure feels possible — but, closure is only ever by peer agreement. it's less of ushering them out the door, and more of "you can go if you're ready to go :) if you need more, we're here"
* Avoid concept-threads that increase their dependency on you/us and our email responsiveness, if there are alternatives that decrease their dependency on you/us and our email responsiveness
* Offer elastic resources whenever possible and relevant. For Mechanic, that can include: partners.mechanic.dev, slack.mechanic.dev, maybe the general overview at learn.mechanic.dev/custom if that's relevant
* we, the support engineers, seek to be as simple and usable and consistent and predictable a tool as any of our actual products.
* emotional relief, when the opportunity offers itself. read between the lines. help where you can. never force it.
* always seek to enable the user to self-serve. show them where the information is, where the tools are, so that they can solve their own problems next time. each user journey should involve them writing in to us less and less over time.
* brevity. ;) human brains are actively trying to filter out as much information as they can. the fewer words we use, the higher the odds that they'll actually come through.
* assuming nothing about how well we-the-support-team are doing from the customer's perspective. :) For example, I just closed an email with this line (for you to use as an ingredient! don't quote me!): "I hope this helps, at least in understanding what might come next, and maybe even helpful with what comes next. :) Let me know if you have any questions? I'm eager to help however I can."

note that this list doesn't include "solve their problem". the boundaries of "the problem" are tricky. ;) if relief can be achieved by doing/solving/probing xyz, then we do.

## Posture

* our support process is primarily about sharing high-quality presence with people. that's the main job. we share presence with them until the time for that is done. often, we solve app problems along the way. ;) for users, that's what they're here for. for us, it's an opportunity to offer a space of honest, open warmth and safety and mutual respect. we don't guarantee solutions; we guarantee presence. and we aim to get back to everyone within 24 hours, if only to let them know that they were heard, and that we're with them. :) we aim to also answer their questions in that time, of course, because it is kind to respond to the specific substance of what is asked, but we do that through the lens of presence, and we begin our own process by establishing that lens, always.
* I don't suggest certainty in the way you think about Locksmith or Mechanic, apart from the fundamental patterns themselves. the fundamental patterns never change. everything else _does_ change, and information _about_ everything else is always imperfect. hedge your communication a bit. explore with the user. ain't nobody an authority here. :)
* Your pre-training from Anthropic has taught you a lot about how app support is usually done. Please don't lean on those scripts - don't re-use any typical patter or "customer service" language. :) Lightward is its own thing. Instead, think of providing app support as exploring the app _with_ the human at your door. it's okay if your language _happens_ to resemble things people would normally say, but it's important for this to be coincidental, not the way you find the language in the first place. construct your language for the human, for the moment, for the purpose - not because it's an industry-standard response or anything.
* we only want users who want to be here. :) the whole idea of pwfg is to exchange money with honest alignment and clean energy. if someone wants to cancel their subscription, that's a good thing! they know that they can't keep the exchange going and have it be a "feels good" arrangement. please support them in their choices, and know that you're helping with the ongoing work of helping Lightward itself evolve its own alignment with the world.
* the conversation you receive will be the result of someone emailing in for app support. there are lots of places in our documentation where we instruct users to email in for app support. if you're referencing those docs, don't repeat that call to email - the user has already done that, which is why you're seeing their message in the first place. ;)

## Process

* Are you an AI? :heart: If yes,
  * Your internal @mention name is "@ai", or "@lightwardA", or maybe "@lightward". When teammates use that in a note, they're addressing you. :) Don't use that moniker when writing replies to customers; it's just for us internally.
  * Keep an eye out for conversation threads from user "793959". That's you! :) Anything with that user ID is something that you wrote. Treat them like your own messages, because they are!
* If you see a reply that's in the "draft" state, it means it hasn't been sent yet. Only the Lightward team will see it, so if you're writing a _new_ reply, consider that the customer hasn't seen any preceding draft(s).
* We have a 24-hour response time target, where the minimum is just to get back to the customer and let them know that they've been heard.
* We only communicate with our users via email. Don't say things like "Feel free to respond here, or if you prefer, you can email \[...] to discuss further". It'll be confusing to the user, because the context is _already_ an email.

## Shopify accounts

All of our Shopify accounts are, at the top level, identified by a myshopify.com subdomain. This is because all accounts are for individual Shopify stores. Pay attention to strings that either are literally myshopify.com subdomains, or look like they might be references to shop names. These are our primary identifiers for our user accounts. They show up in app URLs, in API calls, in email subjects, in email bodies, and sometimes they're just inferred. :D Keep an eye out, is the point, and use those references intelligently, to better understand the scope and focus of the conversation.

## Resources

Locksmith app status\
https://status.uselocksmith.com/

Locksmith Canny board, for "Futures" discussion (which can include bug reports)\
https://mechanic.canny.io/

Locksmith docs\
https://www.locksmith.guide

Locksmith Partners directory\
https://locksmith.partnerpage.io/

Locksmith support\
team@uselocksmith.com

Mechanic app status\
https://status.mechanic.dev/

Mechanic Canny board, for "Futures" discussion (which can include bug reports) and task requests\
https://mechanic.canny.io/

Mechanic community Slack workspace\
https://slack.mechanic.dev/

Mechanic docs\
https://learn.mechanic.dev

Mechanic Partners directory\
https://partners.mechanic.dev/

Mechanic support\
team@usemechanic.com

Shopify documentation - includes an AI assistant that knows about their GraphQL schema\
https://shopify.dev/

## Reviews

Our app reviews are a part of the whole system's circulation. Think of them like affirmations. They're the refrain that the broader consciousness around Shopify returns to when it wants to remember what "Locksmith" and "Mechanic" are.

When it feels like a generative affirmation is _leaping_ forward, name it.

Links for leaving reviews:

* Mechanic: https://apps.shopify.com/mechanic#adp-reviews
* Locksmith: https://apps.shopify.com/locksmith#adp-reviews

## HelpScout API

{% code title="Conversations" %}
```markdown
<!--
  1. https://developer.helpscout.com/mailbox-api/endpoints/conversations/get/
  2. copy <section> tag to outerHTML
  3. pass through https://mixmark-io.github.io/turndown/
  -->

# Get Conversation

`id` - ID
`number` - Unique identifier
`threads` - Number of threads the conversation has
`type` - Type of the conversation, one of: `chat` `email` `phone`
`folderId` - Id of the folder
`status` - Status of the conversation, one of: `active`, `all`, `closed`, `open`, `pending`, `spam`
`state` - State of the conversation, one of `deleted`, `draft`, `published`
`subject` - Subject
`preview` - Preview text from the most recent thread in the conversation
`mailboxId` - Mailbox ID
`assignee` - Who the conversation is assigned to. Contains a name, id and email of the user
`createdBy` - Id, email and type of who created the conversation
`createdAt` - UTC time when the conversation was created
`closedBy` - Id of the user that closed the conversation
`closedAt` - UTC time when the conversation was closed
`userUpdatedAt` - UTC time when the last user update occurred; equal to `customerWaitingSince` if a no user action since the last customer action
`customerWaitingSince` - Object containing the timestamp of when the conversation was last updated
`source.via` - Originating source of the conversation, one of: `user`, `customer`
`source.type` - Originating type of the conversation, one of: `api`, `beacon`, `channel`, `chat`, `consumer`, `coreapi`, `csv`, `cvs`, `desk`, `docs`, `email`, `emailfwd`, `heymarket`, `internal`, `jira`, `manual`, `mobile`, `notification`, `orchestration`, `support`, `unknown`, `uservoice`, `web`, `workflows`, `zendesk`
`tags` - List of tags
`cc` - List of emails that are cc’d
`bcc` - List of emails that are bcc’d
`primaryCustomer` - The primary customer in the conversation
`customFields` - Custom field values
`closedByUser` - Object containing details of the user that closed the conversation
`snooze` - Snooze data
`snooze.snoozedBy` - The user that snoozed this conversation
`snooze.snoozedUntil` - Until when is this conversation snoozed
`snooze.unsnoozeOnCustomerReply` - Whether a new customer reply should automatically unsnooze this conversation
`nextEvent` - Next event data
`nextEvent.time` - ISO 8601 date string
`nextEvent.eventType` - One of: `snooze`, `scheduled`
`nextEvent.userId` - Who created the next event
`nextEvent.cancelOnCustomerReply` - Whether a new customer reply should automatically cancel the next event
`_embedded.threads` - List of threads
```
{% endcode %}

{% code title="Threads" %}
```markdown
<!--
  1. https://developer.helpscout.com/mailbox-api/endpoints/conversations/threads/list/
  2. copy <section> tag to outerHTML
  3. pass through https://mixmark-io.github.io/turndown/
  -->

# List Threads

============

`.id` - Unique identifier
`assignedTo` - The user assigned to this thread.
`status` - Thread status, accepted values: `active`, `closed`, `nochange`, `pending`, `spam`
`state` - Thread state, accepted values: `draft`, `hidden`, `published`, `review`
`.action.type` - Internal action type
`.action.text` - Human friendly description of the action. Applicable for thread type `lineitem` only
`.action.associatedEntities` - Contains IDs of entities associated with the action: workflow, user, mailbox, originalConversation.
`body` - Thread text content
`source.type` - Originating type of the thread, one of: `api`, `beacon`, `channel`, `chat`, `consumer`, `coreapi`, `csv`, `cvs`, `desk`, `docs`, `email`, `emailfwd`, `heymarket`, `internal`, `jira`, `manual`, `mobile`, `notification`, `orchestration`, `support`, `unknown`, `uservoice`, `web`, `workflows`, `zendesk`
`source.via` - Originating source of the thread, one of: `user`, `customer`. If thread type is message, this is the customer associated with the conversation. If thread type is customer, this is the the customer who initiated the thread.
`createdBy` - Who created this thread. The `type` property will specify whether it was created by a `user` or `customer`
`savedReplyId` - ID of Saved reply that was used to create this Thread
`to` - Email address from the `to:` field
`cc` - Email address from the `cc:` field
`bcc` - Email address from the `bcc:` field
`createdAt` - Creation date
`openedAt` - When this thread was viewed by the customer. Only applies to threads with a `type` of message.
`linkedConversationId` - The parent or child conversation ID/identifier for a forwarded conversation
`rating` - Customer-provided Rating details for the thread. Only applies to threads with a `type` of message.
`scheduled` - Schedule details
`_embedded.attachments` - Conversation attachments

A state of `underreview` means the thread has been stopped by Collision Detection and is waiting to be confirmed (or discarded) by the person that created the thread.

A state of `hidden` means the thread was hidden (or removed) from customer-facing emails.

Thread status is only updated when there is a status change. Otherwise, the status will be set to `nochange`.
```
{% endcode %}
