# eskimetalci.github.io

The root of eskimetalci.github.io. It holds what has to sit at the root of a
domain for the Pomelo app: Apple's app-site-association file, the pages
Trello and Todoist sign-in return to, and the client file Todoist reads to
identify Pomelo (`todoist/client.json`, whose own address is the client ID).
The Pomelo site itself lives in [pomelo-docs](https://github.com/eskimetalci/pomelo-docs),
and the home page here forwards to it.

`.nojekyll` makes GitHub Pages serve the `.well-known` folder.
