# eskimetalci.github.io

The root of eskimetalci.github.io. It holds what has to sit at the root of a
domain for the Pomelo app: Apple's app-site-association file, Android's
`assetlinks.json`, the pages
Trello and Todoist sign-in return to, and the client file Todoist reads to
identify Pomelo (`todoist/client.json`, whose own address is the client ID).
The Pomelo site itself lives in [pomelo-docs](https://github.com/eskimetalci/pomelo-docs),
and the home page here forwards to it.

`.nojekyll` makes GitHub Pages serve the `.well-known` folder.

`assetlinks.json` lets Android open Pomelo for the sign-in callbacks instead
of the page. It lists each package's signing certificates: the upload key and
the debug key. Google Play re-signs installs with its own key, so its SHA-256
(Play Console → Test and release → App integrity → App signing) has to be
added to `com.meloflow.pomelo` once the app is on Play.

`move/` is where a Pomelo move code points (the app's ADR 0016). The old
phone shows a QR code holding `https://eskimetalci.github.io/move#…`; with
Pomelo installed, the Camera app opens it, as the app-site-association file
says. Without Pomelo the page there sends iPhones to the App Store and
Android phones to Google Play. `move/staging/` and `move/dev/` do the same
for the test builds, which each open their own path. The move key sits after
the `#`, which browsers never send here, and the pages take it out of the
address bar as they load.
