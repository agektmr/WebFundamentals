{# wf_md_include #}

### Try out the initial app {: #starting-point }

The client-side JavaScript in the app fetches the top 10 Hacker News (HN) articles, and then populates the HTML with the content.

Note: This tutorial uses Google Chrome and Chrome DevTools to demonstrate how the web app behaves when offline. You can use [any browser that supports service workers](http://caniuse.com/#search=service%20workers).

1. Click **Show**. The live app appears in a new tab.
    
    <figure> 
    
    ![The live app](/web/tools/workbox/guides/codelabs/imgs/shared/live.png) <figcaption> **Figure 2**. The live app </figcaption> </figure>
2. In the tab that's running the live app, press <kbd>Command</kbd>+<kbd>Option</kbd>+<kbd>J</kbd> (Mac) or <kbd>Control</kbd>+<kbd>Shift</kbd>+<kbd>J</kbd> (Windows, Linux) to open DevTools.

3. Focus DevTools and press <kbd>Command</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (Mac) or <kbd>Control</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (Windows, Linux) to open the **Command Menu**.
4. Type `Offline`, select **Go offline**, then press <kbd>Enter</kbd>. Google Chrome now has no connection to the Internet in this tab.
    
    <figure> 
    
    ![The 'Go Offline' command](/web/tools/workbox/guides/codelabs/imgs/shared/offline.png) <figcaption> **Figure 3**. The **Go Offline** command </figcaption> </figure>
5. Reload the page. Google Chrome says that you're offline. In other words, the app doesn't work at all when offline.
    
    <figure> 
    
    ![The initial app doesn't work at all when offline](/web/tools/workbox/guides/codelabs/imgs/shared/no-internet.png) <figcaption> **Figure 4**. The initial app doesn't work at all when offline </figcaption> </figure>
6. Open the **Command Menu** again, type `Online`, and select **Go online** to restore your internet connection in this tab.