# jira-markdown-link
A simple extension to copy a link to the currently open JIRA ticket as formatted markdown.

[Available on the Chrome Web Store](https://chrome.google.com/webstore/detail/copy-jira-issue-link-as-m/ddodimdmkjejnaknifbdadmkefibglco)

For example: `[[TEST-3301]](https://mycompany.atlassian.net/browse/TEST-3301) My test ticket`

## Publishing
1. `zip jira-markdown-link.zip logo/* background.js manifest.json LICENSE`
2. Upload at [Developer Dashboard](https://chrome.google.com/webstore/devconsole)

## Local dev
1. Go to `chrome://extensions/`
2. Toggle developer mode
3. Load unpacked extension and select this repository
4. Upon making changes, go to `chrome://extensions/` and reload,

## How does it work?
The extension registers a service worker that runs on `*://*.atlassian.net/browse/*` websites. When upon clicking the extension action button in the top right, the extension injects a function to retrieve `document.title` and `document.url`, manipulate them into a markdown string, and store them in the clipboard.
