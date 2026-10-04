# BalancePet Browser Bridge

Current version: 1.0.0

A local browser extension that lets BalancePet read a relay site session without anyone
copying cookies by hand. This is a separate distribution repository: the application's
online library marks it as a **browser extension** and offers only a link to the
repository, because it cannot install or load it as a feature extension.

## Using it

1. Open `edge://extensions` or `chrome://extensions` in Edge or Chrome.
2. Turn on developer mode.
3. Choose **Load unpacked** and select this directory.
4. In BalancePet, open **Advanced: read the session from this machine's browser**.
5. Click **Connect through the browser extension** and note the six-digit pairing code.
6. Switch to the tab that is already signed in to the relay site, click the extension
   icon and enter the code.
7. Click **Sync this site's session**.

- After updating the extension, reload it on the extensions page and press `Ctrl+R` on
  the relay site's usage page: the page capturer has to be installed early in the load.
- A successful sync says the page capturer is installed and lists how many usage
  responses were captured.
- Once paired, the extension syncs new usage responses to this machine every 30 seconds
  while the code stays valid, including while the settings window is closed.

- The extension asks only for cookie access to the current tab's site; where a site has
  no cookies it also tries the common web session keys in the page.
- Data goes to BalancePet on `127.0.0.1`. It does not leave the machine.
- A pairing code is valid for ten minutes, renewed on every successful sync.
- As long as the page stays signed in and the extension keeps syncing, the code does not
  need to be entered again.
- It expires after ten minutes without a successful sync -- an expired cookie, a closed
  page or a signed-out account.