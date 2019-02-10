project_path: /web/tools/_project.yaml book_path: /web/tools/_book.yaml

{# wf_updated_on: 2018-09-20 #} {# wf_published_on: 2018-09-05 #} {# wf_blink_components: Platform>DevTools #}

# DevTools For Beginners: Get Started with CSS {: .page-title }

{% include "web/_shared/contributors/katjackson.html" %}

In this tutorial, you learn how to use CSS to style a web page. You also learn how to use Chrome DevTools to experiment with CSS changes.

This is the second tutorial in a series of tutorials that teaches you the basics of web development and Chrome DevTools. You gain hands-on experience by actually building your own website. You don't have to complete the first tutorial before doing this one. You can start here. [Set up your code](#setup) shows you how to get set up.

Note: This tutorial is designed for absolute beginners and focuses on both the **fundamentals of web development** and the basics of using DevTools to experiment with CSS. If you want a tutorial that only focuses on DevTools, see [Get Started with Viewing and Changing CSS](/web/tools/chrome-devtools/css/).

Currently your site looks like this:

<figure>
  <img src="imgs/css/intro1.png"
       alt="What your site currently looks like."/>
  <figcaption>
    <b>Figure 1</b>. What your site currently looks like
  </figcaption>
</figure>

After completing the tutorial, it will look like this:

<figure>
  <img src="imgs/css/intro2.png"
       alt="What your site will look like at the end of the tutorial."/>
  <figcaption>
    <b>Figure 2</b>. What your site will look like at the end of the tutorial
  </figcaption>
</figure>

## Goals {: #goals }

By the end of this tutorial, you will understand:

* How to use CSS to style a web page.
* How to use Chrome DevTools to experiment with CSS.
* The difference between CSS and CSS frameworks.

You'll also have a real website!

## Prerequisites {: #prerequisites }

Before attempting this tutorial, complete the following prerequisites:

* Complete [Get Started with HTML and the DOM](/web/tools/chrome-devtools/beginners/html) or make sure that you have an understanding of HTML and the DOM similar to what's taught in that tutorial.
* Download the [Google Chrome](https://www.google.com/chrome/){: .external } web browser. This tutorial uses a set of web development tools, called Chrome DevTools, that are built into Google Chrome. 

## Set up your code {: #setup }

In order to start creating your site, you need to set up your code:

1. **If you have already completed the first tutorial in this series, skip this section! Continue using your code from the last tutorial, [Get Started with HTML and the DOM](/web/tools/chrome-devtools/beginners/html).**
2. Open the <a class="external gc-analytics-event" target="_blank" rel="noopener"
data-category="CTA" data-label="/web/tools/chrome-devtools/beginners/css"
href="https://glitch.com/edit/#!/dfb2?path=index.html">source code</a>. This tab of your browser will be called the **editing tab**.
    
    <figure> 
    
    ![The editing tab.](imgs/css/setup1.png) <figcaption> **Figure 3**. The editing tab </figcaption> </figure>
3. Click **dfb2**. A menu pops up.
    
    <figure> 
    
    ![The Project Options menu.](imgs/css/setup2.png) <figcaption> **Figure 4**. The Project Options menu </figcaption> </figure>
4. Click **Remix This**. Glitch creates a copy of the project that you can edit. Note that Glitch generates a random name for the new project.

5. Click **Show Live**. Another tab opens with a live view of your site. This tab of your browser will be called the **live tab**.
    
    <figure> 
    
    ![The live tab.](imgs/css/setup3.png) <figcaption> **Figure 5**. The live tab </figcaption> </figure>

## Understand CSS {: #add }

**CSS** is a computer language that determines the layout and styling of web pages. For example, here is a paragraph with a border:

<p style="border:1px dashed red; padding:5px">This has been styled with CSS.</p>

Here is the HTML and CSS code used to create that paragraph:

    <p style="border: 1px dashed red; padding: 5px;">
      This has been styled with CSS.
    </p> 
    

`style="border: 1px dashed red; padding: 5px;"` probably looks new to you. The rest should look familiar. If not, complete [Get Started with HTML and the DOM](/web/tools/chrome-devtools/beginners/html) before attempting this tutorial.

## Add inline styles {: #inline }

Use **inline styles** when you want to apply styles to a single element. Try it now:

1. Go back to the editing tab and open `index.html`.
    
    <figure> 
    
    ![index.html.](imgs/css/inline1.png) <figcaption> **Figure 6**. `index.html` </figcaption> </figure>
2. Add `style="background-color: aliceblue;"` to your `<nav>`. In the code block below, the bold line of code is the one you need to change. The rest is just there so you can be sure that you're putting the new code in the right place.
    
    <pre class="prettyprint lang-html">{% htmlescape %}...

...
{% endhtmlescape %}</pre>
3. Go back to the **live tab**.

4. Click **Contact** to go back to the contact page. The font of **Home** and **Contact** has changed.
    
    <figure> 
    
    ![The font of the Home and Contact links has changed.](imgs/css/internal2.png) <figcaption> **Figure 9**. The font of the Home and Contact links has changed </figcaption> </figure>

### Understand internal stylesheets {: #internal-overview }

Internal stylesheets apply styles using **selectors**. Selectors are patterns that may apply to one or more HTML elements. For example, in the previous code:

    <style>
      li a {
        font-family: 'Courier New', Courier, serif;
      }
    </style>
    

`li a` is a selector that translates to "any `<li>` that contains an `<a>`". The browser changes the font of the **Home** and **Contact** links because they match this pattern.

    <li><a href="/">Home</a></li>
    <li><a href="/contact.html">Contact</a></li>
    

`font-family: 'Courier New', Courier, serif` is a **declaration**. A declaration is made of two parts: a **property** and a **value**. `font-family` is the property, and `'Courier New', Courier, serif` is the value of that property. The property describes a general way that you can change the element's style, and the value says how exactly it should change. For example, `font-family: 'Courier New', Courier, serif` gives the browser this instruction: "Set the font of elements that match the pattern `li a` to `'Courier New'`. If that font isn't available, use `Courier`. If that isn't available, use `serif`."

### Add multiple selectors to a ruleset {: #multiple }

A block of CSS code like what you see below is called a **ruleset**.

    li a {
      font-family: 'Courier New', Courier, monospace;
    }
    

Use commas to add multiple selectors to a ruleset. Try it now:

1. In the **editor tab**, open `contact.html`.
2. After `li a` type `, h1`.
    
    <pre class="prettyprint lang-html">{% htmlescape %}...
<style>
  li a{% endhtmlescape %}<strong>{% htmlescape %}, h1{% endhtmlescape %}</strong>{% htmlescape %} {
    font-family: 'Courier New', Courier, Serif;
  }
</style>{% endhtmlescape %}&lt;/strong>{% htmlescape %}
...
{% endhtmlescape %}</pre>
    This tells the browser to style `<h1>` elements the same way that it styles elements that match the pattern `li a`.

3. Go to the **live tab**.

4. Click the **Contact** link to go back to the contact page. Now, **Contact Me!** has the same font as the navigation links.
    
    <figure> 
    
    ![The text 'Contact Me!' now has the same font as the Home and Contact links.](imgs/css/multiple1.png) <figcaption> **Figure 10**. The text "Contact Me!" now has the same font as the Home and Contact links </figcaption> </figure>

## Experiment with DevTools {: #experiment }

As you continue your journey to master web development, you'll find that CSS can be tricky. You'll write some CSS and expect it to display one way, but the browser does something completely different. Chrome DevTools makes it easy to experiment with changes and immediately see how those changes affect the page.

### Add a declaration to an existing rulest in DevTools {: #add }

When you want to iterate on the style of an existing element, add a declaration to an existing ruleset. Try it now:

1. Right-click the **Home** link and select **Inspect**.
    
    <figure> 
    
    ![Inspecting the Home link.](imgs/css/add1.png) <figcaption> **Figure 11**. Inspecting the Home link </figcaption> </figure> 
    DevTools opens up alongside your page. The code that represents the Home link, `<a href="/">Home</a>` is highlighted blue in the DOM Tree. This should be familiar from [Get Started with HTML and the DOM](html). In the **Styles** tab below the DOM Tree you can see the `font-family: 'Courier New', Courier, serif` declaration that you added to `contact.html` earlier.
    
    <figure> 
    
    ![The Styles tab is below the DOM Tree.](imgs/css/add2.png) <figcaption> **Figure 12**. The Styles tab is below the DOM Tree </figcaption> </figure> 
    If your DevTools window is wide, the Styles tab is to the right of the DOM Tree.
    
    <figure> 
    
    ![The Styles tab is to the right of the DOM Tree.](imgs/css/add3.png) <figcaption> **Figure 13**. The Styles tab is to the right of the DOM Tree </figcaption> </figure>
2. Click the whitespace below `font-family: 'Courier New', Courier, Serif` to add a new declaration.
    
    <figure> 
    
    ![Adding a new declaration.](imgs/css/add4.png) <figcaption> **Figure 14**. Adding a new declaration </figcaption> </figure>
3. Type `color` and then press <kbd>Enter</kbd>. The autocomplete UI suggests options as you type.
    
    <figure> 
    
    ![Typing 'color'.](imgs/css/add5.png) <figcaption> **Figure 15**. Typing `color` </figcaption> </figure>
4. Type `magenta` and then press <kbd>Enter</kbd> again. All of the text on the contact page is now magenta.
    
    <figure> 
    
    ![Typing 'magenta'.](imgs/css/add6.png) <figcaption> **Figure 16**. Typing `magenta` </figcaption> </figure>

### Edit a declaration in DevTools {: #edit }

You can also edit existing declarations in DevTools. Try it now:

1. Click the magenta square next to `magenta`. A color picker pops up.
    
    <figure> 
    
    ![The Color Picker.](imgs/css/edit1.png) <figcaption> **Figure 16**. The Color Picker </figcaption> </figure>
2. Use the color picker to change the font text to a color that you like.
    
    <figure> 
    
    ![Changing the font color to purple with the Color Picker.](imgs/css/edit2.png) <figcaption> **Figure 17**. Changing the font color to purple with the Color Picker </figcaption> </figure>

### Add a new ruleset in DevTools {: #rule }

You can also add new rulesets in DevTools. Try it now:

1. Click **New Style Rule** ![New Style Rule](/web/tools/chrome-devtools/images/shared/new-style-rule.png){: .inline-icon }, which is next to **.cls**. An empty ruleset appears with `a` as the selector.
    
    <figure> 
    
    ![Adding a new rule.](imgs/css/rule1.png) <figcaption> **Figure 18**. Adding a new rule </figcaption> </figure>
2. Replace `a` with `a:hover`.
    
    <figure> 
    
    ![Replacing 'a' with 'a:hover'.](imgs/css/rule2.png) <figcaption> **Figure 19**. Replacing `a` with `a:hover` </figcaption> </figure> 
    `:hover` is a **pseudo-class**. Use pseudo-classes to style elements when they enter special states. For example, the `a:hover` style only takes effect when you're hovering over an `<a>` element.

3. Click between the brackets to add a new declaration.

4. Type `background-color` for the declaration name and then press <kbd>Enter</kbd>.
    
    <figure> 
    
    ![Typing 'background-color'.](imgs/css/rule3.png) <figcaption> **Figure 20**. Typing `background-color` </figcaption> </figure>
5. Type `green` for the declaration value and then press <kbd>Enter</kbd>.
    
    <figure> 
    
    ![Typing 'green'.](imgs/css/rule4.png) <figcaption> **Figure 21**. Typing `green` </figcaption> </figure>
6. Hover your mouse over the **Home** link. The background of the link turns green.
    
    <figure> 
    
    ![Hovering over the Home link to reveal its green background.](imgs/css/rule5.png) <figcaption> **Figure 22**. Hovering over the Home link to reveal its green background </figcaption> </figure>

## Re-use styles across pages with external stylesheets {: #external}

Earlier you added this internal stylesheet to `contact.html`:

    <style>
      li a, h1 {
        font-family: 'Courier New', Courier, monospace;
      }
    </style>
    

What if you wanted to style `index.html` the same way? What if you had a *thousand* pages and you wanted to apply these styles to all of them? You'd have to copy and paste this internal stylesheet into every single web page on your site. **External stylesheets** allow you to write your CSS once yet apply it to multiple pages. Try it now:

1. First, reload the live tab to remove the changes that you made in DevTools.
    
    <figure> 
    
    ![After reloading the page the changes that were made in DevTools are gone.](imgs/css/external1.png) <figcaption> **Figure 23**. After reloading the page the changes that were made in DevTools are gone </figcaption> </figure>
2. Go back to the **editor tab** and open `contact.html`.
    
    <figure> 
    
    ![contact.html](imgs/css/external2.png) <figcaption> **Figure 24**. contact.html </figcaption> </figure>
3. Delete everything between `<style>` and `</style>`, including `<style>` and `</style>`.
    
    <figure> 
    
    ![The style tag has been removed.](imgs/css/external3.png) <figcaption> **Figure 25**. The style tag has been removed </figcaption> </figure>
4. Go to `index.html` and remove `style="background-color: aliceblue;"` from the `<nav>` tag.
    
    You have now removed all of the CSS that you previously added to your site.
    
    <figure> 
    
    ![The inline style has been removed from the nav element.](imgs/css/external4.png) <figcaption> **Figure 26**. The inline style has been removed from the nav element </figcaption> </figure>
5. Click **New File**.
    
    <figure> 
    
    ![The new file dialog.](imgs/css/external5.png) <figcaption> **Figure 27**. The new file dialog </figcaption> </figure>
6. Replace `cool-file.js` with `style.css` and then click **Add File**.
    
    <figure> 
    
    ![Typing 'style.css'.](imgs/css/external6.png) <figcaption> **Figure 28**. Typing `style.css` </figcaption> </figure>
7. Paste this code into `style.css`:
    
    <pre class="prettyprint lang-css">li a, h1 {
  font-family: 'Courier New', Courier, Serif;
}
a:hover {
  background-color: green;
}
nav {
  background-color: aliceblue;
}
</pre>
    <figure> 
    
    ![Adding code to style.css](imgs/css/external7.png) <figcaption> **Figure 29**. Adding code to `style.css` </figcaption> </figure> 
    At this point, you have created an external stylesheet, but your HTML doesn't know that it exists, yet.

8. Open `index.html`.

9. Add `<link rel="stylesheet" href="style.css">` to your HTML.
    
    <pre class="prettyprint lang-html">{% htmlescape %}...

...
{% endhtmlescape %}</pre>
    <figure> 
    
    ![Linking to style.css.](imgs/css/external8.png) <figcaption> **Figure 30**. Linking to `style.css` </figcaption> </figure>
10. Go to `contact.html` and add the link there, too.
    
    <figure> 
    
    ![Linking to style.css in contact.html.](imgs/css/external9.png) <figcaption> **Figure 31**. Linking to `style.css` in `contact.html` </figcaption> </figure>
11. Go to the **live tab**. The home page now has the same font from the last section and a blue navigation section.
    
    <figure> 
    
    ![The home page.](imgs/css/external10.png) <figcaption> **Figure 32**. The home page </figcaption> </figure>
12. Click the **Contact** link to go to the contact page. The contact page has the same formatting as the home page.
    
    <figure> 
    
    ![The contact page](imgs/css/external11.png) <figcaption> **Figure 33**. The contact page </figcaption> </figure>

## Use a CSS framework {: #framework }

**CSS frameworks** are collections of styles built by other developers that make it easier to create attractive web sites. Instead of defining styles yourself, a framework gives you a collection of styles that you can use on your page elements.

1. Copy the following code: `<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.1/css/bootstrap.min.css">` 
2. Go to the editing tab and paste the code into `contact.html`.
    
    <figure> 
    
    ![Linking to the framework in contact.html.](imgs/css/framework1.png) <figcaption> **Figure 34**. Linking to the framework in contact.html </figcaption> </figure>
3. Paste the code into `index.html`, as well.
    
    <figure> 
    
    ![Linking to the framework in index.html](imgs/css/framework2.png) <figcaption> **Figure 35**. Linking to the framework in index.html </figcaption> </figure>
4. Go back to the live tab to view your changes. While the background color of the `<nav>` and the font of the `li a` elements are the same, the font of the other elements has changed.
    
    <figure> 
    
    ![Some of the font on the home page has changed because of the framework.](imgs/css/framework3.png) <figcaption> **Figure 36**. Some of the font on the home page has changed because of the framework </figcaption> </figure>

### Use a class {: #class }

In the last section, you added Bootstrap to your web pages, which changed the fonts of some of the elements on your site. CSS frameworks can help you make major changes to your page with very little code. Try it now by changing your header:

1. Copy this code: `class="jumbotron jumbotron-fluid"`
2. Add this code to your `<header>` tag in `index.html`.
    
    <figure> 
    
    ![Adding the jumbotron class in index.html.](imgs/css/jumbotron1.png) <figcaption> **Figure 37**. Adding classes in index.html </figcaption> </figure>
3. Add the code to your `<header>` tag in `contact.html`, too.
    
    <figure> 
    
    ![Adding the jumbotron class in contact.html.](imgs/css/jumbotron2.png) <figcaption> **Figure 38**. Adding classes in contact.html </figcaption> </figure>
4. View your changes in the live tab. There's a big, grey box around your header now.
    
    <figure> 
    
    ![The header now has a big, grey box around it.](imgs/css/jumbotron3.png) <figcaption> **Figure 39**. The header now has a big, grey box around it </figcaption> </figure>

### Understand classes {: #classes-overview }

Classes let you assign collections of styles to arbitrary elements. For example, setting the `class` attribute of the `<header>` tags to `jumbotron` applied the following styles to them:

    .jumbotron {
      padding: 2rem 1rem;
      margin-bottom: 2rem;
      background-color: #e9ecef;
      border-radius: .3rem;
    }
    

One advantage of classes is that they let you apply styles to whatever elements you want. For example, suppose you want to set the background color of *some* `<p>` elements to purple, but not *all* of them. You could define the style in a class:

    .custom-background {
      background-color: purple;
    }
    

And then apply the class to only the `<p>` elements that you want to style:

    <p>This won't be purple.</p>
    <p class="custom-background">This will be purple.</p>
    <p>This won't be purple.</p>
    <p class="custom-background">This will be purple.</p>
    

### Align elements {: #align }

Bootstrap also provides classes for aligning elements. Try it now:

1. Go back to the editor tab and open `index.html`.
2. Add `class="container-fluid"` to your `<body>` tag.
    
    <figure> 
    
    ![Adding the 'container-fluid' class.](imgs/css/align1.png) <figcaption> **Figure 40**. Adding the `container-fluid` class </figcaption> </figure>
3. Wrap your `<nav>` and `<main>` elements in `<div class="row">`. Make sure to put `</div>` after `</main>` in order to properly close the new tag.
    
    <figure> 
    
    ![Adding a row.](imgs/css/align2.png) <figcaption> **Figure 41**. Adding a row </figcaption> </figure>
4. Add `class="col-3"` to your `<nav>` tag and `class="col-9"` to your `<main>` tag.
    
    <figure> 
    
    ![Adding the 'col-3' and 'col-9' classes.](imgs/css/align3.png) <figcaption> **Figure 42**. Adding the `col-3` and `col-9` classes </figcaption> </figure>
5. View your changes in the live tab.
    
    <figure> 
    
    ![The nav content is now to the left of the main content.](imgs/css/align4.png) <figcaption> **Figure 43**. The nav content is now to the left of the main content </figcaption> </figure>

## Next steps {: #next-steps }

Congratulations! You're done!

* The best way to get better at web development is to build more sites. Don't worry about breaking stuff. Just have fun and learn as much as you can along the way.
* Check out [Introduction to CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS) to learn lots more about styling web pages.
* Work through our [Get Started with Viewing and Changing CSS](/web/tools/chrome-devtools/css/) tutorial to learn more about how you can use DevTools to experiment with a page's CSS.

## Feedback {: #feedback }

{% include "web/_shared/helpful.html" %}