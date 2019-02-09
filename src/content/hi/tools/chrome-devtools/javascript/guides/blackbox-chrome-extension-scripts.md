project_path: /web/tools/_project.yaml book_path: /web/tools/_book.yaml description: Enable "Blackbox content scripts" from Settings > Blackboxing.

{# wf_updated_on: 2018-12-14 #} {# wf_published_on: 2018-12-14 #} {# wf_blink_components: Platform>DevTools #}

# Blackbox Chrome Extension Scripts {: .page-title }

{% include "web/_shared/contributors/kaycebasques.html" %}

When using the **Sources** panel of Chrome DevTools to [step through code](/web/tools/chrome-devtools/javascript/#code-stepping), sometimes you pause on code that you don't recognize. You're probably paused on the code of one of the Chrome Extensions that you've installed. To never pause on extension code:

1. Press <kbd>F1</kbd> to open **Settings**. Or open it from **Main Menu** ![Main Menu](/web/tools/chrome-devtools/images/shared/main-menu.png){: .inline-icon } > **Settings**.

2. Open the **Blackboxing** tab.

3. Enable the **Blackbox content scripts** checkbox.
    
    <figure> 
    
    ![Enabling the 'Blackbox content scripts' checkbox.](/web/tools/chrome-devtools/javascript/guides/images/blackbox-content-scripts.png) <figcaption> **Figure 1**. Enabling the **Blackbox content scripts** checkbox </figure>

## Feedback {: #feedback .hide-from-toc }

{% include "web/_shared/helpful.html" %}