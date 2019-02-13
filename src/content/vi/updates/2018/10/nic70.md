project_path: /web/_project.yaml book_path: /web/updates/_book.yaml description: What's new in Chrome 70 for developers?

{# wf_published_on: 2018-10-16 #} {# wf_updated_on: 2018-10-18 #} {# wf_featured_image: /web/updates/images/generic/new-in-chrome.png #} {# wf_tags: chrome70,new-in-chrome,progressive-web-apps,desktop,credentials,security,workers #} {# wf_featured_snippet: Chrome 70 adds support for Desktop Progressive Web Apps on Windows and Linux, support for Public Key Credentials to the Credential Management API, allows you to provide a `name` to dedicated `workers` and plenty more. Let’s dive in and see what’s new for developers in Chrome 70! #} {# wf_blink_components: N/A #}

# New in Chrome 70 {: .page-title }

{% include "web/_shared/contributors/petelepage.html" %}

<div class="clearfix"></div>

<div class="video-wrapper">
  <iframe class="devsite-embedded-youtube-video" data-video-id="msA284Q6yZU"
          data-autohide="1" data-showinfo="0" frameborder="0" allowfullscreen>
  </iframe>
</div>

In Chrome 70, we've added support for:

* [Desktop Progressive Web Apps on Windows & Linux](#dpwa-windows).
* The credential management API adds support for [Public Key Credentials](#pki).
* And you can now [name workers](#named-workers)!

And there’s [plenty more](#more)!

I’m [Pete LePage](https://mobile.twitter.com/petele). Let’s dive in and see what’s new for developers in Chrome 70!

<div class="clearfix"></div>

Note: Want the full list of changes? Check out the [Chromium source repository change list](https://chromium.googlesource.com/chromium/src/+log/69.0.3497.81..70.0.3538.66).

## Desktop Progressive Web Apps on Windows & Linux {: #dpwa-windows }

**Users can now install Desktop Progressive Web Apps on Windows & Linux!**

<a href="https://storage.googleapis.com/webfundamentals-assets/updates/2018/10/spotify-on-windows.mp4"></p> <video class="attempt-right screenshot" autoplay muted loop> <source type="video/webm" src="https://storage.googleapis.com/webfundamentals-assets/updates/2018/10/spotify-on-windows.webm"> <source type="video/mp4" src="https://storage.googleapis.com/webfundamentals-assets/updates/2018/10/spotify-on-windows.mp4"> </video> 

<p>
  </a>
</p>

<p>
  Once installed, they’re launched from the Start menu, and run like all other installed apps, without an address bar or tabs. <a href="/web/fundamentals/primers/service-workers/">Service workers</a> ensure that they’re fast, and reliably, the <a href="/web/updates/2018/05/dpwa#the_app_window">app window</a> experience makes them feel like any other installed app.
</p>

<p>
  Getting started isn't any different than what you're already doing today. All of the work you've done for your existing Progressive Web App still applies! If your app meets the standard <a href="/web/fundamentals/app-install-banners/#criteria">PWA criteria</a>, Chrome will fire the <a href="/web/fundamentals/app-install-banners/#listen_for_beforeinstallprompt"><code>beforeinstallprompt</code></a> event. Save the event; then, <a href="/web/fundamentals/app-install-banners/#notify_the_user_your_app_can_be_installed">add some UI</a> (like an install app button) to tell the user your app can be installed. Then, when the user clicks the button, call <a href="/web/fundamentals/app-install-banners/#show_the_prompt"><code>prompt()</code></a> on the saved event; Chrome will then show the prompt to the user. If they click add, Chrome will add your PWA to their start menu and desktop.
</p>

<p>
  See my <a href="/web/progressive-web-apps/desktop">Desktop PWAs</a> post for complete details.
</p>

<div class="clearfix"></div>

<p>
  Note: Mac support is expected to arrive in Chrome 72. Linux support was added in Chrome 70, but was accidentally left out of the original version of this post.
</p>

<div class="clearfix"></div>

<h2>
  Credential Management API: Public Key Credentials {: #pki }
</h2>

<p>
  The <a href="https://developer.mozilla.org/en-US/docs/Web/API/Credential_Management_API">Credential Management API</a> makes sign in super simple for users. It allows your site to interact with the browser’s <a href="https://developer.mozilla.org/en-US/docs/Web/API/PasswordCredential">credential manager</a> or <a href="https://developer.mozilla.org/en-US/docs/Web/API/FederatedCredential">federated account services</a> like Google and Facebook to sign.
</p>

<p>
  <img src="/web/updates/images/2018/10/webauth.png" class="attempt-right" />
</p>

<p>
  Chrome 70 adds support for a third type of credential: <a href="https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredential"><strong>Public Key Credential</strong></a>, which allows web applications to create and use, strong, cryptographically attested, and application-scoped credentials to strongly authenticate users.
</p>

<p>
  I'm pretty excited about it because it allows sites to use my fingerprint for 2-factor authentication. But, it also adds support for additional types of security keys and better security on the web.
</p>

<div class="clearfix"></div>

<p>
  Check the <a href="/web/fundamentals/security/credential-management/">Credential Management API docs</a> for more details or give it a try with the <a href="https://webauthndemo.appspot.com/">WebAuthn Demo</a> and how you can get started!
</p>

<div class="clearfix"></div>

<h2>
  Named <code>workers</code> {: #named-workers }
</h2>

<p>
  <a href="https://developer.mozilla.org/en-US/docs/Web/API/Worker">Workers</a> are an easy way to move JavaScript off the main thread and into the background. This is critical to keeping your site interactive, because it means that the main thread won’t lock up when it’s running an expensive or complex JavaScript computation.
</p> 

<style>
.worker-example {
  display: flex;
}
.worker-example p {
  white-space: nowrap;
}
.worker-example > div {
  padding: 0 0.5em 0.5em;
}
.no-worker {
  background-color: #FFEBEE;
}
.with-worker {
  background-color: #ECEFF1;
}

.spin-fast {
  animation: spin-smooth 1s linear infinite;
}
.spin-slow {
  animation: spin-smooth 2s linear infinite;
}
.spin-janky {
  animation: spin-janky 4s linear infinite;
}
@keyframes spin-smooth {
 100% { transform:rotate(360deg); }
}
@keyframes spin-janky {
 10% { transform:rotate(36deg); }
 20% { transform:rotate(72deg); }
 25% { transform:rotate(72deg); }
 30% { transform:rotate(108deg); }
 40% { transform:rotate(144deg); }
 50% { transform:rotate(180deg); }
 58% { transform:rotate(180deg); }
 60% { transform:rotate(216deg); }
 70% { transform:rotate(216deg); }
 80% { transform:rotate(288deg); }
 90% { transform:rotate(324deg); }
 100% { transform:rotate(360deg); }
}
</style>

<div class="worker-example">
  <div class="no-worker">
    <p><b>Without WebWorkers</b></p>
    <figure>
      <img class="spin-janky"
           src="https://www.gstatic.com/images/icons/material/system/2x/settings_black_48dp.png">
      <figcaption>
        <b>Main thread</b><br>
        Lots of heavy JavaScript running, resulting in slow, janky experience.
      </figcaption>
    </figure>
  </div>
  <div class="with-worker">
    <p><b>With WebWorkers</b></p>
    <div style="display:flex">
      <figure>
        <img class="spin-fast"
             src="https://www.gstatic.com/images/icons/material/system/2x/settings_black_48dp.png">
        <figcaption>
          <b>Main thread</b><br>
          No heavy JavaScript running, resulting in fast, smooth experience.
        </figcaption>
      </figure>
      <figure>
        <img class="spin-slow"
             src="https://www.gstatic.com/images/icons/material/system/2x/settings_black_48dp.png">
        <figcaption>
          <b>WebWorker</b><br>
          Lots of heavy JavaScript running, doesn't affect main thread.
        </figcaption>
      </figure>
    </div>
  </div>
</div>

<div class="clearfix"></div>

<p>
  In Chrome 70, workers now have a <a href="https://www.chromestatus.com/feature/4594144336936960"><code>name</code> attribute</a>, which is specified by an optional argument on the constructor.
</p>

<pre class="prettyprint lang-js">
const url = '/scripts/my-worker.js';

const wNYC = <strong>new Worker(url, {name: 'NewYork'});</strong>

<atrong>const oSF = {name: 'SanFrancisco'};</atrong>
const wSF = new Worker(url, <strong>oSF</strong>);
</pre>

<p>
  This lets you distinguish dedicated workers by <code>name</code> when you have multiple workers with the same URL. You can also print the name in the DevTools console, making it much easier to know which worker you’re debugging!
</p>

<p>
  Naming workers is already available in Firefox, Edge, and Safari. See the <a href="https://github.com/whatwg/html/issues/2477">discussion on GitHub</a> for more details.
</p>

<div class="clearfix"></div>

<h2>
  And more! {: #more }
</h2>

<p>
  These are just a few of the changes in Chrome 70 for developers, of course, there’s plenty more.
</p>

<ul>
  <li>
    <a href="/web/updates/2015/07/interact-with-ble-devices-on-the-web">Web Bluetooth</a> is <a href="https://www.chromestatus.com/feature/5264933985976320">now available in Windows 10</a>, and allows your site to communicate with nearby user-selected Bluetooth devices in a secure and privacy-preserving way.
  </li>
  <li>
    Chrome can <a href="https://www.chromestatus.com/feature/5544632075157504">send intervention and deprecation messages</a> to your servers using the <code>Report-To HTTP</code> Response header field or surface them in the <code>ReportingObserver</code> interface.
  </li>
  <li>
    There are a number of important deprecations you should know about, check the <a href="/web/updates/2018/09/chrome-70-deps-rems">Deprecations and removals in Chrome 70</a> post for more details.
  </li>
  <li>
    And be sure to check out the latest <a href="/web/updates/2018/08/devtools">What's new in DevTools</a> post to learn what's new in Chrome DevTools.
  </li>
</ul>

<div class="clearfix"></div>

<h3>
  Subscribe
</h3>

<p>
  Want to stay up to date with our videos, then <a href="https://goo.gl/6FP1a5">subscribe</a> to our <a href="https://www.youtube.com/user/ChromeDevelopers/">Chrome Developers YouTube channel</a>, and you’ll get an email notification whenever we launch a new video, or add our <a href="/web/shows/rss.xml">RSS feed</a> to your feed reader.
</p>

<p>
  I’m Pete LePage, and as soon as Chrome 71 is released, I’ll be right here to tell you -- what’s new in Chrome!
</p>

<h2>
  Feedback {: .hide-from-toc }
</h2>

<p>
  {% include "web/_shared/helpful.html" %}
</p>

<div class="clearfix"></div>

<p>
  {% include "web/_shared/rss-widget-updates.html" %}
</p>