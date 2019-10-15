# Accessibility and JavaScript: An Unconventional Romance

Hey everyone! First of all, I am incredibly honored to be here.

Anyways, welcome to my talk: Accessibility and JavaScript: An Unconventional Romance.

## So who the heck am I?

\*Points\* That's a picture of me :D

- I'm a Front End Developer. I actually just hit my 5 year mark officially employed as a developer. I used to work in Drupal for the longest time, but now I am primarily doing React and d3.
- I'm an accessibility blogger. I started my blog, a11y with Lindsey as a way to take the jargon out of accessibility and encourage web developers to make their internet everybody's internet. I've been writing for over 7 months now and it's been quite a journey to say the least.
- I'm also a craft beer drinker! If you ever hit up the DC area I have plenty of recommendations!

## Cutting to the chase

> Why does accessibility matter to your org?

## Your org provides a product or service to people.

That's it. I know there's a lot of business and legal reasons that accessibility matters. But when it comes down to it, you are serving **people**

## Why do I care about accessibility?

It wasn't until I became an accessibility expert TM [quote unquote] that I really started thinking about how people with disabilities either greatly benefited or were excluded from the products I used everyday. I could go on more about this, but it's a major theme in my talk.

## "The Great Divide"

Does anyone remember this article? [checks to see who has]

### if nobody raises their hands

Oh wow! Interesting. Well, to summarize, Chris Coyier wrote it about how there's a large divide between what a "front end developer" is.

[change slides]

[READ IMAGE IN TWEET]

### Start here

Does anyone remember the tweet storm that happened afterward?

It was at this exact moment that it became clear to me that there are MANY thought leaders in the JavaScript community who deeply care about accessibility. However, putting "accessibility" on the HTML and CSS side of things wasn't completely unfounded. Some of the worst accessibility issues I've found have been on Progressive Web Apps and Single Page Apps. I've noticed that once I came to the JavaScript side of things, something I found second nature (accessibility) was seen as this magical and mystical thing that only came from learning well written HTML. It's been fascinating for me as someone who was on the HTML/CSS side of things for a long time and is now on the JavaScript side of things.

This whole "conflict" that was probably unintentional about whether JavaScript developers care about accessibility quite honestly defined my whole mission about why I cared about accessibility.

[Change slides]

"JavaScript isn’t the enemy of accessibility. Instead, the lack of empathy is."

As you can see from this tweet, it got a decent amount of attention. It was a bold statement that I've certainly made before, just not on a public platform.

Let's dissect that for a second. When I tweeted this I got a lot of people who were like "Hmmm I don't know, I feel like ignorance is." Lack of knowledge is certainly a problem,but knowledge is something that can be remedied. It's willingly not caring about other people that is the enemy.

The reason I point this out is because I believe Chris's article got wildly misunderstood. JavaScript is not the opposite of accessibility; However, because people skip over HTML so quickly, and a lot of frameworks render **HTML** in the end, there tends to be a lot of absence of accessible HTML.

I saw this quote and I think it perfectly illustrates my point.

<!-- The reason that accessibility is on the HTML/CSS side of things is because of how much HTML and CSS gets minimized by JavaScript developers, while simultaneously being told it's incredibly difficult. -->

## How privilege defines performance

Something I've come across many times is people not even **considering** how something is going to work for someone else. I watched this talk by Tatiana Mac and it moved me to tears. But something she talked about is WebAIMs accessibility analysis of the top million websites. The results are depressingly bad.

59,653,607 distinct accessibility errors were detected across the 1 million home pages—an average of 59.6 errors per page.
97.8% of home pages had detectable WCAG 2 failures!

85% for low contrast pages, 52% for missing form labels.

Do you see these numbers? They are **Abysmal**. Why do we think that is?

We center the able-bodied and neurotypical experience. We test it for ourselves. We don't consider how it affects everyone else.

## How to improve Accessibility?

TL;DR don't have any of the errors that occurred in the audit since they are low hanging fruit.

### First IMPROVE YOUR HTML and CSS

If at the end of the day, React renders HTML, let's improve our HTML and CSS stuff. Ensure all forms have labels. This can be a visually hidden label, but we need to have a label or an aria-label.

Then we need to ensure that we have alt text, even if it's empty to imply that it's decorative. For example, if you are on a team member's bio page, their photo isn't really necessary for the context of the page - it's decorative.

Don't have an empty link or a button. There needs to be some form of text for a screenreader to understand, even if it's a visually hidden span that just tells you what that button or link is.

Have accessible contrast - we want to account for glare, colorblindness, strained vision, older eyes. etc. Please test your gray on gray type. (btw I did for yours and it passed!)

Have clear focus styling! A lot of times this is just bu **not** removing the default. But sometimes if the default doesn't have enough distinction with the color palette of the site, you can change the outline to be "on brand"

## Your Homework

Read. The. Docs. I was actually very wowed to see how well documented the React docs were for accessibility. I highly suggest you read them.

## JavaScript

Most errors can be solved with simple HTML fixes. However, what if I told you that so many Accessibility issues **required** JavaScript?

## Modals

Accessible modals seem to be something that trip people up. But what does it entail?

It entails properly shifting focus to the first focusable element when the modal pops up (meaning there should be at least one focusable element).

"Focus trapping" which means that when you reach the last focusable element within the modal, it goes back to the first focusable element of the modal.

Upon Close, the modal should return to the item it was last focused on before the modal opened.

## Accordions

Using semantic buttons so click events have built in keyboard handling

Ensuring to keep all the sections expanded (Visually and to a screenreader with aria-expanded) until JavaScript loads.

Then add ARIA states (aria-expanded and aria-hidden) and style toggling.

My latest blog post went deep into the code of how to do accordions in JavaScript. I even do some screen reader demos.

## Overall Focus Management

So this for me is less about screen reader users and more about keyboard users. We want to ensure that we are not focusing on elements that are not seen. The best example I can think of this is hamburger menus. A lot of times people will be tabbing through the focusable elements without actually knowing where they are because the links are like left: -100%; and then when it's toggled open it's

Making sure to properly navigate keyboard users where they should go. A good exercise is to think about where someone's mouse may normally go if they were i.e. In Spotify, selecting a playlist should shift the focus to that playlist instead of continuing down the other tabs. Because ideally you want to check it out right?

<!-- Go to codes -->

WITH GREAT POWER, COMES GREAT RESPONSIBILITY.
