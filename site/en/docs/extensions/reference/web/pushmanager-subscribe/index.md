---
layout: "layouts/doc-post.njk"
title: "PushManager.subscribe()"
seoTitle: "PushManager.subscribe() in extensions"
date: 2023-08-28
description: Use PushManager.subscribe() in extensions.
---

The [subscribe()](https://developer.mozilla.org/docs/Web/API/PushManager/subscribe) method of the [PushManager](https://developer.mozilla.org/docs/Web/API/PushManager) interface subscribes to a push service. Refer to MDN for complete details of the [Push API](https://developer.mozilla.org/docs/Web/API/Push_API).


## Availability in extensions

The Push API is available in any Chrome extension; however, some versions have differences with standard Push API that are specific to extensions. See [Extension differences](#extension-differences) for details.

## Extension differences

You can specify a minimum Chrome version using the [`"minimum_chrome_version"`](/docs/extensions/mv3/manifest/minimum_chrome_version/) manifest key.

`userVisibleOnly` (Chrome 117 or later)
This argument to `PushManager.subscribe()` specifies whether push messages from the server must be shown to the user as a notification. Typically, this value is required to be set to `true`. When used in an extension, this argument may be `false` in Chrome 117 or later, meaning that no notification will be shown. This allows a push to be used as an alternative to WebSockets in extension service workers for asynchronous client-server communication.

## Permissions

Requires the following in the permissions field of the manifest file:

```json
"notifications"
```

Additionally, PushManager triggers a user permission flow.

## Supporting contexts

This API may be used in:

* Extension service workers

## Example

TBD