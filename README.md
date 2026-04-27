# safari-userstyles

A user stylesheet for **old.reddit.com** (`old.reddit.com`, not the redesign at `www.reddit.com` / `sh.reddit.com`).

It slims down the right sidebar, hides promoted posts and the "Get new Reddit" nag, and widens the post column to fill the reclaimed space.

## What it changes

- Hides sidebar boxes: recently viewed, karma, account activity, premium/gold banners, ads, info bars.
- On aggregate pages (front / all / popular / multis), also hides the submit + create-subreddit buttons. Subreddit pages keep them.
- Shrinks the remaining sidebar to ~60% via `zoom`.
- Widens `.content` to use the freed-up space.
- Hides `.promoted` / `.promotedlink` / `.organic-listing` posts in feeds.
- Hides the redesign opt-in button in the header.

## Install (Safari)

1. Save `safari-userstyles.css` somewhere stable (e.g. `~/Library/Application Support/SafariUserStyles/`).
2. Safari → Settings → Advanced → **Style sheet** → *Other…* → pick the file.
3. Reload old.reddit.com.

Safari applies this file globally to every site. The selectors are scoped to `body.loggedin` / `body.loggedout` plus reddit-specific classes (`.side`, `.thing.promoted`, etc.), so it's effectively a no-op on other sites — but it is *not* sandboxed to reddit.com. If you visit a site that happens to use the same class names, it could match.

## Use in other browsers

The CSS itself is plain CSS and not Safari-specific. To use it elsewhere:

- **Chrome / Firefox / Edge**: install [Stylus](https://add0n.com/stylus.html), create a new style scoped to `old.reddit.com`, and paste the contents in. With proper URL scoping you can drop the `body.loggedin` / `body.loggedout` guards.

One caveat: rule #3 uses `zoom`, which is non-standard. It works in Safari and Chromium, and Firefox 126+ supports it. Older Firefox will leave the sidebar full-size — the rest of the rules still apply.
