project_path: /web/tools/_project.yaml book_path: /web/tools/_book.yaml description: Learn how to view messages and run JavaScript in the Console.

{# wf_updated_on: 2018-12-19 #} {# wf_published_on: 2018-03-08 #} {# wf_blink_components: Platform>DevTools #}

{% include "web/tools/chrome-devtools/_shared/styles.html" %}

# Get Started With The Console {: .page-title }

{% include "web/_shared/contributors/kaycebasques.html" %}

This tutorial teaches you how to use the **Console** in Chrome DevTools.

<figure>
  <img src="/web/tools/chrome-devtools/images/panels/console.png"
       alt="The Console.">
  <figcaption><b>Figure 1</b>. The <b>Console</b></figcaption>
</figure>

The **Console** has two main functions:

* Viewing diagnostic information about the page. This information can come from the web developers that built the page, or from the browser.
* Running JavaScript. You can view and change the page's [DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction){:.external} by typing JavaScript statements in the **Console**. Or, if you just want to experiment, you can use the **Console** as your code playground to run code that is not related to the page at all.

This tutorial is interactive. You're going to open up DevTools on this very page in order to get hands-on experience with the **Console**.

## Step 1: View messages {: #view }

Messages in the **Console** come from either the page's JavaScript, or from the browser.

### Part A: View messages from the page's JavaScript {: #page }

The [**Console** API](/web/tools/chrome-devtools/console/console-reference) lets you log messages from your JavaScript to the **Console**.

1. Press <kbd>Command</kbd>+<kbd>Option</kbd>+<kbd>J</kbd> (Mac) or <kbd>Control</kbd>+<kbd>Shift</kbd>+<kbd>J</kbd> (Windows, Linux, Chrome OS) to open the **Console**, right here on this very page.
    
    <figure> 
    
    ![The Console, opened alongside this very page.](images/open.png) <figcaption> **Figure 2**. The **Console**, opened alongside this very page </figcaption> </figure>
2. Click **Log A Message**. You should see the text `click listener executed` get logged to the **Console**.
    
    {% framebox width="auto" height="auto" enable_widgets="true" %} <button class="gc-analytics-event" data-category="DevTools"
             data-label="Console / Get Started / 1.A.1 (Log)">Log a message</button> <script>
       document.querySelector('button').addEventListener('click', function () {
         console.log('click listener executed');
       });
     </script>
 {% endframebox %}
    
    This message is logged to the **Console** because the button's `click` [event listener](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events){:.external} instructs the browser to run `console.log('click listener
 executed')` when the button is clicked.

3. To the right of the message there is a link. Click that link now. DevTools opens the **Sources** panel and shows you the line of code that caused the message to get logged.
    
    <figure> 
    
    ![Highlighted in yellow is the line of code that caused the message to get logged.](images/cause.png) <figcaption> **Figure 3**. Highlighted in yellow is the line of code that caused the message to get logged </figcaption> </figure>
4. Click the **Console** tab to go back to the **Console**.

5. The `console` object has other methods for printing messages. Click **Debug** to see how the **Console** prints `console.debug()` messages. If your **Console** is set to its default settings, you won't see any thing.
    
    {% framebox width="auto" height="auto" enable_widgets="true" %} <button class="gc-analytics-event" data-category="DevTools"
           data-label="Console / Get Started / 1.A.2 (Debug)">debug</button> 

<script>
     var button = document.querySelector('button');
     button.addEventListener('click', function () {
       console.debug('debug');
     });
   </script>

 
    
    {% endframebox %}

6. If you didn't see anything, click the dropdown menu that says **Default Levels** or **Custom Levels** and enable **Verbose**. You should now see the text `debug` in your **Console**. `console.debug()` messages are styled the same as `console.log()` ones.
    
    The **Console** displays messages in chronological order. The newest message is at the bottom.

7. Click the buttons below to see how the remaining message types \--- `console.info()`, `console.warn()`, and `console.error()` \--- are styled in the **Console**.
    
    {% framebox width="auto" height="auto" enable_widgets="true" %} 

<style>
       button { margin: 1em; }
     </style>

 
    
         <button class="gc-analytics-event" data-category="DevTools"
                 data-label="Console / Get Started / 1.A.3 (Info)">info</button>
         <button class="gc-analytics-event" data-category="DevTools"
                 data-label="Console / Get Started / 1.A.4 (Warn)">warn</button>
         <button class="gc-analytics-event" data-category="DevTools"
                 data-label="Console / Get Started / 1.A.5 (Error)">error</button>
         <script>
           function exampleFunctionA() {
             console.warn('warn');
           }
           function exampleFunctionB() {
             console.error('error');
           }
           function exampleFunctionC(e) {
             e.target.textContent === 'warn' ? exampleFunctionA() : exampleFunctionB();
           }
           var buttons = document.querySelectorAll('button');
           buttons[0].addEventListener('click', function () {
             console.info('info');
           });
           buttons[1].addEventListener('click', exampleFunctionC);
           buttons[2].addEventListener('click', exampleFunctionC);
         </script>
        
    
    {% endframebox %}
    
    Use `console.warn()` to warn that something has happened in your code that may cause problems. Use `console.error()` to call out a critical error.

8. Click **Expand** ![The Expand icon](/web/tools/chrome-devtools/images/shared/expand.png){:.inline-icon} next to `warn` and `error` to see the [call stack](https://developer.mozilla.org/en-US/docs/Glossary/Call_stack){:.external} leading up to those messages. The function at the bottom of the stack called the one above it.
    
    <figure> 
    
    ![The call stack leading up to console.error().](images/error-stack.png) <figcaption> **Figure 4**. The call stack leading up to `console.error()` </figcaption> </figure>

### Part B: View messages from the browser {: #browser }

The browser can also log messages to the Console. This usually occurs when you write incorrect code.

1. Click **Throw Error**. The browser logs a `TypeError`.
    
    {% framebox width="auto" height="auto" enable_widgets="true" %} <button class="gc-analytics-event" data-category="DevTools"
             data-label="Console / Get Started / 1.B.1 (TypeError)">Throw Error</button> <script>
       const button = document.querySelector('button');
       button.addEventListener('click', function () {
         boosh.howard = "I don't buffet about in the winds of fashion.";
       });
     </script>
 {% endframebox %}
    
    The browser throws this error because the button's click listener is trying to access an object property that doesn't exist.

2. Click **Throw 404**. The browser logs a `404 (Not Found)` error, as well as others.
    
    {% framebox width="auto" height="auto" enable_widgets="true" %} <button class="gc-analytics-event" data-category="DevTools"
             data-label="Console / Get Started / 1.B.2 (404)">Throw 404</button> <script>
       const button = document.querySelector('button');
       button.addEventListener('click', function () {
         const url = "not/a/real/file.png";
         fetch(url);
       });
     </script>
 {% endframebox %}
    
    The browser throws these errors when a page tries to request a file that doesn't exist.

### Part C: Filter messages {: #filter }

On big sites, you'll sometimes see the **Console** get flooded with messages. You can filter the **Console** to only show messages that you care about.

1. Click **Log Numbers**. The **Console** prints out whether each number from 1 to 1000 is prime. Every third message is printed with `console.warn()`. In real life you should only use `console.warn()` for warning scenarios, but this is just a contrived example to demonstrate filtering.
    
    {% framebox width="auto" height="auto" enable_widgets="true" %} {% includecode content_path="web/tools/chrome-devtools/console/_code/primes.html" %} {% endframebox %}

2. Type `123` in the **Filter** text box. The **Console** only shows messages that contain `123` in either the content of the message, or the filename that caused the message.

3. Replace `123` with `-not`. The **Console** hides any message that contains `not`. Using the pattern `-<text>` hides any message that includes `<text>`.
4. Replace `-not` with `/1[0-9]1/`, which is a [regular expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions){:.external}. The **Console** only shows messages that include a 3-digit number that starts with `1` and ends with `1`. Keep the filter enabled and continue to the next step.

5. Click **Show Console Sidebar** ![Show Console Sidebar](/web/tools/chrome-devtools/images/shared/show-console-sidebar.png){: .inline-icon }. The **Sidebar** lets you further filter messages by type.

6. Click **333 Warnings**. DevTools now only shows messages that were logged with `console.warn()`. Remember that the `/1[0-9]1/` filter is still active, so you actually are filtering along 2 dimensions right now.
    
    <figure> 
    
    ![Filtering with the Sidebar and a regular expression, simultaneously.](images/sidebar-regex.png) <figcaption> **Figure 5**. Filtering with the **Sidebar** and a regular expression, simultaneously </figcaption> </figure>
7. Close the **Sidebar** and delete `/1[0-9]1/` from the **Filter** text box.

## Step 2: Run JavaScript {: #javascript }

The **Console** is also a [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop){:.external}, which stands for Read, Evaluate, Print, and Loop. In other words, you can run JavaScript statements in the **Console**, and the **Console** prints out the results.

### Part A: View and change the page's JavaScript or DOM {: #page }

When building or debugging a page, it's often useful to run statements in the **Console** in order to change how the page looks or runs.

1. Your **Console** is probably cluttered up from all the messages in the previous section. Click **Clear Console** ![Clear Console](images/clear-console-button.png){.cdt-inl}. Hover over the button to see its keyboard shortcuts.

2. Type `document.getElementById('changeMyText').textContent = 'Hello'` in the **Console** and then press <kbd>Enter</kbd> to attempt to change the text of the button below from `Change My Text` to `Hello`. It probably won't work. You'll find out why next.
    
    {% framebox width="auto" height="auto" enable_widgets="true" %} <button id="changeMyText">Change My Text</button> <script>
       document.getElementById('changeMyText').addEventListener('click', function () {
         console.log('This button doesn\'t do anything :)');
       });
     </script>
 {% endframebox %}
    
    This probably didn't work for you because the button is embedded in an [`iframe`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe){:.external}, which means it's in a different execution context. An `iframe` element lets you embed a page within another page, without giving that sub-page access to your main page. This is how most ads on the web are distributed.
    
    <figure> 
    
    ![Unsuccessfully attempting to change the button's text.](images/change-fail.png) <figcaption> **Figure 6**. Unsuccessfully attempting to change the button's text </figcaption> </figure>
3. Notice the dropdown menu to the left of the **Filter** text box. It probably says **Top**. **Top** represents the execution context of your main page.

4. Right-click **Change My Text** and select **Inspect**. DevTools jumps to the **Elements** panel and highlights the element in the **DOM Tree**.
    
    <figure> 
    
    ![Inspecting the button.](images/inspect-button.png) <figcaption> **Figure 7**. Inspecting the button </figcaption> </figure>
5. Press <kbd>Escape</kbd>. The **Console** opens up at the bottom of the **Elements** panel. Note how the dropdown that used to say **Top** now says something else, and it's background is colored red. This means that the **Console** is now in a different execution context. You're in a different execution context because the **Change My Text** button is selected in the **DOM Tree**, and that button is embedded in an `iframe`.
    
    <figure> 
    
    ![The Console opened at the bottom of the Elements panel, and in a different
             execution context.](images/iframe-context.png) <figcaption> **Figure 8**. The **Console** opened at the bottom of the **Elements** panel, and in a different execution context </figcaption> </figure>
6. Try running `document.getElementById('changeMyText').textContent = 'Hello'` again. You don't have to type it out or copy-paste it. Just focus the **Console** and press the <kbd>Up Arrow</kbd> key. DevTools remembers your history. After running the statement, look at the button's text again. This time, it should have successfully changed.

Hopefully you get the idea that this workflow is completely open-ended. You can run any JavaScript here. This is a flexible way to debug pages and explore how they're built.

### Part B: Run arbitrary JavaScript {: #arbitrary }

Sometimes, you just want a code playground where you can test out JavaScript features that you're not familiar with. The **Console** is the perfect place to do this. For example, ES6 introduced a nice feature where you can [define default values for function arguments](http://es6-features.org/#DefaultParameterValues){:.external}. Try it now:

1. Type the following code into the **Console**. Try typing it, rather than copy-pasting it, in order to to see how DevTools intelligently decides whether to continue to let you enter input, or to evaluate the code.
    
        function add(a, b=20) {
          return a + b;
        }
        

2. Type the following code in the **Console** to call the function that you just defined.
    
        add(25);
        

## Next steps {: #next-steps }

Congrats, you're now familiar with the core uses of the **Console**. Below are more resources for learning how to use it more effectively.

### View messages

See the [Console API Reference](/web/tools/chrome-devtools/console/console-reference) to learn all of the ways that you can print messages to the **Console**.

### Run JavaScript to view and change a page

DevTools lets you pause a script in the middle of its execution. While you're paused, you can use the **Console** to view and change the page at that moment in time. This makes for a powerful debugging workflow. See [Get Started With Debugging JavaScript](/web/tools/chrome-devtools/javascript/) for an interactive tutorial.

The **Console** also has a set of convenience functions that make it easier to interact with a page. For example:

* Rather than typing `document.querySelector()` to select an element, you can type `$()`. This syntax is inspired by jQuery, but it's not actually jQuery. It's just an alias for `document.querySelector()`.
* `debug(function)` effectively sets a breakpoint on the first line of that function.
* `keys(object)` returns an array containing the keys of the specified object.

See [Command Line API Reference](/web/tools/chrome-devtools/console/command-line-reference) for the full reference.

## Feedback {: #feedback }

{% include "web/_shared/helpful.html" %}

{# Runs on page load. #}

{% framebox width="0px" height="0px" enable_widgets="true" %} 

<script>
    console.log('%cWelcome to the Console!', 'font-weight:bold;color:#317efb;font-style:italic',
        'Read on to learn how messages like this get here.');
  </script>

 

{% endframebox %}