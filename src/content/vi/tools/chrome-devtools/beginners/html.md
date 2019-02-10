project_path: /web/tools/_project.yaml book_path: /web/tools/_book.yaml

{# wf_updated_on: 2018-12-19 #} {# wf_published_on: 2018-08-13 #} {# wf_blink_components: Platform>DevTools #}

# DevTools for Beginners: Get Started with HTML and the DOM {: .page-title }

{% include "web/_shared/contributors/katjackson.html" %}

This is the first in a series of tutorials that teach you the basics of web development. You will also learn about a set of web developer tools called Chrome DevTools that can increase your productivity.

In this particular tutorial, you learn about HTML and the DOM. HTML is one of the core technologies of web development. It is the language that controls the structure and content of webpages. The DOM is also related to the structure and content of webpages, but you'll learn more about that later.

## Goals {: #goals }

You are going to learn web development by actually building your own website. By the time you complete all of the tutorials in the *DevTools for Beginners* series, your finished site will look like **Figure 1**.

<figure>
  <img src="imgs/finished.png"
       alt="The finished site."/>
  <figcaption>
    <b>Figure 1</b>. The finished site
  </figcaption>
</figure>

By the end of this tutorial, you will understand:

* How HTML and the DOM create the content that you see on webpages.
* How Chrome DevTools can help you experiment with HTML and DOM changes.
* The difference between HTML and the DOM.

You'll also have a real website! You can use this site to host your resume or blog.

## Prerequisites {: #prerequisites }

Before attempting this tutorial, complete the following prerequisites:

* If you're unfamiliar with HTML, read [Getting Started with HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Getting_started){: .external }.
* Download the [Google Chrome](https://www.google.com/chrome/){: .external } web browser. This tutorial uses a set of web development tools, called Chrome DevTools, that are built into Google Chrome.

## Set up your code {: #setup}

You're going to build your site in an online code editor called Glitch.

1. Open the <a class="external gc-analytics-event" target="_blank" rel="noopener"
data-category="CTA" data-label="/web/tools/chrome-devtools/beginners/html"
href="https://glitch.com/edit/#!/dfb1?path=index.html">source code</a>. This tab will be called the **editor tab** throughout this tutorial.
    
    <figure> 
    
    ![The editor tab.](imgs/setup1.png) <figcaption> **Figure 2**. The editor tab </figcaption> </figure>
2. Click **dfb1**. The Project Options menu opens in the top-left corner.
    
    <figure> 
    
    ![The Project Options menu.](imgs/setup2.png) <figcaption> **Figure 3**. The Project Options menu </figcaption> </figure>
3. Click **Remix This**. Glitch creates a copy of the project that you can edit and randomly generates a new name for the project. The content is the same as before.
    
    <figure> 
    
    ![The remixed project.](imgs/setup3.png) <figcaption> **Figure 4**. The remixed project </figcaption> </figure>
4. If you plan on completing the next tutorial in this series, click **Sign In** and sign in to Glitch with your GitHub or Facebook account. If you don't sign in you will lose the ability to edit this project once you close the editing tab.

5. Click **Show Live**. A new tab opens, showing you the live page. This tab will be called the **live tab** throughout this tutorial.
    
    <figure> 
    
    ![The live tab.](imgs/setup4.png) <figcaption> **Figure 5**. The live tab </figcaption> </figure>

## Add content {: #add }

Your site is pretty empty. Follow the steps below to add some content to it!

1. In the **editor tab**, replace `<!-- You're "About Me" will go here. -->` with `<h1>About Me</h1>`.
    
    <pre class="prettyprint lang-html">{% htmlescape %}...

  

<p>
  Your site!
</p>
  <main>{% endhtmlescape %}

<strong>
  {% htmlescape %}  

<h1>
  About Me
</h1>{% endhtmlescape %}
  </strong>{% htmlescape %}</main>
  ...{% endhtmlescape %}</pre>



<p>
  
</p>

<figure>
   

<img src="imgs/add1.png"
        alt="The new code is highlighted in the editor tab." />
   <figcaption>
     <b>Figure 6</b>. The new code is highlighted in the editor tab
   </figcaption>
 </figure></li>


<li>
  <p>
    View your changes in the <strong>live tab</strong>. The text <code>About Me</code> is visible on the page.
    It's larger than the rest of the text, because the <code>&lt;h1&gt;</code> element represents
    a section heading. Your web browser automatically styles headings in larger
    font sizes.
  </p>
  
  
  <p>
    
  </p>
  
  <figure>
     
  <img src="imgs/add2.png"
        alt="The new heading is visible in the live tab." />
     <figcaption>
       <b>Figure 7</b>. The new heading is visible in the live tab
     </figcaption>
   </figure>
</li>


<li>
  <p>
    Back in the <strong>editor tab</strong>, insert <code>&lt;p&gt;I am learning HTML. Recent accomplishments:&lt;/p&gt;</code> on the line below
    where you just put <code>&lt;h1&gt;About Me&lt;/h1&gt;</code>.
  </p>
  
  
  <pre class="prettyprint lang-html">{% htmlescape %}...

  

<p>
  Your site!
</p>
  <main>
    

<h1>
  About Me
</h1>{% endhtmlescape %}

<strong>
  {% htmlescape %}  

<p>
  I am learning web development. Recent accomplishments:
</p>{% endhtmlescape %}
  </strong>{% htmlescape %}</main>
  ...{% endhtmlescape %}</pre>



<p>
  
</p>

<figure>
   

<img src="imgs/add3.png"
        alt="The new code is highlighted in the editor tab." />
   <figcaption>
     <b>Figure 8</b>. The new code is highlighted in the editor tab
   </figcaption>
 </figure></li>


<li>
  <p>
    View your change in the <strong>live tab</strong>.
  </p>
</li>


<li>
  <p>
    Back in the <strong>editor tab</strong>, add a list of your accomplishments:
  </p>
  
  
  <pre class="prettyprint lang-html">{% htmlescape %}...
  

<p>
  I am learning web development. Recent accomplishments:
</p>{% endhtmlescape %}

<strong>
  {% htmlescape %}

<ul>
  <li>
    Learned how to set up my code in Glitch.
  </li>
      
  
  <li>
    Added content to my HTML.
  </li>
      
  
  <li>
    TODO: Learn how to use Chrome DevTools to experiment with content changes.
  </li>
      
  
  <li>
    TODO: Learn the difference between HTML and the DOM.
  </li>
    
</ul>{% endhtmlescape %}</strong>{% htmlescape %}
...{% endhtmlescape %}</pre>
  
  
  
  <p>
    
  </p>
  
  <figure>
     
  <img src="imgs/add4.png"
        alt="The new code is highlighted in the editor tab." />
     <figcaption>
       <b>Figure 4</b>. The new code is highlighted in the editor tab
     </figcaption>
   </figure>
</li>


<li>
  <p>
    Again, go back to the <strong>live tab</strong> to make sure that the new content is displaying correctly.
  </p>
  
  
  <p>
    
  </p>
  
  <figure>
     
  <img src="imgs/add5.png"
        alt="The new list is visible in the live tab." />
     <figcaption>
       <b>Figure 4</b>. The new list is visible in the live tab
     </figcaption>
   </figure>
</li>
</ol>



<h2>
  Experiment with content changes in Chrome DevTools {: #experiment }
</h2>



<p>
  If you were developing a big page with a lot of HTML, you can imagine that it might be
  somewhat tedious to go back-and-forth between the editor tab and the live tab hundreds of times
  in order to see your changes, especially if you weren't sure what exactly to put on the page.
  Chrome DevTools can help you experiment with content changes without ever leaving the live tab.
</p>



<h3>
  Learn the difference between HTML and the DOM {: #DOM }
</h3>



<p>
  Before you start editing your content from Chrome DevTools, it's helpful to understand
  the difference between HTML and the DOM. The best way to learn is by example:
</p>



<ol start="1">
  <li>
    <p>
      Go to the <strong>live tab</strong>. At the bottom of your page you see the text <code>A new element!?!</code>.
    </p>
    
    
    <p>
      
    </p>
    
    <figure>
       
    <img src="imgs/dom1.png"
        alt="At the bottom of the page the text 'A new element!?!' can be seen." />
       <figcaption>
         <b>Figure 9</b>. At the bottom of the page the text <code>A new element!?!</code> can
         be seen
       </figcaption>
     </figure>
  </li>
  
  
  <li>
    <p>
      Go back to the <strong>editor tab</strong> and try to find this text in <code>index.html</code>. It's not there!
    </p>
    
    
    <p>
      
    </p>
    
    <figure>
       
    <img src="imgs/dom2.png"
        alt="The mystery text is nowhere to be found in index.html." />
       <figcaption>
         <b>Figure 10</b>. The mystery text <code>A new element!?!</code> is nowhere to
         be found in <code>index.html</code>
       </figcaption>
     </figure>
  </li>
  
  
  <li>
    <p>
      Go back to the <strong>live tab</strong>, right-click <code>A new element!?!</code>, and select <strong>Inspect</strong>.
    </p>
    
    
    <p>
      
    </p>
    
    <figure>
       
    <img src="imgs/dom3.png"
        alt="Inspecting some text." />
       <figcaption>
         <b>Figure 11</b>. Inspecting some text
       </figcaption>
     </figure>
    
    <p>
      DevTools opens up alongside your page. <code>&lt;div&gt;A new element!?!&lt;/div&gt;</code> is highlighted blue.
      Although this structure in DevTools looks like your HTML, it is actually the <strong>DOM Tree</strong>.
    </p>
    
    
    <p>
      
    </p>
    
    <figure>
       
    <img src="imgs/dom4.png"
        alt="DevTools is open alongside the page." />
       <figcaption>
         <b>Figure 12</b>. DevTools is open alongside the page
       </figcaption>
     </figure>
  </li>
  
</ol>



<p>
  When your page loads, the browser takes your HTML to create the <em>initial</em> content of the page. The
  DOM represents the <em>current</em> content of the page, which can change over time.
  The mysterious <code>&lt;div&gt;A new element!?!&lt;/div</code> content is added to your page because of the
  <code>&lt;script src="new.js"&gt;&lt;/script&gt;</code> tag at the bottom of your HTML. This tag causes some JavaScript
  code to run. You'll learn more about JavaScript in a later tutorial, but for now think of it as a
  programming language that can change the content of your page. In this particular case, JavaScript
  code adds <code>&lt;div&gt;A new element!?!&lt;/div&gt;</code> to your page. That is why this mystery text is visible on
  your live page, but not in your HTML.
</p>



<h3>
  Edit the DOM {: #edit }
</h3>



<p>
  If you want to quickly experiment with content changes without ever leaving the live tab,
  try DevTools.
</p>



<ol start="1">
  <li>
    <p>
      In DevTools, right-click <code>Your site!</code> and select <strong>Edit as HTML</strong>.
    </p>
    
    
    <p>
      
    </p>
    
    <figure>
       
    <img src="imgs/edit1.png"
        alt="Editing the node as HTML." />
       <figcaption>
         <b>Figure 13</b>. Editing the node as HTML
       </figcaption>
     </figure>
  </li>
  
  
  <li>
    <p>
      Replace <code>&lt;p&gt;Your site!&lt;/p&gt;</code> with the code below.
    </p>
    
    
    <pre class="prettyprint lang-html">{% htmlescape %}
&lt;header>
  

<p>
  <b>Welcome to my site!</b>
</p>
  

<button>Download my resume</button>
&lt;/header>
{% endhtmlescape %}</pre>
    
    
    <p>
      
    </p>
    
    <figure>
       
    <img src="imgs/edit2.png"
        alt="Editing the node as HTML." />
       <figcaption>
         <b>Figure 14</b>. Editing the node as HTML
       </figcaption>
     </figure>
  </li>
  
  
  <li>
    <p>
      Press <kbd>Command</kbd>+<kbd>Enter</kbd> (Mac) or <kbd>Control</kbd>+<kbd>Enter</kbd>
      (Windows, Linux, Chrome OS) to save your changes, or click outside of the box.
      Your changes automatically show up in the live view of your page. The text <code>Your site!</code>
      has been replaced with the new content.
    </p>
    
    
    <p>
      
    </p>
    
    <figure>
       
    <img src="imgs/edit3.png"
        alt="The new content shows up immediately on the page." />
       <figcaption>
         <b>Figure 15</b>. The new content shows up immediately on the page
       </figcaption>
     </figure>
  </li>
  
</ol>



<p>
  This workflow is only good for experimenting with content changes. If you reload the page or close the
  tab, your changes will be gone forever. If you're using this workflow and you want to save your changes,
  you need to manually copy those changes over to your HTML.
</p>



<p>
  The next couple of sections show you some more ways that you can change content from the DOM Tree.
</p>



<h2>
  Reorder nodes {: #reorder }
</h2>



<p>
  You can also change the order of DOM nodes. For example, on your web page the navigation menu is near the
  bottom. To move it to the top:
</p>



<ol start="1">
  <li>
    <p>
      Find the <code>&lt;nav&gt;</code> node in the <strong>DOM Tree</strong> of DevTools.
    </p>
    
    
    <p>
      
    </p>
    
    <figure>
       
    <img src="imgs/reorder1.png"
        alt="The nav node is highlighted blue in DevTools." />
       <figcaption>
         <b>Figure 16</b>. The nav node is highlighted blue in DevTools
       </figcaption>
     </figure>
  </li>
  
  
  <li>
    <p>
      Drag the <code>&lt;nav&gt;</code> node to the top, so that it's the first child below the <code>&lt;body&gt;</code> node.
    </p>
    
    
    <p>
      
    </p>
    
    <figure>
       
    <img src="imgs/reorder2.png"
        alt="Dragging the nav node to the top." />
       <figcaption>
         <b>Figure 17</b>. Dragging the nav node to the top
       </figcaption>
     </figure>
    
    <p>
      The <code>&lt;nav&gt;</code> node is now displaying at the top of your page.
    </p>
    
    
    <p>
      
    </p>
    
    <figure>
       
    <img src="imgs/reorder3.png"
        alt="The nav node is at the top of the page." />
       <figcaption>
         <b>Figure 18</b>. The nav node is at the top of the page
       </figcaption>
     </figure>
  </li>
  
</ol>



<h3>
  Delete a node {: #delete }
</h3>



<p>
  You can also remove nodes from the DOM Tree.
</p>



<ol start="1">
  <li>
    <p>
      In the <strong>DOM Tree</strong>, click <code>&lt;div&gt;A new element!?!&lt;/div&gt;</code>. DevTools highlights the node blue.
    </p>
    
    
    <p>
      
    </p>
    
    <figure>
       
    <img src="imgs/delete1.png"
        alt="Selecting the node to be deleted." />
       <figcaption>
         <b>Figure 19</b>. Selecting the node to be deleted
       </figcaption>
     </figure>
  </li>
  
  
  <li>
    <p>
      Press the <kbd>Delete</kbd> key on your keyboard. The <code>&lt;div&gt;A new element!?!&lt;/div&gt;</code> node is removed
      from your DOM Tree.
    </p>
    
    
    <p>
      
    </p>
    
    <figure>
       
    <img src="imgs/delete2.png"
        alt="The node has been deleted." />
       <figcaption>
         <b>Figure 20</b>. The node has been deleted
       </figcaption>
     </figure>
  </li>
  
</ol>



<h2>
  Copy your changes {: #copy }
</h2>



<p>
  You're almost done. You've made a few changes to your page in DevTools, but they're not yet saved to your
  source code.
</p>



<ol start="1">
  <li>
    <p>
      Reload your <strong>live tab</strong>. The changes that you made in the DOM Tree disappear. In particular,
      the text <code>Your site!</code> returns to the top of the page, and the text <code>A new element!?!</code> returns to the
      bottom.
    </p>
    
    
    <p>
      
    </p>
    
    <figure>
       
    <img src="imgs/copy1.png"
        alt="The changes that you've made are gone." />
       <figcaption>
         <b>Figure 21</b>. The changes that you've made are gone
       </figcaption>
     </figure>
  </li>
  
  
  <li>
    <p>
      Copy the code below.
    </p>
    
    
    <pre class="prettyprint notranslate lang-html">
&lt;!DOCTYPE html&gt;
&lt;html lang="en"&gt;
  &lt;head&gt;
    &lt;meta charset="utf-8"&gt;
    &lt;meta http-equiv="X-UA-Compatible" content="IE=edge"&gt;
    &lt;meta name="viewport" content="width=device-width, initial-scale=1"&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;header&gt;
      &lt;p&gt;Welcome to my site!&lt;/p&gt;
    &lt;/header&gt;
    &lt;nav&gt;
      &lt;ul&gt;
        &lt;li&gt;&lt;a href="/"&gt;Home&lt;/a&gt;&lt;/li&gt;
        &lt;li&gt;&lt;a href="/contact.html"&gt;Contact&lt;/a&gt;&lt;/li&gt;
      &lt;/ul&gt;
    &lt;/nav&gt;
    &lt;main&gt;
      &lt;h1&gt;About Me&lt;/h1&gt;
      &lt;p&gt;I am learning web development. Recent accomplishments:&lt;/p&gt;
      &lt;ul&gt;
        &lt;li&gt;Learned how to set up my code in Glitch.&lt;/li&gt;
        &lt;li&gt;Added content to my HTML.&lt;/li&gt;
        &lt;li&gt;Learned how to use Chrome DevTools to experiment with content changes.&lt;/li&gt;
        &lt;li&gt;Learned the difference between HTML and the DOM.&lt;/li&gt;
      &lt;/ul&gt;
    &lt;/main&gt;
  &lt;/body&gt;
&lt;/html&gt;
</pre>
  </li>
  
  
  <li>
    <p>
      Go back to the <strong>editor tab</strong> and replace the contents of your <code>index.html</code> file with the code that
      you just copied.
    </p>
    
    
    <p>
      
    </p>
    
    <figure>
       
    <img src="imgs/copy2.png"
        alt="How your index.html file should look." />
       <figcaption>
         <b>Figure 22</b>. How your <code>index.html</code> file should look
       </figcaption>
     </figure>
  </li>
  
</ol>



<h2>
  Next steps {: #next-steps}
</h2>



<ul>
  <li>
    Complete the next tutorial in this series, <a href="css">Get Started with CSS</a>, to learn how to style your page
    and experiment with style changes in Chrome DevTools.
  </li>
  
  
  <li>
    Read <a href="https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction">Introduction to the DOM</a>{: .external } to learn more about the DOM.
  </li>
  
  
  <li>
    Check out a course like <a href="https://www.coursera.org/learn/web-development">Introduction to Web Development</a>{: .external } to get
    more hands-on web development experience.
  </li>
  
</ul>



<h2>
  Feedback {: #feedback }
</h2>



<p>
  {% include "web/_shared/helpful.html" %}
</p>