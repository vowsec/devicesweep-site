# devicesweep-site

Public web pages for **DeviceSweep (手机安检)**. Currently this holds the privacy
policy, which Google Play requires at a publicly reachable URL.

- Live: https://vowsec.github.io/devicesweep-site/privacy/
- Served by GitHub Pages from `main` (root).

## Source of truth

The page is **not authored here**. The canonical file lives in the private app
repository:

    devicesweep-android → docs/play-store/privacy-site/index.html

`privacy/index.html` in this repository is a verbatim copy of that file. Do not
edit it here — edit the original, then re-publish with:

    android/tools/publish_privacy_site.sh

The script copies the file, refuses to publish if the content is unchanged, and
pushes. Keeping one authoring location avoids the two-copies-drift problem.

## Layout

    index.html          → redirects to ./privacy/
    privacy/index.html  → the policy itself (EN + ZH on one page)
    .nojekyll           → serve files as-is; no Jekyll processing

## Notes

- No external assets: the page inlines its CSS and its brand mark, so it renders
  with no network access beyond the HTML itself.
- The same file is also embedded in the app repository's release docs, so the
  policy text and the shipped app can never disagree.
