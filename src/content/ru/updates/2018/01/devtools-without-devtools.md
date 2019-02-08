project_path: /web/_project.yaml book_path: /web/updates/_book.yaml description: Use Puppeteer to launch Chromium with DevTools features enabled.

{# wf_updated_on: 2018-03-05 #} {# wf_published_on: 2018-01-22 #} {# wf_tags: devtools #} {# wf_featured_image: /web/updates/images/generic/chrome-devtools.png #} {# wf_featured_snippet: Use Puppeteer to launch Chromium with DevTools features enabled. #} {# wf_blink_components: Platform>DevTools, Internals>Headless #}

{% include "web/tools/chrome-devtools/_shared/styles.html" %}

# Using DevTools Features Without Opening DevTools {: .page-title }

{% include "web/_shared/contributors/kaycebasques.html" %}

I commonly see questions along the lines of "I really like feature X of DevTools, but it stops working when I close DevTools. How do I keep feature X running even when DevTools is closed?"

The short answer is: you probably can't.

However, you *can* hack together a [Puppeteer](https://github.com/GoogleChrome/puppeteer){:.external} script that launches Chromium, opens a remote debugging client, then turns on the DevTools feature that you like (via the [Chrome DevTools Protocol](https://chromedevtools.github.io/devtools-protocol/){:.external}), without ever explicitly opening DevTools.

For example, the script below lets me overlay the [FPS Meter](/web/tools/chrome-devtools/evaluate-performance/reference#fps-meter) over the top-right of the viewport, even though DevTools never opens, as you can see in the video below.

    // Node.js version: 8.9.4
    const puppeteer = require('puppeteer'); // version 1.0.0
    
    (async () => {
      // Prevent Puppeteer from showing the "Chrome is being controlled by automated test
      // software" prompt, but otherwise use Puppeteer's default args.
      const args = await puppeteer.defaultArgs().filter(flag => flag !== '--enable-automation');
      const browser = await puppeteer.launch({
        headless: false,
        ignoreDefaultArgs: true,
        args
      });
      const page = await browser.newPage();
      const devtoolsProtocolClient = await page.target().createCDPSession();
      await devtoolsProtocolClient.send('Overlay.setShowFPSCounter', { show: true });
      await page.goto('https://developers.google.com/web/tools/chrome-devtools');
    })();
    

<style>
  video { width: 100%; }
</style>

<video controls>
  <source src="https://storage.googleapis.com/webfundamentals-assets/updates/2018/01/devtools.mp4">
</video>

This is just one of many, many DevTools features that you can potentially access via the Chrome DevTools Protocol.

A general suggestion: check out the [Puppeteer API](https://github.com/GoogleChrome/puppeteer/blob/master/docs/api.md){:.external} before resorting to creating a DevTools Protocol client. Puppeteer already has dedicated APIs for many DevTools features, such as [code coverage](https://github.com/GoogleChrome/puppeteer/blob/master/docs/api.md#class-coverage){:.external} and [intercepting **Console** messages](https://github.com/GoogleChrome/puppeteer/blob/master/docs/api.md#event-console){:.external}.

If you need help accessing a DevTools feature via Puppeteer, [ask a question on Stack Overflow](https://stackoverflow.com/questions/ask?tags=google-chrome-devtools,puppeteer){:.external}.

If you want to show off a Puppeteer script that makes use of the DevTools Protocol, tweet us at [@ChromeDevTools](https://twitter.com/chromedevtools){:.external}.

{% include "web/_shared/rss-widget-updates.html" %}