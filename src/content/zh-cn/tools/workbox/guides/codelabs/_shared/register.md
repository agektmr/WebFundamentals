{# wf_md_include #}

## Step 4: Register and inspect the generated service worker {: #register }

Workbox has generated a service worker, but there's no reference to it from your app, yet.

1. Click `src/app.js` to open that file.
2. Register your service worker at the bottom of `init()`.
    
    <pre class="prettyprint">function init() {
  ...
  <strong>if ('serviceWorker' in navigator) {
    window.addEventListener('load', () => {
      navigator.serviceWorker.register('/sw.js').then(registration => {
        console.log('SW registered: ', registration);
      }).catch(registrationError => {
        console.log('SW registration failed: ', registrationError);
      });
    });
  }</strong>
}</pre>
3. Re-focus the tab that's running the live version of your app. In the DevTools **Console** you see a message indicating that the service worker was registered.

4. Click the **Application** tab of DevTools.
5. Click the **Service Workers** tab.
    
    <figure> 
    
    ![The Service Workers pane](/web/tools/workbox/guides/codelabs/imgs/shared/sw-pane.png) <figcaption> **Figure 6**. The Service Workers pane </figcaption> </figure>
6. Click **sw.js**, next to **Source**. DevTools displays the service worker code that Workbox generated. It should look close to this:
    
    <figure> 
    
    ![The generated service worker code](/web/tools/workbox/guides/codelabs/imgs/shared/sources.png) <figcaption> **Figure 7**. The generated service worker code </figcaption> </figure>

### Try out the offline-capable app {: #try-incomplete }

Your app now sort-of works offline. Try it now:

1. In the live version of your app, use DevTools to go offline again. Focus DevTools and press <kbd>Command</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (Mac) or <kbd>Control</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (Windows, Linux) to open the **Command Menu**. Type `Offline`, select **Go offline**, then press <kbd>Enter</kbd>.
2. Reload the page. The title of the page appears, but the list of the top 10 stories doesn't.
3. Click the **Network** tab in DevTools. The request for `topstories.json` is red, meaning that it failed. This is why the list isn't appearing. The app tries to make a request for `https://hacker-news.firebaseio.com/v0/topstories.json`, but the request fails since you're offline and you haven't instructed Workbox to cache this resource, yet.
    
    <figure> 
    
    ![The incomplete offline experience](/web/tools/workbox/guides/codelabs/imgs/shared/offline-capable.png) <figcaption> **Figure 8**. The incomplete offline experience </figcaption> </figure>
4. Use the **Command Menu** in DevTools to go back online.

### Optional: How the service worker code works {: #optional-generated }

The service worker code is generated based on your Workbox configuration.

* `importScripts('{% include "web/tools/workbox/_shared/workbox-sw-cdn-url.html" %}');` imports Workbox's service worker library. You can inspect this file from the **Sources** panel of DevTools.<figure> 
    
    ![The code for Workbox's service worker library](/web/tools/workbox/guides/codelabs/imgs/shared/lib-src.png) <figcaption> **Figure 9**. The code for Workbox's service worker library </figcaption> </figure>
* The `self.__precacheManifest` array lists all of the resources that Workbox is precaching.

* Each resource has a `revision` property. This is how Workbox determines when to update a resource. Each time you build your app, Workbox generates a hash based on the contents of the resource. If the contents change, then the `revision` hash changes.
* When the service worker runs, it writes the `url` and `revision` of each resource to [IndexedDB](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API) (IDB) if it doesn't exist. If the resource does exist, the service worker checks that the `revision` in its code matches the `revision` in IDB. If the hashes don't match, then the resource has changed, and therefore the service worker needs to download the updated resource and update the hash in IDB.

In sum, Workbox only re-downloads resources when they change, and ensures that your app always caches the most up-to-date version of each resource.