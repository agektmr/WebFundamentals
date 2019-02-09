project_path: /web/tools/_project.yaml book_path: /web/tools/_book.yaml description: Open the "Rendering" tab and select "Emulate CSS media" > "print".

{# wf_updated_on: 2018-12-14 #} {# wf_published_on: 2018-12-14 #} {# wf_blink_components: Platform>DevTools #}

# Force Chrome DevTools Into Print Preview Mode (CSS Print Media Type) {: .page-title }

{% include "web/_shared/contributors/kaycebasques.html" %}

The [print media query](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries) controls how your page looks when printed. To force your page into print preview mode:

1. Press <kbd>Command</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (Mac) or <kbd>Control</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (Windows, Linux, Chrome OS) to open the **Command Menu**.
    
    <figure> 
    
    ![The Command Menu](/web/tools/chrome-devtools/images/shared/command-menu.png) <figcaption> **Figure 1**. The **Command Menu** </figure>
2. Type `rendering`, select **Show Rendering**, and then press <kbd>Enter</kbd>.

3. Under **Emulate CSS media** select **print**.
    
    <figure> 
    
    ![Print preview mode.](/web/tools/chrome-devtools/css/imgs/print-mode.png) <figcaption> **Figure 2**. Print preview mode </figure>

From here, you can view and change your CSS, like any other web page. See [Get Started With Viewing And Changing CSS](/web/tools/chrome-devtools/css/).

## Feedback {: #feedback .hide-from-toc }

{% include "web/_shared/helpful.html" %}