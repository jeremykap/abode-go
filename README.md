# abode-go

A one-page redirect for the Daily Dashboard in
[jeremykap/abode](https://github.com/jeremykap/abode). The dashboard runs in a sandboxed page that
can't open app links directly, so it links here instead:

```
https://jeremykap.github.io/abode-go/#<encodeURIComponent(target)>
```

`index.html` decodes the part after `#` and sends the browser on to it. Only `obsidian:` and
`message:` (Apple Mail) targets are allowed. The target stays in the `#` fragment, which browsers
never send to the server, so note paths and email IDs don't reach GitHub's logs. The page holds no
data of its own.

Hosted with GitHub Pages: Settings → Pages → Deploy from a branch → `main`, `/ (root)`.

## Home-screen launcher

`dashboard/` is a launcher for the dashboard with its own icon (the claude.ai page can't set one).
Open `https://jeremykap.github.io/abode-go/dashboard/?add#<artifact id>` on the iPhone, tap Share → Add to Home
Screen, and turn off "Open as Web App" so it opens in Safari, where claude.ai is signed in. The
shortcut saves `/dashboard/#<artifact id>`, which goes straight on to
`https://claude.ai/artifact/<artifact id>`. Like the redirect above, the id stays in the `#`
fragment, so it isn't in this repo or GitHub's logs.

The icon's source is `dashboard/icon.svg`. The PNGs (180 apple-touch, 192, 512, 512 maskable) are
rendered from it with no transparency. iOS caches home-screen icons, so after changing the icon,
delete the shortcut and add it again.
