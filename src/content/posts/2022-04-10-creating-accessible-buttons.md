---
template: blog-post
title: Creating Accessible Buttons
slug: /creating-accessible-buttons
date: 2022-04-10 19:50
description: creating accessible buttons
---
# Creating Accessible Buttons

On almost every web page there are buttons. It is hard not to encounter one on a daily basis as a web developer. Unfortunately, it is easy to produce an inaccessible button if one is unaware of what needs to be implemented. Buttons, like anything else we create on the web, should follow WCAG guidelines and consider best usability practices.  

We will learn about button functionality and styling by creating one from scratch.

This button we will create will be a "Get Started" button, which will trigger a popup modal and ask the user for their information in a form. A button like this is on [Medium](https://medium.com/)'s home page. Let's think about how to start implementing it. 

# Semantic HTML

The first thing to consider is how to represent a button in the markup. There is the button `<button>` element, but there is also the link/anchor `<a>` element. Choosing which element to use can sometimes be confusing. Delving into each element's native functionality might clear up some of the confusion.

Links generally navigate the user to some other place on the web. That means either somewhere else on current page, or to another web site. The anchor element has a `href` attribute that accepts a URL, unlike the button element. 

Buttons generally trigger something to happen on the page, like a popup modal, navigation menu, or some kind of content shift. Buttons can also natively submit or reset form content. Here are some important aspects of each to consider:

Links:

* focusable by default with `href` attribute
* has `:link`, `:visited`, `:focus`, `:hover`, `:active` states
* the Enter key registers as a click

Buttons:

* focusable by default
* has `:focus`, `:hover`, `:active`, `:disabled` states
* the Space key registers as a click

The importance in knowing these elements' native functionality is that if you want to create a button or a link that does not use semantic HTML (it is a `<div>` or a `<span>`, for example), then it is the developer's job to recreate this functionality with CSS, JavaScript, and/or aria labels. 

So what HTML element will we choose for our button? It can be tricky when we think of how to implement the modal. One way to implement a popup modal without the use of JavaScript is to link to a specific tag, say, `#modal`. Then, when the button is pressed, we style the `#modal:target` CSS property. Another way is to use the button element and use JavaScript to add/remove a class that shows the modal. 

At this point, it is really up to the developer. As long as the button is usable and accessible, it can be created as a link, button, div, span, etc. It is often easier to use semantic HTML elements since they offer native functionality that we don't have to implement ourselves. 

In our case, I will make our button an actual button HTML element.

```html

```

Without any styling, this button will show up differently depending on the browser.

Firefox button:
[![Image from Gyazo](https://i.gyazo.com/380c4b1dbbfab9fa5fe9f0fdf789199a.jpg)](https://gyazo.com/380c4b1dbbfab9fa5fe9f0fdf789199a)
Firefox button on hover:
[![Image from Gyazo](https://i.gyazo.com/78ef49afe070d211ae635a571e107c2a.jpg)](https://gyazo.com/78ef49afe070d211ae635a571e107c2a)
Firefox button on focus:
[![Image from Gyazo](https://i.gyazo.com/1beacf56e60805197479c0b3ac257bbb.jpg)](https://gyazo.com/1beacf56e60805197479c0b3ac257bbb)

<hr>

Chrome button:
[![Image from Gyazo](https://i.gyazo.com/857ec5b5fa2dc1f37f2ab0ff191b4490.jpg)](https://gyazo.com/857ec5b5fa2dc1f37f2ab0ff191b4490)
Chrome button on hover:
[![Image from Gyazo](https://i.gyazo.com/27fb779dff1fe1a50556bb51177767da.jpg)](https://gyazo.com/27fb779dff1fe1a50556bb51177767da)
Chrome button on focus:
[![Image from Gyazo](https://i.gyazo.com/be9da9ae555cd1d80b71377a15437d13.jpg)](https://gyazo.com/be9da9ae555cd1d80b71377a15437d13)

Since these buttons show up so differently depending on the browser, it is usually necessary to reset these styles and add our own. This makes it so the button will look the same across all browsers.

To reset all button styles, we can apply these styles:

```css

```

Now our button looks just like any other text on the page, giving no indication that it is a button other than the cursor change. It looks this way on any browser.
[![Image from Gyazo](https://i.gyazo.com/dfcc1e5b877624b4ad5b8b3bd49e9d32.png)](https://gyazo.com/dfcc1e5b877624b4ad5b8b3bd49e9d32)

Now we can recreate our button with the styling we want for our page. A lot of it is under the developer's discretion, but there are some important points for accessibility that should be considered.

## Color

Stephanie Eckles talks about proper button color contrast in her [CSS Button Styling Guide](https://moderncss.dev/css-button-styling-guide/?utm_campaign=top10&utm_medium=twitter). There are two pairs of colors to think about: the button background color to the background color it is displayed against, and the button text color to the button background color. Each has a color contrast ratio that should be adhered to.

* **3:1** --> button background color to background color
* **4:5:1** --> button text to button background color

Figuring out the contrast ratio of color combinations is not something you're supposed to calculate yourself. There are several apps that can do it for you. Here are some of them:

* [Button Buddy](https://buttonbuddy.dev/): specifically a button contrast generator!
* [Adobe Color Contrast Checker](https://color.adobe.com/create/color-contrast-analyzer): displays the contrast ratio for any color combination
* [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/): another reliable contrast checker
* [WAVE (web accessibility evaluation tool)](https://wave.webaim.org/extension/): a browser extension that checks for accessible contrast ratios on the whole web page

For our example, our website background will be an off-white color. Our button will be shades of green. I will use button buddy here to generate colors with high enough contrast.
[![Image from Gyazo](https://i.gyazo.com/6dfbad1559a12fdc341386a8404b92f9.png)](https://gyazo.com/6dfbad1559a12fdc341386a8404b92f9)

All contrast checks are passing! Now we can apply these colors to our button, knowing well that there is proper contrast between every state. By pressing the "copy to clipboard" button, we copy the color values we made attached to CSS custom properties that we can include in our project with ease. 

```css

```

[![Image from Gyazo](https://i.gyazo.com/f725ccedc4879ee32fc03a1e1e6cf88e.gif)](https://gyazo.com/f725ccedc4879ee32fc03a1e1e6cf88e)

## :hover

Since our colors are in order, now we can focus (...get it?) on the different button states. We've started to implement the `:hover` state since we have colors for it, but we might want to add a transition to make the color change less jarring. This can be done with one line of code.

```css

```

Putting this CSS declaration here will apply the transition to and from all button states!
[![Image from Gyazo](https://i.gyazo.com/78f5be119bc76aa4527208733c2c3b89.gif)](https://gyazo.com/78f5be119bc76aa4527208733c2c3b89)

## :focus

For the button's `:focus` state, the browser adds an outline to the element. The last thing the developer should do is remove the outline and call it a day. We want to make sure that the focus state is clear and distinguishable for keyboard users. It does not have to be done with an outline - it can be done in other ways like underline, box-shadow, or border. In our case I'm going to use the box-shadow property but basically create an outline. The reason I'm doing this is because the animation will apply to box-shadow but not outline. Since a button can be in `:hover` and `:focus` state at the same time, I will make the outline color a darker green (almost black).

```css

```

[![Image from Gyazo](https://i.gyazo.com/a9596e09d62295899b05c88def6b2682.gif)](https://gyazo.com/a9596e09d62295899b05c88def6b2682)

## :active

The button's `:active` states comes into play as:

* a touchscreen user touches the button
* a mouse user clicks the button
* a keyboard user pressed spacebar on a focused button

It is important to have a style on this pseudo class, but it doesn't have to be terribly different from other button states. In our instance, it is perfectly fine for it to have the same styles as our hover state. We can simply add the pseudo-class to the `.button:hover` selector.

```css

```

## :disabled

The `:disabled` state of a button