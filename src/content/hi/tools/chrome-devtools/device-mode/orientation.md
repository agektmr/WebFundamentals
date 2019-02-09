project_path: /web/tools/_project.yaml book_path: /web/tools/_book.yaml description: Open the Sensors tab and go to the "Orientation" section.

{# wf_updated_on: 2018-12-18 #} {# wf_published_on: 2018-12-18 #} {# wf_blink_components: Platform>DevTools #}

# Simulate Device Orientation With Chrome DevTools {: .page-title }

{% include "web/_shared/contributors/kaycebasques.html" %}

To simulate different [device orientations](/web/fundamentals/native-hardware/device-orientation/) from Chrome DevTools:

1. Press <kbd>Command</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (Mac) or <kbd>Control</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (Windows, Linux, Chrome OS) to open the **Command Menu**.
    
    <figure> 
    
    ![The Command Menu.](/web/tools/chrome-devtools/images/shared/command-menu.png) <figcaption> **Figure 1**. The Command Menu </figcaption> </figure>
2. Type `sensors`, select **Show Sensors**, and press <kbd>Enter</kbd>. The **Sensors** tab opens up at the bottom of your DevTools window.

3. From the **Orientation** list select one of the preset orientations, like **Portrait upside down**, or select **Custom orientation** to provide your own exact orientation.
    
    <figure> 
    
    ![Selecting 'Portrait upside down' from the 'Orientation' list.](/web/tools/chrome-devtools/device-mode/imgs/portrait-upside-down.png) <figcaption> **Figure 2**. Selecting **Portrait upside down** from the **Orientation** list</b> </figcaption> </figure> 
    After selecting **Custom orientation** the **alpha**, **beta**, and **gamma** fields are enabled. See [Alpha](/web/fundamentals/native-hardware/device-orientation/#alpha), [Beta](/web/fundamentals/native-hardware/device-orientation/#beta), and [Gamma](/web/fundamentals/native-hardware/device-orientation/#gamma) to understand how these axes work.
    
    You can also set a custom orientation by dragging the **Orientation Model**. Hold <kbd>Shift</kbd> before dragging to rotate along the **alpha** axis.<figure> 
    
    ![The Orientation Model.](/web/tools/chrome-devtools/device-mode/imgs/orientation-model.png) <figcaption> **Figure 3**. The **Orientation Model** </figcaption> </figure>

## Feedback {: #feedback .hide-from-toc }

{% include "web/_shared/helpful.html" %}