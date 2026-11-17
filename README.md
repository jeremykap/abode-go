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
