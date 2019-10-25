# Accessibility and JavaScript: An Unconventional Romance

Hey everyone! First of all, I am incredibly honored to be here.

Anyways, welcome to my talk: Accessibility and JavaScript: An Unconventional Romance.

## So who the heck am I?

- I'm a Front end focused JavaScript Developer. I used to be a UI developer who recently transitioned to being a JavaScript developer after getting my first React project. N ow I am primarily doing React and d3, creating accessible data visualizations.
- I'm an accessibility blogger. I started my blog, a11y with Lindsey as a way to help web developers who never learned about accessibility what it is and how to implement it. My blog just hit it's one year birthday a few weeks ago!

## Cutting to the chase

> Why do I care?

> We create products to help people. We don't create products to exclude people.

## Why do I care about accessibility?

It wasn't until I became an accessibility focused developer TM [quote unquote] that I really started thinking about how people either greatly benefited or were excluded from the products I used everyday. It wasn't until I started writing my blog that I realized how often cognitive disabilities are ignored. It's personal for me. I personally struggle with ADHD, and sometimes overstimulation causes panic attacks. This year, on April 1st, I went to Stack Overflow as I was googling a question to help me solve a bug, and I had to immediately close down the browser before I had a panic attack because it was exploding in animations and distractions. SO yeah it's pretty important to me.

As my career has evolved, I've learned more and more JavaScript and have been learning how to use it both ethically and inclusively. But I really want to talk a little bit of perceptions that JavaScript and Accessibility are foes.

## "The Great Divide"

Back in January, Chris Coyier wrong The Great Divide. The subtitle says "Two Front End Developers are sitting at a bar. They have nothing to talk about."

[change slides]

[READ IMAGE IN TWEET]

Does anyone remember the tweet storm that happened afterward? There was a LOT of arguing in the mentions, especially from the JavaScript developers who really really care about accessibility.

It was at this exact moment that it became clear to me that there are MANY folks in the JavaScript community who deeply care about accessibility. However, putting "accessibility" on the HTML and CSS side of things wasn't completely unfounded. I mean, I started out as a UI developer, and most of the accessibility experts I know focus more on the HTML and CSS side of things.

Some of the worst accessibility issues I've found have been on Progressive Web Apps and Single Page Apps. I've noticed that once I came to the JavaScript side of things, something I was skilled at (accessibility focused web development) was seen as this magical and mystical thing that only came from learning well written HTML. It's been fascinating for me as someone who was on the HTML/CSS side of things for a long time and is now on the JavaScript side of things.

This whole "conflict" that was probably unintentional about whether JavaScript developers care about accessibility quite honestly defined my whole mission about why I cared about accessibility.

[Change slides]

"JavaScript isn’t the enemy of accessibility. Instead, the lack of empathy is."

As you can see from this tweet, it got a decent amount of attention. It was a bold statement that I've certainly made before, just not on a public platform.

I'd probably rephrase it if I were to rewrite it now, after learning how white women use the word empathy.

However, let's dissect that for a second. When I tweeted this I got a lot of people who were like "Hmmm I don't know, I feel like ignorance is." Lack of knowledge is certainly a problem,but knowledge is something that can be remedied. It's willingly not caring about other people and not trusting their experience is valid...now that is the enemy.

JavaScript is not the opposite of accessibility; However, because people skip over HTML so quickly, and a lot of frameworks render **HTML** in the end, there tends to be a lot of absence of accessible HTML.

Gif alt: The character Anger from inside out, having their head lit on fire from an anger explosion.

This is a metaphor for how I felt when I was told I didn't have empathy for web developers because I wanted them to make their apps accessible. OK.

So the WebAIM million has certainly come up many times already, and for good reason because this is an accessibility conference, and this survey reminds us just how inaccessible the web is. But while writing out the rest of this talk I actually remembered that they had an update, and I wondered whether it got better.

## It didn't

Sadly 4 out of the 6 main categories got worse.

- Low contrast text increased from 85.3 percent to 86.1 percent
- Empty Links increased from 58.1 percent to 58.9 percent
- Missing form input labels increased from 52.8 percent to 53.2 percent
- and Empty buttons increased from 25% to 27%

And 98% of homepages had errors as compared to 97.8% in February.

Although, there was a **slight** decrease on total errors per page, from 59.7 to 59.1. And there is my shrug emoji because I am not super happy about this update but I guess there's one thing.

## But Lindsey, isn't this talk about JavaScript

## YES it is.

But at the end of the day, JavaScript frameworks render HTML.

And at the end of the day, JavaScript doesn't produce inaccessible HTML. Web Developers produce inaccessible HTML.

So the first thing to start with is to learn how your JavaScript framework renders HTML and make sure that rendered HTML is accessible.

## BUT

Accessible HTML isn't always enough, even if it gets you most of the way there.

We still have to worry about

- interactions
- focus management
- Using localStorage to store accessibility settings
- Progressive enhancement
- Integration testing for complex custom features (which we won't be talking about today but I did want to mention it).

Before we jump into JavaScript I want to say that I learned about JavaScript BECAUSE of accessibility, not in spite of it. I had to create a fully accessible language pop up menu that had 27 languages inside it. And I didn't really approach it from a "JavaScripty" mindset. All I did was think, "How do I make this not annoying at all?"

## But now let's get to the JavaScript

First a few notes:
I'll be using React in some of these samples, but I won't be going in depth for the sake of time. Here's the TL;DR:

- JSX is a syntax extension to JavaScript that looks VERY similar to HTML. Think of it as a template.
- JSX that doesn't look like HTML is likely a component
- Components may have props which are pieces of data.
- Components might have state, which is data that can change within the component

## Modals

Inaccessible modals suck. Let's just get that out of the way now. Whenever something pops up and you CAN'T EVEN ACCESS THE CONTENT? What gives?

It entails properly shifting focus to the first focusable element when the modal pops up (meaning there should be at least one focusable element).

"Focus trapping" which means that when you reach the last focusable element within the modal, it goes back to the first focusable element of the modal.

Upon Close, the modal should return to the item it was last focused on before the modal opened.

So let's go through this code a little bit.

All of this was done with a React Modal package that is part of the reactjs repository. All I needed to do was include the Modal Component, give it a few props and it works accessibly.

## Overall Focus Management

We want to ensure that we are not focusing on elements that are not visible. The best example I can think of this is hamburger menus which I'll be showing you in the next example. A lot of times people will be tabbing through the focusable elements without actually knowing where they are because the links positioned off screen.

Making sure to properly navigate keyboard users where they should go.

- We have a button that opens the menu
- Then we have a nav in the markup
- then I just added a test button so we had something focusable for testing purposes

So when we go through this you see that we have multiple tabs before we get to that button. Why? Because we are

            </ul> -->

WITH GREAT POWER, COMES GREAT RESPONSIBILITY.
