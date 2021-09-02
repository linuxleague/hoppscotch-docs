---
title: RestAPI platform
description: "Rest Editor "
position: 2

category: Getting started
---

<alert type="success">

This documentation is a work in progress!

</alert>

<video loop playsinline controls>
  <source src="/api/APIvid.webm" type="video/webm" />
  <source src="/api/APIvid.mp4" type="video/mp4" />
</video>
You can make API requests and examine responses using Hoppscotch.
An API request allows you to retrieve or send data to and from an API endpoint.

The common http methods used in API requests are:

- `GET` : Retrieve information about the REST API resource
- `POST` : Create a REST API resource
- `PUT` : Update a REST API resource
- `DELETE` : Delete a REST API resource or related component

Other methods like `HEAD`,`CONNECT`, `OPTIONS`,`TRACE`,`PATCH`and other `CUSTOM`methods can also be used.
Lets go over the features offered by Hoppscotch API platoform:

## How to Use

---

### Choosing Method:

<img src="/api/method-dark.png" class="dark-img" height="1280" width="640" alt=""/>
<img src="/api/method-light.png" class="light-img" height="1280" width="640" alt=""/>

### Collections

#### Adding requests to collections

Click on the save button ,next to `SEND` ,name your request and add to existing or new collections

<img src="/api/nameRequest-light.png" class="light-img" height="1280" width="640" alt=""/>
<img src="/api/nameRequest-dark.png" class="dark-img" height="1280" width="640" alt=""/>

You can add your requests to collections folders or subfolders.

### Adding dynamic behavior to requests:

<img src="/api/dynamic-light.png" class="light-img" height="1280" width="640" alt=""/>
<img src="/api/dynamic-dark.png" class="dark-img" height="1280" width="640" alt=""/>

The editor allows you to add dynamic behaviour to requests and collections.This lets you add `parameters` , `Headers` , `Authentication` , build `pre-request scripts` and write `tests`.
_See Also :_ <nuxt-link to='/quickstart/scripts'> Writing pre-request Scripts( quick start guide) </nuxt-link>
<nuxt-link to='/quickstart/tests'> Writing Tests(quick start guide) </nuxt-link>

### Response body :

<img src="/api/response-dark.png" class="dark-img" height="1280" width="640" alt=""/>
<img src="/api/response-light.png" class="light-img" height="1280" width="640" alt=""/>

The response from the `API endpoint` can be viewed here. You can download or copy the response for further use.

_See Also :_ <nuxt-link to='/quickstart/rest#environment-variables'> Using Environments (quick start guide) </nuxt-link>

## Keyboard shortcuts

**Optimized for efficiency.**

<p>

| Shortcut                       | Action                 |
| ------------------------------ | ---------------------- |
| <kbd>Ctrl</kbd> + <kbd>G</kbd> | Send/Cancel Request    |
| <kbd>Ctrl</kbd> + <kbd>S</kbd> | Save to Collections    |
| <kbd>Ctrl</kbd> + <kbd>K</kbd> | Copy Request Link      |
| <kbd>Ctrl</kbd> + <kbd>I</kbd> | Reset Request          |
| <kbd>Alt</kbd> + <kbd>🠋</kbd>  | Select Next method     |
| <kbd>Alt</kbd> + <kbd>🠉</kbd>  | Select Previous method |
| <kbd>Alt</kbd> + <kbd>G</kbd>  | Select `GET` method    |
| <kbd>Alt</kbd> + <kbd>H</kbd>  | Select `HEAD` method   |
| <kbd>Alt</kbd> + <kbd>P</kbd>  | Select `POST` method   |
| <kbd>Alt</kbd> + <kbd>U</kbd>  | Select `PUT` method    |
| <kbd>Alt</kbd> + <kbd>X</kbd>  | Select `DELETE` method |

</p>

## TroubleShooting

<alert type="warning">

TroubleShooting Guide needs review

</alert>

# Removing CORS restrictions

#### What is CORS?

`CORS` or Cross-Origin Resource Sharing is a security mechanism built into modern web-browers.
It may cause the following error when testing local `API endpoints` or some other API endpoints with Hoppscotch.

<img src="/api/CORS error example.png"   alt=""/>

This is Due to the API not sending the proper API headers( `Access-Control-Allow`). This issue can be solved in two ways.

1.  Ask whoever manages the API to add CORS support.
2.  Use Middleware like ProxyScotch or the [Hoppscotch Web Extension.](https://chrome.google.com/webstore/detail/hoppscotch-browser-extens/amknoiejhlmhancpahfcfcfhllgkpbld?hl=en)

### Interceptor

Hoppscotch has in-house Porxy server ProxyScotch built to handle this.

#### How it works

<img src="/api/ProxyScotch-light.png" class="light-img"  alt=""/>

<img src="/api/ProxyScotch-dark.png" class="dark-img"  alt=""/>

Enable it in settings.

<img src="/api/proxy-light.png" class="light-img" height="1280" width="640" alt=""/>

<img src="/api/proxy-dark.png" class="dark-img" height="1280" width="640" alt=""/>

You can replace this with your own proxy middleware if you wish.

#### Using Middle ware

Since `CORS` is as simple as adding some HTTP headers, and it’s the only browser blocked, then you can build some proxy-like component that will basically make a call for you, get the response from the desired API, add those headers on top, and then send it back to Hoppscotch.

_See Also :_ <a href="https://github.com/hoppscotch/hoppscotch/wiki/Proxy">ProxyScotch GitHub Wiki</a>

### Hoppscotch Web Extension

1. Download the Hoppscotch WebExtension [here.](https://chrome.google.com/webstore/detail/hoppscotch-browser-extens/amknoiejhlmhancpahfcfcfhllgkpbld?hl=en)

2. Enable it in Settings.

3. Open the extension and add new origins
   <img src="/api/Extension.png"  height="400" width="300" halt=""/>

Hoppscotch extension routes all added origins to PorxyScotch.