# syncableStore-bundle #

bundles syncableStore, SyncedStore, yjs and several related packages into a single module that can be used in no-build environments

## Background ##

When using [Yjs](https://github.com/yjs/yjs) and depending modules in a browser (or another no-build environment, typical import statements such as

```
import * as Y                from 'yjs'
import { WebsocketProvider } from 'y-websocket'
import { YKeyValue }         from 'y-utility/y-keyvalue'
import { syncableStore }     from 'https://rozek.github.io/syncableStore/dist/syncableStore.esm.js'
```

may lead to a **completely unpredictable behaviour of Yjs**.

A brief look into the browser console will reveal one or multiple error messages starting with `Yjs was already imported. This breaks constructor checks and will lead to issues!`

As written by [dmonad](https://github.com/dmonad): this message has to be taken seriously - **Yjs will not work as expected**!

But how does it then become possible to use Yjs within a browser without having to use a build environment (which will collect all required imports and build a large package including every import only once - together with other advantages)?

One possibility is to just bundle Yjs and all packages that depend on it into one module which may then be safely imported into a script - such an approach is by no means elegant but makes Yjs usable even within no-build environments.

This is what this repo wants to provide.

It currently bundles

* Yjs
* y-indexeddb
* y-websocket
* y-webrtc
* y-keyvalue and
* y-lwwmap
* @syncedstore/core
* syncableStore

into a single monolith.



(documentation follows)
