project_path: /web/tools/_project.yaml book_path: /web/tools/_book.yaml description: Open the Command Menu and run the "Disable JavaScript" command.

{# wf_updated_on: 2019-02-04 #} {# wf_published_on: 2019-01-31 #} {# wf_blink_components: Platform>DevTools #}

# Disable JavaScript With Chrome DevTools {: .page-title }

{% include "web/_shared/contributors/kaycebasques.html" %}

To see how a web page looks and behaves when JavaScript is disabled:

1. [Open Chrome DevTools](/web/tools/chrome-devtools/open).
2. Press <kbd>Control</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> or <kbd>Command</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (Mac) to open the **Command Menu**.
    
    <figure> 
    
    ![The Command Menu.](/web/tools/chrome-devtools/images/shared/command-menu.png) <figcaption> **Figure 1**. The Command Menu </figcaption> </figure>
3. Start typing `javascript`, select **Disable JavaScript**, and then press <kbd>Enter</kbd> to run the command. JavaScript is now disabled.
    
    <figure> 
    
    ![Selecting 'Disable JavaScript' in the Command Menu.](/web/tools/chrome-devtools/javascript/imgs/disable-javascript.png) <figcaption> **Figure 2**. Selecting **Disable JavaScript** in the Command Menu </figcaption> </figure> 
    The yellow warning icon next to **Sources** reminds you that JavaScript is disabled.
    
    <figure> 
    
    ![The warning icon next to Sources.](/web/tools/chrome-devtools/javascript/imgs/disabled-javascript-warning.png) <figcaption> **Figure 3**. The warning icon next to **Sources** </figcaption> </figure>

JavaScript will remain disabled in this tab so long as you have DevTools open.

You may want to reload the page to see if and how the page depends on JavaScript while loading.

To re-enable JavaScript:

* Open the Command Menu again and run the **Enable JavaScript** command.
* Close DevTools.

## Feedback {: #feedback .hide-from-toc }

{% include "web/_shared/helpful.html" %}