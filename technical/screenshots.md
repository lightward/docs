---
description: And now, some gloriously concrete details.
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Screenshots

We do a lot of documentation, and a lot of email. Screenshots come up a lot.

## Priorities

* Let the subject be one thing.
  * Even if it's a multi-component thing.
  * Stay focused. Be clear with yourself about what the screenshot is for.
* Don't distract the user.
  * Avoid inconsistencies in your screenshot capture.
  * Avoid elements (including data) that are irrelevant.
* Make it easy for someone to locate the thing for themselves.
  * Given a particular app URL, make it easy for someone to orient themselves upon arrival, such that they can locate the subject of your screenshot for themselves.
* If all else fails, use a red box.
  * Avoid it, but, you know, don't hesitate to use it if it's the only way.

## Strategies

### Pad your crops the way the UI pads content

Our app UI (powered by Polaris) always has a consistent amount of padding around each element, be it text or an interactive selector. When you're drawing screenshot boundaries, consider that padding, and make choices that feel like they fit.

<div align="center">

<img src="../.gitbook/assets/Screen Shot 2022-04-01 at 7.43.47 PM.png" alt="⛔️ Bad: uneven padding around the element." width="375">

</div>

![✅ Good: even padding around the subject. Not pixel perfect, but basically even.](<../.gitbook/assets/Screen Shot 2022-04-01 at 7.44.33 PM.png>)

### Include "peeks" of nearby areas

If you're helping your users find something in the UI, give them reference points by including pieces of the surrounding terrain when drawing the boundaries of your screenshot.

Heuristic for this: take the natural boundary of your content, and expand it just enough that someone can figure out the local context. Make it easy for people to find what you're showing them.

![⛔️ Bad: no context.](<../.gitbook/assets/Screen Shot 2022-04-01 at 7.32.29 PM.png>)

![⛔️ Bad: too much context; it's not clear what this screenshot is meant to focus on.](<../.gitbook/assets/Screen Shot 2022-04-01 at 7.32.51 PM.png>)

![✅ Good: includes a peek of the content above and below, and includes a peek of the card boundary on the left.](<../.gitbook/assets/Screen Shot 2022-04-01 at 7.33.45 PM.png>)

![⛔️ Bad: no context.](<../.gitbook/assets/Screen Shot 2022-04-01 at 7.30.37 PM.png>)

![⛔️ Bad: the context below is meaningful, the context above is not meaningful.](<../.gitbook/assets/Screen Shot 2022-04-01 at 7.35.41 PM.png>)

![✅ Good, confusingly. :D It's good because we've given up on trying to decide where to draw the line on surrounding context, so we've gone with a crop that shows us the larger picture, and have used a red box to highlight the important stuff. Note the placement of the box, and how it doesn't interfere with any layout elements (lines/borders/shadows) already on the page.](<../.gitbook/assets/image (1).png>)

### Be inclusive

When filling in sample data, prefer sample data (names, email addresses, genders, countries) that reflect our global community.

Here's a name generator that works well: [https://www.name-generator.org.uk/quick/](https://www.name-generator.org.uk/quick/)

### Don't include internal references

Don't distract the user. It's less of a security thing, and more of a kindness thing.

If your screenshot includes data from our dev/staging/test instances, use Chrome's developer tools to edit that content _out_ before taking the screenshot. Use generic content (like "example.com") wherever possible.

