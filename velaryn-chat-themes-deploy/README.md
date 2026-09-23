# Velaryn Chat Themes — deploy folder

This folder is ready for a static deployment on Cloudflare Pages.

## What to upload

Upload the **contents** of this directory to the root of a new public GitHub repository. Keep the layout unchanged:

```text
themes.json
_headers
index.html
wallpapers/
thumbs/
```

## Cloudflare Pages

1. Create a public GitHub repository, for example `velaryn-chat-themes`.
2. Upload the contents of this folder to its root and commit.
3. In Cloudflare: **Workers & Pages → Create application → Pages → Connect to Git**.
4. Select the repository. Set **Framework preset** to `None`, leave **Build command** empty, and use `/` as the output directory.
5. Deploy.

The deploy URL must serve this endpoint:

```text
https://YOUR-PROJECT.pages.dev/themes.json
```

## After deployment

Give that URL to the extension code. The extension will fetch only this small catalogue first. A full wallpaper is requested only when a user selects that theme; thumbnails and wallpapers use a long immutable browser cache.

Do not delete the original local files from the extension until the remote catalogue is connected and checked in the browser.
