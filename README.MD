# A simple example PWA
This project was built as part of a YouTube video on [https://www.youtube.com/watch?v=I3jTvWj8JrQ](https://www.youtube.com/watch?v=I3jTvWj8JrQ).

# Usage
Run `npm install http-server` (you need [Node.js](https://nodejs.org) for that) to install the development server which will serve the `public` folder.

Once that command finished, start the server via `npm start` and view the app at [localhost:8081](http://localhost:8081)

In this app important files are.
  1. Manifest.json which is public folder.
  2. sw.js(The service worker) in public folder
  

# Manifest file
The web app manifest is a simple JSON file that tells the browser about your web application and how it should behave when 'installed' on the user's mobile device or desktop. Having a manifest is required by Chrome to show the Add to Home Screen prompt.


Create the manifest
A complete manifest.json file for a progressive web app.
```
{
  "short_name": "Maps",
  "name": "Google Maps",
  "icons": [
    {
      "src": "/images/icons-192.png",
      "type": "image/png",
      "sizes": "192x192"
    },
    {
      "src": "/images/icons-512.png",
      "type": "image/png",
      "sizes": "512x512"
    }
  ],
  "start_url": "/maps/?source=pwa",
  "background_color": "#3367D6",
  "display": "standalone",
  "scope": "/maps/",
  "theme_color": "#3367D6"
}
```

Tell the browser about your manifest
When you have created the manifest, add a link tag to all the pages that encompass your web app:

``` <link rel="manifest" href="/manifest.json"> ```

[Read more about manifest file](https://developers.google.com/web/fundamentals/web-app-manifest/)


# Service worker
Once the service worker installed in your browser you can see it by going in 'devlopment tools -> application tab' there you will find service worker.

for installing service worker add this line of code in your main js file.

```
if (!('serviceWorker' in navigator)) {
  console.log('Service Worker not supported');
  return;
}
navigator.serviceWorker.register('/service-worker.js')
.then(function(registration) {
  console.log('SW registered! Scope is:', registration.scope);
}); // .catch a registration error
```

[service worker intro](https://docs.google.com/presentation/d/1bFVDRa71JK0ilr6lS6y9Twqp9gy8jzV1O8FFbG4A3qk/edit#slide=id.p4)

[learn more about service worker](https://codelabs.developers.google.com/codelabs/pwa-scripting-the-service-worker/index.html?index=..%2F..dev-pwa-training#0)



