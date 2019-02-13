project_path: /web/_project.yaml book_path: /web/ilt/pwa/_book.yaml

{# wf_auto_generated #} {# wf_updated_on: 2017-09-28 #} {# wf_published_on: 2016-01-01 #}

# Tools for PWA Developers {: .page-title }

<div id="opendevtools"></div>

## Open Developer Tools

<div id="chromedevtools"></div>

### Chrome

To access **Developer Tools** ("[DevTools](/web/tools/chrome-devtools/)") in Chrome, open a web page or web app in Google Chrome. Click the **Chrome menu** <img src="img/dc66ff026f4af280.png" style="width:20px;height:20px;" alt="Chrome Menu Icon" /> icon, and then select **More Tools** > **Developer Tools**.

You can also use the keyboard shortcut <kbd>Control+Shift+I</kbd> on Windows and Linux, or <kbd>⌘+alt+I</kbd> on Mac (see the [Keyboard and UI Shortcuts Reference](/web/tools/chrome-devtools/inspect-styles/shortcuts)). Alternatively, right-click anywhere on the page and select Inspect.

On a Mac, you can also select **View** > **Developer** > **Developer Tools** in the Chrome menu bar at the top of the screen.

The **DevTools** window opens in your Chrome browser.

<div id="firefoxdevtools"></div>

### Firefox

To open Developer Tools in Firefox, open a web page or web app in Firefox. Click the Menu icon <img src="img/7fe46717c086da27.png" style="width:20px;height:20px;" alt="Firefox Menu Icon" /> in the browser toolbar, and then click **Developer** > **Toggle Tools**.

You can also use the keyboard shortcut <kbd>Control+Shift+I</kbd> on Windows and Linux, or <kbd>⌘ + alt + I</kbd> on Mac (see the [Keyboard Shortcuts Reference](https://developer.mozilla.org/en-US/docs/Tools/Keyboard_shortcuts)).

On Mac, you can also select **View __> __Web Developer __> __Toggle Tools** in the Firefox menu bar at the top of the screen.

The **Toolbox** window opens in your Firefox browser.

<div id="operadevtools"></div>

### Opera

To launch **Opera Dragonfly**, open a web page or web app in Opera. Use the keyboard shortcut <kbd>Ctrl + Shift + I</kbd> on Windows and Linux, or <kbd>⌘ + alt + I</kbd> on Mac. Alternatively, you can target a specific element by right-clicking in the page and selecting "Inspect Element".

On a Mac, you can also select **View > Show Developer Menu** in the Opera menu bar at the top of the screen. Then select **Developer > Developer Tools**.

The **Dragonfly** window opens in your Opera browser.

<div id="iedevtools"></div>

### Internet Explorer

To open Developer Tools in Internet Explorer, open a web page or web app in Internet Explorer. Press <kbd>F12</kbd> or click **Developer Tools** from the **Tools** menu.

<div id="safaridevtools"></div>

### Safari

To start using **Web Inspector** in Safari, open a web page or web app in Safari. In the menu bar, select **Safari** > **Preferences**. Go to the **Advanced** pane and enable the "Show Develop menu in menu bar" setting. In the menu bar, select **Develop** > **Show Web Inspector**.

You can also use the keyboard shortcut <kbd>⌘ + ⌥ + I</kbd>.

The **Web Inspector** window opens in your Safari browser.

<div id="console"></div>

## Open the console

<div id="chromeconsole"></div>

### Chrome

To open the dedicated **Console** panel, either:

* Press <kbd>Ctrl + Shift + J</kbd> (Windows / Linux) or <kbd>⌘ + ⌥ + J</kbd> (Mac).
* [Open **DevTools**](#chromedevtools) and select the **Console** panel.

![Console in Chrome](img/37a8715708d445b7.png)

See [Using the Console](/web/tools/chrome-devtools/console/) for more information.

<div id="firefoxconsole"></div>

### Firefox

To open the Web Console, either:

* Press <kbd>Ctrl + Shift + K</kbd> (Windows/Linux) or <kbd>⌘ + ⌥ + K</kbd> (Mac).
* From the Firefox menu (or Tools menu if you display the menu bar or are on Mac OS X), select __Developer > Web Console. __
* [Open the **Toolbox**](#firefoxdevtools) and select the **Console** panel.

![Console in Firefox](img/13a38f1279b3aa2.png)

See [Opening the Web Console](https://developer.mozilla.org/en-US/docs/Tools/Web_Console/Opening_the_Web_Console) for more information.

<div id="operaconsole"></div>

### Opera

[Open **Dragonfly**](#operadevtools) and select the **Console** panel.

![Console in Opera](img/8403c7af6f2e2281.png)

### Internet Explorer

[Open Developer Tools](#iedevtools) and select the **Console** panel.

### Safari

To open the **Console**, either:

* [Enable the Developer menu](#safaridevtools). From the menu bar, select **Develop** > **Show Error Console**.
* Press <kbd>⌘ + ⌥ + C</kbd>
* [Open the Web Inspector](#safaridevtools) and select the **Console** panel.

![Console in Safari](img/5569b9d73d1c879.png)

<div id="network"></div>

## Work with the network

<div id="viewnetwork"></div>

### View network requests

<div id="chromerequests"></div>

#### Chrome

[Open **DevTools**](#chromedevtools) and select the **Network** panel. Requests are displayed in the **Network** panel's **Requests Table**. See [Measure Resource Loading Times](/web/tools/chrome-devtools/network-performance/resource-loading?utm_source=dcc&utm_medium=redirect&utm_campaign=2016q3) for more information.

![View Network Requests in Chrome](img/1fcd33a8eacc126b.png)

<div id="firefoxrequests"></div>

#### Firefox

[Open the **Toolbox**](#firefoxdevtools) and select the **Network** panel. See [Network Monitor](https://developer.mozilla.org/en-US/docs/Tools/Network_Monitor) for more information.

![View Network Requests in Firefox](img/711b3dc929202919.png)

<div id="operarequests"></div>

#### Opera

See [View Network Requests in Chrome](#chromerequests).

<div id="ierequests"></div>

#### Internet Explorer

[Open Developer Tools](#iedevtools), and then open the **Network** panel. See [Network](https://developer.microsoft.com/en-us/microsoft-edge/platform/documentation/f12-devtools-guide/network/) for more information.

<div id="safarirequests"></div>

#### Safari

[Open the **Web Inspector**](#safaridevtools), and then open the **Network** panel.

![View Network Requests in Safari](img/a5b9f79db4820056.png)

<div id="offline"></div>

### Simulate offline behavior

<div id="chromeoffline"></div>

#### Chrome

[Open **DevTools**](#chromedevtools) and select the **Network** panel. Check the **Offline** checkbox. Check out [Optimize Performance Under Varying Network Conditions](/web/tools/chrome-devtools/network-performance/network-conditions) for more information.

![Simulate Offline in Chrome](img/fe171eca066e4ee.png)

<div id="firefoxoffline"></div>

#### Firefox

Click menu icon <img src="img/7fe46717c086da27.png" style="width:20px;height:20px;" alt="Firefox Menu Icon" /> in the browser toolbar. Then click **Developer** > **Work Offline**.

![Work Offline in Firefox](img/b2ebcf485e2cc2ed.png)

On Mac, you can enable offline mode from the menu bar by clicking **File** > **Work Offline**.

![Work Offline in Firefox](img/45e13f82e6216e31.png)

<div id="manifest"></div>

## Inspect the manifest

<div id="chromemanifest"></div>

#### Chrome

[Open **DevTools**](#chromedevtools) in Chrome. Click the **Application** panel, and then click **Manifest** in the navigation bar.

![View Manifest in Chrome](img/29e17a75fcd9df99.png)

If your app has a **manifest.json** file, the options you have defined will be listed here.

You can test the add to homescreen feature from this pane. Click **Add to homescreen**. You should see an "add this site to your shelf" message.

![Add to Homescreen in Chrome](img/c6682f7c49dde4f4.png)

<div id="serviceworker"></div>

## Interact with service workers in the browser

<div id="accesssw"></div>

### Inspect the service worker

<div id="chromesw"></div>

#### Chrome

[Open **DevTools**](#chromedevtools) in Chrome. Click the **Application** panel, and then click **Service Workers** in the navigation bar.

![Service Workers in DevTools](img/e825904b1ab30ff7.png)

If a service worker is installed for the currently open page, you'll see it listed on this pane. For example, in the screenshot above there's a service worker installed for the scope of `https://events.google.com/io2016/`.

#### chrome://serviceworker-internals/

You can also view a list of all service workers by navigating to **chrome://serviceworker-internals/** in your Chrome browser.

![Chrome Service Worker Internals](img/d0f255989e3aa71d.png)

<div id="firefoxsw"></div>

#### Firefox

The **about:debugging** page provides an interface for interacting with Service Workers.

There are several different ways to open **about:debugging**:

* On Mac, in the **Tools** > **Web Developer** menu, click **Service Workers**.
* Click the Menu icon <img src="img/7fe46717c086da27.png" style="width:20px;height:20px;" alt="Firefox Menu Icon" /> in the browser toolbar.

Then click the Developer icon <img src="img/71072a17a8634436.png" style="width:20px;height:20px;" alt="Firefox Menu Icon" /> and select **Service Workers**.

* Enter "about:debugging" in the Firefox URL bar and click **Workers**.

![Firefox Service Worker](img/49229fd8759a0547.png)

<div id="unregister"></div>

### Unregister the service worker

<div id="chromeunregister"></div>

#### Chrome

[Open the Service Workers pane](#chromesw) in **DevTools**. Click **Unregister** next to the service worker.

![Unregister a Service Worker in Chrome](img/43a5fb58b30c942e.png)

<div id="firefoxunregister"></div>

#### Firefox

[Open the Workers page in **about:debugging**](#firefoxsw). Click **Unregister** next to the service worker scope.

![Unregister a Service Worker in Firefox](img/1426bd86abcf7ae8.png)

<div id="update"></div>

### Force update the service worker

<div id="chromeupdate"></div>

#### Chrome

There are several ways to force-update the service worker in Chrome:

1. Refresh your app in the browser so the new service worker is recognized. Then hold <kbd>Shift</kbd> and click the Reload icon <img src="img/879b00a99b4bcb97.png" style="width:20px;height:20px;" alt="Chrome Reload Icon" /> .
2. [Open the Service Workers pane](#chromesw) in **DevTools**. Click **Update**. When the new service worker installs, click **skipWaiting**.

![Skip Waiting in Chrome](img/77b5eaa130252f7e.png)

3. To force the service worker to update automatically whenever you reload the page, check **Update on reload**.

![Update Service Worker on Reload in Chrome](img/3431837468013f78.png)

4. [Unregister the service worker](#chromeunregister) and refresh the app in the browser.

<div id="firefoxupdate"></div>

#### Firefox

To update the service worker in Firefox, close all pages controlled by the service worker and then reopen them. The service worker only updates when there are no pages open in Firefox that are within its scope.

If you want to be absolutely certain (for testing reasons) that the service worker will update, you can [unregister the service worker](#firefoxunregister) from the **about:debugging** page and refresh your app in the browser. The new service worker installs on page reload.

Note that unregistering the service worker will change the subscription object if you are working with Push Notifications. Be sure to use the new subscription object if you unregister the service worker.

<div id="push"></div>

### Send simulated push notifications

<div id="chromepush"></div>

#### Chrome

[Open the Service Workers pane](#chromesw) in **DevTools**. Click **Push** to ping the service worker.

![Send Push from DevTools](img/5032f49fde7b0274.png)

<div id="firefoxpush"></div>

#### Firefox

Navigate to **about:debugging** in Firefox and select **Workers**. Click **Push**. If the worker isn't running, you will see **Start** instead of **Push**. Click **Start** to start the service worker, then click **Push**.

![Send Push in Firefox](img/cd2a860dcddbc873.png)

<div id="permissions"></div>

## Check notification permissions

<div id="chromepermissions"></div>

### Chrome

Click the Information icon in the URL bar. Use the **Notifications** dropdown menu to set the permission status for **Notifications**.

![Access Site Permissions in Chrome](img/eae0f39fca38f6f2.png)

<div id="firefoxpermissions"></div>

### Firefox

Click the Information icon in the URL bar. Use the **Receive Notifications** dropdown menu to set the permission status for notifications.

![Access Site Permissions in Firefox](img/95e5d187eaa95142.png)

<div id="storage"></div>

## Inspect cache storage

<div id="cache"></div>

### Check the service worker cache

<div id="chromecache"></div>

#### Chrome

[Open **DevTools**](#chromedevtools) and select the **Application** panel. In the navigation bar click **Cache Storage** to see a list of caches. Click a specific cache to see the resources it contains.

![View the Service Worker Cache in Chrome](img/b46b92cc3c6d3d3a.png)

<div id="firefoxcache"></div>

#### Firefox

[Open the **Toolbox**](#firefoxdevtools) and click the Settings icon to open **Settings**. Under **Default Firefox Developer Tools**, check **Storage**.

![Enable Storage Inspector in Firefox](img/fcc0b0ed0728e578.png)

Open the **Storage** panel and expand the **Cache Storage** node. Select a cache to see its contents.

![View the Service Worker Cache in Firefox](img/96aeba2e8aff5869.png)

See the MDN article on the [Storage Inspector](https://developer.mozilla.org/en-US/docs/Tools/Storage_Inspector) for more information.

<div id="clearcache"></div>

### Clear the service worker cache

#### Chrome

[Go to **Cache Storage**](#chromecache) in **DevTools**. In the **Application** panel, expand **Cache Storage**. Right-click the cache name and then select **Delete**.

![Clear the Service Worker Cache in Chrome](img/dd0b5fd1762c05c0.png)

#### Firefox

[Go to **Cache Storage**](#firefoxcache) in **DevTools**. In the **Storage** panel, expand **Cache Storage** and the appropriate domain. Right-click the cache name and then select **Delete All**.

![Clear the Service Worker Cache in Firefox](img/940a818ae4d7d6.png)

<div id="indexeddb"></div>

### Check IndexedDB

<div id="chromeindexeddb"></div>

#### Chrome

In **DevTools**, navigate to the **Application** tab. Select **IndexedDB**. You may need to click Reload <img src="img/879b00a99b4bcb97.png" style="width:20px;height:20px;" alt="Chrome Reload Icon" /> to update the contents.

![View IndexedDB in Chrome](img/e9220dcc82da209e.png)

<div id="firefoxindexeddb"></div>

#### Firefox

[Open the **Toolbox**](#firefoxdevtools) and click the Settings icon to open **Settings**. Under **Default Firefox Developer Tools, __check __Storage**.

![Enable Storage Inspector in Firefox](img/fcc0b0ed0728e578.png)

Open the **Storage** panel and expand the **IndexedDB** node. Select a database, object store, or index to see its contents.

![View IndexedDB in Firefox](img/852f7c79a3322b45.png)

<div id="clearindexeddb"></div>

### Clear IndexedDB

In all browsers that support IndexedDB, you can delete a database by entering the following in the console:

`indexedDB.deleteDatabase('database_name');`

Where `database_name` is the name of the database to delete.

#### Chrome

[Open **IndexedDB**](#chromeindexeddb) in **DevTools**. In the navigation pane, expand **IndexedDB**, right-click the object store to clear, and then click **Clear**.

![Clear IndexedDB in Chrome](img/ef127d70355d5e4.png)

<div id="disablehttpcache"></div>

### Disable HTTP Cache

#### Chrome

[Open **DevTools**](#chromedevtools) and open the **Network** panel. Check the **Disable cache** checkbox.

![Disable HTTP Cache in Chrome](img/625447d2942ef3da.png)

#### Firefox

[Open the **Toolbox**](#firefoxdevtools) and click the Settings icon to open the **Settings**. Under **Advanced settings**, select **Disable HTTP Cache**.

![Disable HTTP Cache in Firefox](img/df759390516a0bae.png)

<div id="mobile"></div>

## Simulate mobile devices

Each browser has it's own version of device simulation and testing. See the documentation for each:

* [Chrome](/web/tools/chrome-devtools/device-mode/)
* [Firefox](https://developer.mozilla.org/en-US/docs/Tools/Responsive_Design_Mode#Device_selection)
* [Edge](https://docs.microsoft.com/en-us/microsoft-edge/f12-devtools-guide/emulation)
* [Safari](https://support.apple.com/kb/PH26266?locale=en_US&viewlocale=en_US)

These tools give you a close approximation as to how your site will look on a mobile device, but to get the full picture you should always test your site on real devices. Here is documentation for debugging Android devices on [Chrome](/web/tools/chrome-devtools/remote-debugging/) and [Firefox](https://developer.mozilla.org/en-US/docs/Tools/Remote_Debugging).

<div id="resources"></div>

## Further reading

### Chrome

* [Debugging Progressive Web Apps](/web/tools/chrome-devtools/progressive-web-apps)

### Safari

* [Web Development Tools](https://developer.apple.com/safari/tools/)
* [Safari Web Inspector Guide](https://developer.apple.com/library/content/documentation/AppleApplications/Conceptual/Safari_Developer_Guide/GettingStarted/GettingStarted.html)

### Firefox

* [Opening Settings](https://developer.mozilla.org/en-US/docs/Tools/Settings)

### Opera

* [Opera Dragonfly documentation](http://www.opera.com/dragonfly/documentation/)

### Internet Explorer

* [Using the Debugger Console](https://msdn.microsoft.com/en-us/library/dd565628(v=vs.85).aspx#db_console)
* [Debugging Script with the Developer Tools](https://msdn.microsoft.com/en-us/library/dd565625(v=vs.85).aspx)
* [Using the Console to view errors and debug](https://msdn.microsoft.com/en-us/library/dn255006(v=vs.85).aspx)