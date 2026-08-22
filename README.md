# rotationmusic.org

The website for [Rotation](https://github.com/Jannehy/rotation), served by
GitHub Pages. Plain HTML and CSS — no build step, no dependencies.

```
index.html              the page
privacy.html            the privacy policy, linked from both app stores
style.css               the styling
CNAME                   the custom domain
assets/mark.svg         the record, drawn with currentColor so CSS can tint it
assets/favicon.svg      the same mark with the colour baked in
assets/icon.png         1024 px app icon, used as the touch icon and preview image
assets/screenshots/     the app screenshots shown in the "Apps" section
```

`assets/icon.png` is generated, not drawn by hand:

```bash
# from the rotation-ios repository
python3 Tools/make-icon.py
cp Resources/Assets.xcassets/AppIcon.appiconset/icon-1024.png \
   ../rotation-web/assets/icon.png
```

The same script rasterises the icon for all six accent colours, so the mark is
identical everywhere.

## Publishing

Settings → Pages → Source: *Deploy from a branch*, `main` / `root`. GitHub reads
`CNAME` and issues the certificate itself once the DNS records point at it:

```
A     @    185.199.108.153
A     @    185.199.109.153
A     @    185.199.110.153
A     @    185.199.111.153
CNAME www  jannehy.github.io.
```
