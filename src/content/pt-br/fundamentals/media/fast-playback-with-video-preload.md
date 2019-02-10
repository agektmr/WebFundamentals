project_path: /web/fundamentals/_project.yaml book_path: /web/fundamentals/_book.yaml description: Preload video and audio for faster playback.

{# wf_published_on: 2017-08-17 #} {# wf_updated_on: 2018-09-20 #} {# wf_blink_components: Blink>Media #}

# Fast Playback with Video Preload {: .page-title }

{% include "web/_shared/contributors/beaufortfrancois.html" %}

Faster playback start means more people watching your video. That's a known fact. In this article I'll explore techniques you can use to accelerate your media playback by actively preloading resources depending on your use case.

Note: Unless specified otherwise, this article also applies to the audio element.

<figure>
  <video controls controlslist="nodownload" muted playsinline style="width: 100%">
    <source src="https://storage.googleapis.com/webfundamentals-assets/videos/video-preload-hero.webm#t=1.1"
            type="video/webm">
    <source src="https://storage.googleapis.com/webfundamentals-assets/videos/video-preload-hero.mp4#t=1.1"
            type="video/mp4">
  </video>
  <figcaption>
    <p>Credits: copyright Blender Foundation | <a href="http://www.blender.org">www.blender.org </a>.</p>
  </figcaption>
</figure>

### TL;DR {: .hide-from-toc }

<table>
  <tr>
    <th>
    </th>
    
    <th>
      It's great...
    </th>
    
    <th>
      But...
    </th>
  </tr>
  
  <tr>
    <td rowspan=3 style="white-space: nowrap">
<a href="#video_preload_attribute">Video preload attribute</a>
 </td> <td rowspan=3> Simple to use for a unique file hosted on a web server. </td> 
    
    <td>
      Browsers may completely ignore the attribute.
    </td>
    
    <tr>
      <td>
        Resource fetching starts when the HTML document has been completely loaded and parsed.
      </td>
    </tr>
    
    <tr>
      <td>
        MSE ignores the preload attribute on media elements because the app is responsible for providing media to MSE.
      </td>
    </tr>
    
    <tr>
      <td rowspan=2 style="white-space: nowrap">
<a href="#link_preload">Link preload</a>
 </td> 
      
      <td>
        Forces the browser to make a request for a video resource without blocking the document's <code>onload</code> event.
      </td>
      
      <td>
        HTTP Range requests are not compatible.
      </td>
      
      <tr>
        <td>
          Compatible with MSE and file segments.
        </td>
        
        <td>
          Should be used only for small media files (<5 MB) when fetching full resources.
        </td>
      </tr>
      
      <tr>
        <td>
          
<a href="#manual_buffering">Manual buffering</a>
        </td>
        
        <td>
          Full control
        </td>
        
        <td>
          Complex error handling is the website's responsibility.
        </td>
      </tr></tbody> </table> 
      
      <h2>
        Video preload attribute
      </h2>
      
      <p>
        If the video source is a unique file hosted on a web server, you may want to use the video <code>preload</code> attribute to provide a hint to the browser as to <a href="/web/fundamentals/media/video#preload">how much information or content to preload</a>. This means <a href="/web/fundamentals/media/mse/basics">Media Source Extensions (MSE)</a> is not compatible with <code>preload</code>.
      </p>
      
      <p>
        Resource fetching will start only when the initial HTML document has been completely loaded and parsed (e.g. the <code>DOMContentLoaded</code> event has fired) while the very different <code>window.onload</code> event will be fired when resource has actually been fetched.
      </p>

<figure>
  <img src="/web/fundamentals/media/images/video-preload/video-preload.svg">
</figure>

      
      <p>
        Setting the <code>preload</code> attribute to <code>metadata</code> indicates that the user is not expected to need the video, but that fetching its metadata (dimensions, track list, duration, and so on) is desirable. Note that starting in <a href="/web/updates/2017/12/chrome-63-64-media-updates#media-preload-defaults-metadata">Chrome 64</a>, the default value for <code>preload</code> is <code>metadata</code>. (It was <code>auto</code> previously).
      </p>
      
      <pre><code>&lt;video id="video" preload="metadata" src="file.mp4" controls&gt;&lt;/video&gt;

&lt;script&gt;
  video.addEventListener('loadedmetadata', function() {
    if (video.buffered.length === 0) return;

    var bufferedSeconds = video.buffered.end(0) - video.buffered.start(0);
    console.log(bufferedSeconds + ' seconds of video are ready to play!');
  });
&lt;/script&gt;
</code></pre>
      
      <p>
        Setting the <code>preload</code> attribute to <code>auto</code> indicates that the browser may cache enough data that complete playback is possible without requiring a stop for further buffering.
      </p>
      
      <pre><code>&lt;video id="video" preload="auto" src="file.mp4" controls&gt;&lt;/video&gt;

&lt;script&gt;
  video.addEventListener('loadedmetadata', function() {
    if (video.buffered.length === 0) return;

    var bufferedSeconds = video.buffered.end(0) - video.buffered.start(0);
    console.log(bufferedSeconds + ' seconds of video are ready to play!');
  });
&lt;/script&gt;
</code></pre>
      
      <p>
        There are some caveats though. As this is just a hint, the browser may completely ignore the <code>preload</code> attribute. At the time of writing, here are some rules applied in Chrome:
      </p>
      
      <ul>
        <li>
          When <a href="https://support.google.com/chrome/answer/2392284">Data Saver</a> is enabled, Chrome forces the <code>preload</code> value to <code>none</code>.
        </li>
        <li>
          In Android 4.3, Chrome forces the <code>preload</code> value to <code>none</code> due to an <a href="https://bugs.chromium.org/p/chromium/issues/detail?id=612909">Android bug</a>.
        </li>
        <li>
          On a cellular connection (2G, 3G, and 4G), Chrome forces the <code>preload</code> value to <code>metadata</code>.
        </li>
      </ul>
      
      <h3>
        Tips
      </h3>
      
      <p>
        If your website contains many video resources on the same domain, I would recommend you set the <code>preload</code> value to <code>metadata</code> or define the <code>poster</code> attribute and set <code>preload</code> to <code>none</code>. That way, you would avoid hitting the maximum number of HTTP connections to the same domain (6 according to the HTTP 1.1 spec) which can hang loading of resources. Note that this may also improve page speed if videos aren't part of your core user experience.
      </p>
      
      <h2>
        Link preload
      </h2>
      
      <p>
        As <a href="/web/updates/2016/03/link-rel-preload">covered</a> in other <a href="https://www.smashingmagazine.com/2016/02/preload-what-is-it-good-for/">articles</a>, <a href="https://w3c.github.io/preload/">link preload</a> is a declarative fetch that allows you to force the browser to make a request for a resource without blocking the <code>window.onload</code> event and while the page is downloading. Resources loaded via <code>&lt;link rel="preload"&gt;</code> are stored locally in the browser, and are effectively inert until they're explicitly referenced in the DOM, JavaScript, or CSS.
      </p>
      
      <p>
        Preload is different from prefetch in that it focuses on current navigation and fetches resources with priority based on their type (script, style, font, video, audio, etc.). It should be used to warm up the browser cache for current sessions.
      </p>

<figure>
  <img src="/web/fundamentals/media/images/video-preload/link-preload.svg">
</figure>

      
      <h3>
        Preload full video
      </h3>
      
      <p>
        Here's how to preload a full video on your website so that when your JavaScript asks to fetch video content, it is read from cache as the resource may have already been cached by the browser. If the preload request hasn't finished yet, a regular network fetch will happen.
      </p>
      
      <pre><code>&lt;link rel="preload" as="video" href="https://cdn.com/small-file.mp4"&gt;

&lt;video id="video" controls&gt;&lt;/video&gt;

&lt;script&gt;
  // Later on, after some condition has been met, set video source to the
  // preloaded video URL.
  video.src = 'https://cdn.com/small-file.mp4';
  video.play().then(_ =&gt; {
    // If preloaded video URL was already cached, playback started immediately.
  });
&lt;/script&gt;
</code></pre>
      
      <p>
        Note: I would recommend using this only for small media files (< 5MB).
      </p>
      
      <p>
        Because the preloaded resource is going to be consumed by a video element in the example, the <code>as</code> preload link value is <code>video</code>. If it were an audio element, it would be <code>as="audio"</code>.
      </p>
      
      <h3>
        Preload the first segment
      </h3>
      
      <p>
        The example below shows how to preload the first segment of a video with <code>&lt;link
rel="preload"&gt;</code> and use it with Media Source Extensions. If you're not familiar with the MSE Javascript API, please read <a href="/web/fundamentals/media/mse/basics">MSE basics</a>.
      </p>
      
      <p>
        For the sake of simplicity, let's assume the entire video has been split into smaller files like "file_1.webm", "file_2.webm", "file_3.webm", etc.
      </p>
      
      <pre><code>&lt;link rel="preload" as="fetch" href="https://cdn.com/file_1.webm"&gt;

&lt;video id="video" controls&gt;&lt;/video&gt;

&lt;script&gt;
  const mediaSource = new MediaSource();
  video.src = URL.createObjectURL(mediaSource);
  mediaSource.addEventListener('sourceopen', sourceOpen, { once: true });

  function sourceOpen() {
    URL.revokeObjectURL(video.src);
    const sourceBuffer = mediaSource.addSourceBuffer('video/webm; codecs="vp09.00.10.08"');

    // If video is preloaded already, fetch will return immediately a response
    // from the browser cache (memory cache). Otherwise, it will perform a
    // regular network fetch.
    fetch('https://cdn.com/file_1.webm')
    .then(response =&gt; response.arrayBuffer())
    .then(data =&gt; {
      // Append the data into the new sourceBuffer.
      sourceBuffer.appendBuffer(data);
      // TODO: Fetch file_2.webm when user starts playing video.
    })
    .catch(error =&gt; {
      // TODO: Show "Video is not available" message to user.
    });
  }
&lt;/script&gt;
</code></pre>
      
      <p>
        Warning: For cross-origin resources, make sure your CORS headers are set properly. As we can't create an array buffer from an opaque response retrieved with <code>fetch(videoFileUrl, { mode: 'no-cors' })</code>, we won't be able to feed any video or audio element.
      </p>
      
      <h3>
        Support
      </h3>
      
      <p>
        Link preload is not supported in every browser yet. You may want to detect its availability with the snippets below to adjust your performance metrics.
      </p>
      
      <pre><code>function preloadFullVideoSupported() {
  const link = document.createElement('link');
  link.as = 'video';
  return (link.as === 'video');
}

function preloadFirstSegmentSupported() {
  const link = document.createElement('link');
  link.as = 'fetch';
  return (link.as === 'fetch');
}
</code></pre>
      
      <h2>
        Manual buffering
      </h2>
      
      <p>
        Before we dive into the <a href="https://developer.mozilla.org/en-US/docs/Web/API/Cache">Cache API</a> and service workers, let's see how to manually buffer a video with MSE. The example below assumes that your web server supports HTTP Range requests but this would be pretty similar with file segments. Note that some middleware libraries such as <a href="https://github.com/google/shaka-player">Google's Shaka Player</a>, <a href="https://developer.jwplayer.com/">JW Player</a>, and <a href="http://videojs.com/">Video.js</a> are built to handle this for you.
      </p>
      
      <pre><code>&lt;video id="video" controls&gt;&lt;/video&gt;

&lt;script&gt;
  const mediaSource = new MediaSource();
  video.src = URL.createObjectURL(mediaSource);
  mediaSource.addEventListener('sourceopen', sourceOpen, { once: true });

  function sourceOpen() {
    URL.revokeObjectURL(video.src);
    const sourceBuffer = mediaSource.addSourceBuffer('video/webm; codecs="vp09.00.10.08"');

    // Fetch beginning of the video by setting the Range HTTP request header.
    fetch('file.webm', { headers: { range: 'bytes=0-567139' } })
    .then(response =&gt; response.arrayBuffer())
    .then(data =&gt; {
      sourceBuffer.appendBuffer(data);
      sourceBuffer.addEventListener('updateend', updateEnd, { once: true });
    });
  }

  function updateEnd() {
    // Video is now ready to play!
    var bufferedSeconds = video.buffered.end(0) - video.buffered.start(0);
    console.log(bufferedSeconds + ' seconds of video are ready to play!');

    // Fetch the next segment of video when user starts playing the video.
    video.addEventListener('playing', fetchNextSegment, { once: true });
  }

  function fetchNextSegment() {
    fetch('file.webm', { headers: { range: 'bytes=567140-1196488' } })
    .then(response =&gt; response.arrayBuffer())
    .then(data =&gt; {
      const sourceBuffer = mediaSource.sourceBuffers[0];
      sourceBuffer.appendBuffer(data);
      // TODO: Fetch further segment and append it.
    });
  }
&lt;/script&gt;
</code></pre>
      
      <h3>
        Considerations
      </h3>
      
      <p>
        As you're now in control of the entire media buffering experience, I suggest you consider the device's battery level, the "Data-Saver Mode" user preference and network information when thinking about preloading.
      </p>
      
      <h4>
        Battery awareness
      </h4>
      
      <p>
        Please take into account the battery level of users' devices before thinking about preloading a video. This will preserve battery life when the power level is low.
      </p>
      
      <p>
        Disable preload or at least preload a lower resolution video when the device is running out of battery.
      </p>
      
      <pre><code>if ('getBattery' in navigator) {
  navigator.getBattery()
  .then(battery =&gt; {
    // If battery is charging or battery level is high enough
    if (battery.charging || battery.level &gt; 0.15) {
      // TODO: Preload the first segment of a video.
    }
  });
}
</code></pre>
      
      <h4>
        Detect "Data-Saver"
      </h4>
      
      <p>
        Use the <code>Save-Data</code> client hint request header to deliver fast and light applications to users who have opted-in to "data savings" mode in their browser. By identifying this request header, your application can customize and deliver an optimized user experience to cost- and performance-constrained users.
      </p>
      
      <p>
        Learn more by reading our complete <a href="/web/updates/2016/02/save-data">Delivering Fast and Light Applications with Save-Data</a> article.
      </p>
      
      <h4>
        Smart loading based on network information
      </h4>
      
      <p>
        You may want to check <code>navigator.connection.type</code> prior to preloading. When it's set to <code>cellular</code>, you could prevent preloading and advise users that their mobile network operator might be charging for the bandwidth, and only start automatic playback of previously cached content.
      </p>
      
      <pre><code>if ('connection' in navigator) {
  if (navigator.connection.type == 'cellular') {
    // TODO: Prompt user before preloading video
  } else {
    // TODO: Preload the first segment of a video.
  }
}
</code></pre>
      
      <p>
        Checkout the <a href="https://googlechrome.github.io/samples/network-information/">Network Information sample</a> to learn how to react to network changes as well.
      </p>
      
      <h3>
        Pre-cache multiple first segments
      </h3>
      
      <p>
        Now what if I want to speculatively pre-load some media content without knowing which piece of media the user will eventually pick. If the user is on a web page that contains 10 videos, we probably have enough memory to fetch one segment file from each but we should definitely not create 10 hidden video elements and 10 <code>MediaSource</code> objects and start feeding that data.
      </p>
      
      <p>
        The two part example below shows you how to pre-cache multiple first segments of video using the powerful and easy-to-use Cache API. Note that something similar can be achieved with IndexedDB as well. We're not using service workers yet as the Cache API is also accessible from the Window object.
      </p>
      
      <h4>
        Fetch and cache
      </h4>
      
      <pre><code>const videoFileUrls = [
  'bat_video_file_1.webm',
  'cow_video_file_1.webm',
  'dog_video_file_1.webm',
  'fox_video_file_1.webm',
];

// Let's create a video pre-cache and store all first segments of videos inside.
window.caches.open('video-pre-cache')
.then(cache =&gt; Promise.all(videoFileUrls.map(videoFileUrl =&gt; fetchAndCache(videoFileUrl, cache))));

function fetchAndCache(videoFileUrl, cache) {
  // Check first if video is in the cache.
  return cache.match(videoFileUrl)
  .then(cacheResponse =&gt; {
    // Let's return cached response if video is already in the cache.
    if (cacheResponse) {
      return cacheResponse;
    }
    // Otherwise, fetch the video from the network.
    return fetch(videoFileUrl)
    .then(networkResponse =&gt; {
      // Add the response to the cache and return network response in parallel.
      cache.put(videoFileUrl, networkResponse.clone());
      return networkResponse;
    });
  });
}
</code></pre>
      
      <p>
        Note that if I were to use HTTP Range requests, I would have to manually recreate a <code>Response</code> object as the Cache API doesn't support Range responses <a href="https://github.com/whatwg/fetch/issues/144">yet</a>. Be mindful that calling <code>networkResponse.arrayBuffer()</code> fetches the whole content of the response at once into renderer memory, which is why you may want to use small ranges.
      </p>
      
      <p>
        For reference, I've modified part of the example above to save HTTP Range requests to the video pre-cache.
      </p>
      
      <pre><code>    ...
    return fetch(videoFileUrl, { headers: { range: 'bytes=0-567139' } })
    .then(networkResponse =&gt; networkResponse.arrayBuffer())
    .then(data =&gt; {
      const response = new Response(data);
      // Add the response to the cache and return network response in parallel.
      cache.put(videoFileUrl, response.clone());
      return response;
    });
</code></pre>
      
      <h4>
        Play video
      </h4>
      
      <p>
        When a user clicks a play button, we'll fetch the first segment of video available in the Cache API so that playback starts immediately if available. Otherwise, we'll simply fetch it from the network. Keep in mind that browsers and users may decide to clear the <a href="/web/fundamentals/instant-and-offline/web-storage/offline-for-pwa">Cache</a>.
      </p>
      
      <p>
        As seen before, we use MSE to feed that first segment of video to the video element.
      </p>
      
      <pre><code>function onPlayButtonClick(videoFileUrl) {
  video.load(); // Used to be able to play video later.

  window.caches.open('video-pre-cache')
  .then(cache =&gt; fetchAndCache(videoFileUrl, cache)) // Defined above.
  .then(response =&gt; response.arrayBuffer())
  .then(data =&gt; {
    const mediaSource = new MediaSource();
    video.src = URL.createObjectURL(mediaSource);
    mediaSource.addEventListener('sourceopen', sourceOpen, { once: true });

    function sourceOpen() {
      URL.revokeObjectURL(video.src);

      const sourceBuffer = mediaSource.addSourceBuffer('video/webm; codecs="vp09.00.10.08"');
      sourceBuffer.appendBuffer(data);

      video.play().then(_ =&gt; {
        // TODO: Fetch the rest of the video when user starts playing video.
      });
    }
  });
}
</code></pre>
      
      <p>
        Warning: For cross-origin resources, make sure your CORS headers are set properly. As we can't create an array buffer from an opaque response retrieved with <code>fetch(videoFileUrl, { mode: 'no-cors' })</code>, we won't be able to feed any video or audio element.
      </p>
      
      <h3>
        Create Range responses with a service worker
      </h3>
      
      <p>
        Now what if you have fetched an entire video file and saved it in the Cache API. When the browser sends an HTTP Range request, you certainly don't want to bring the entire video into renderer memory as the Cache API doesn't support Range responses yet.
      </p>
      
      <p>
        So let me show how to intercept these requests and return a customized Range response from a service worker.
      </p>
      
      <pre><code>addEventListener('fetch', event =&gt; {
  event.respondWith(loadFromCacheOrFetch(event.request));
});

function loadFromCacheOrFetch(request) {
  // Search through all available caches for this request.
  return caches.match(request)
  .then(response =&gt; {

    // Fetch from network if it's not already in the cache.
    if (!response) {
      return fetch(request);
      // Note that we may want to add the response to the cache and return
      // network response in parallel as well.
    }

    // Browser sends a HTTP Range request. Let's provide one reconstructed
    // manually from the cache.
    if (request.headers.has('range')) {
      return response.blob()
      .then(data =&gt; {

        // Get start position from Range request header.
        const pos = Number(/^bytes\=(\d+)\-/g.exec(request.headers.get('range'))[1]);
        const options = {
          status: 206,
          statusText: 'Partial Content',
          headers: response.headers
        }
        const slicedResponse = new Response(data.slice(pos), options);
        slicedResponse.setHeaders('Content-Range': 'bytes ' + pos + '-' +
            (data.size - 1) + '/' + data.size);
        slicedResponse.setHeaders('X-From-Cache': 'true');

        return slicedResponse;
      });
    }

    return response;
  }
}
</code></pre>
      
      <p>
        It is important to note that I used <code>response.blob()</code> to recreate this sliced response as this simply gives me a handle to the file (<a href="https://github.com/whatwg/fetch/issues/569">in Chrome</a>) while <code>response.arrayBuffer()</code> brings the entire file into renderer memory.
      </p>
      
      <p>
        My custom <code>X-From-Cache</code> HTTP header can be used to know whether this request came from the cache or from the network. It can be used by a player such as <a href="https://github.com/google/shaka-player/blob/master/docs/tutorials/service-worker.md">ShakaPlayer</a> to ignore the response time as an indicator of network speed.
      </p>

<div class="video-wrapper">
  <iframe class="devsite-embedded-youtube-video" data-video-id="f8EGZa32Mts"
          data-autohide="1" data-showinfo="0" frameborder="0" allowfullscreen>
  </iframe>
</div>

      
      <p>
        Have a look at the official <a href="https://github.com/GoogleChrome/sample-media-pwa">Sample Media App</a> and in particular its <a href="https://github.com/GoogleChrome/sample-media-pwa/blob/master/src/client/scripts/ranged-response.js">ranged-response.js</a> file for a complete solution for how to handle Range requests.
      </p>

<div class="clearfix"></div>

      
      <h2>
        Feedback {: #feedback }
      </h2>
      
      <p>
        {% include "web/_shared/helpful.html" %}
      </p>