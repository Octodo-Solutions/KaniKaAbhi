# Kanika & Abhishek · Wedding Invitation (#KanikAbhi)

A single-page digital invitation for the wedding celebrations on 17th & 18th November 2026 in Jaipur, ready for GitHub Pages. No build step and nothing to install: it's plain HTML, images and one music file.

## What's in the folder

```
index.html          the invitation
guest-links.html    makes personalised links ("Dear Sharma Family,") for each guest
404.html            sends mistyped addresses back to the invitation
favicon.ico         browser-tab icon (the KA seal)
robots.txt          asks search engines not to list the site
.nojekyll           tells GitHub Pages to serve files exactly as they are
assets/             illustrations, photos, song.mp3, link-preview image, app icons
```

## Deploy on GitHub Pages (about 5 minutes, all in the browser)

1. Sign in at github.com, click **+ → New repository**.
   Name it something short, e.g. `kanikabhi`. Choose **Public** (free GitHub Pages needs a public repo). Click **Create repository**.
2. On the new repo page, click **uploading an existing file**.
   Unzip the download first, then drag **everything inside** the `kanikabhi-site` folder (not the folder itself) into the upload box, including the `assets` folder.
   *Note:* `.nojekyll` is a hidden file. If your computer hides it, it's fine to skip it; the site works without it.
3. Click **Commit changes**.
4. Go to **Settings → Pages**. Under *Build and deployment*, set **Source: Deploy from a branch**, **Branch: main**, folder **/ (root)**, then **Save**.
5. Wait 1–2 minutes and refresh that page. Your link appears at the top, e.g.
   `https://YOUR-USERNAME.github.io/kanikabhi/`

### Prefer the command line?

```bash
cd kanikabhi-site
git init && git add . && git commit -m "Wedding invitation"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/kanikabhi.git
git push -u origin main
```
Then do step 4 above.

## One edit after it's live: the WhatsApp preview

WhatsApp and Facebook only show the photo card when the preview image uses the full web address. Open `index.html` on GitHub (pencil icon to edit) and replace **both** `SITE_URL` placeholders near the top with your live link, keeping the trailing slash:

```html
<meta property="og:url" content="https://YOUR-USERNAME.github.io/kanikabhi/">
<meta property="og:image" content="https://YOUR-USERNAME.github.io/kanikabhi/assets/og-image.jpg">
```

Commit, wait a minute, and the link will show the couple's photo, names and dates when pasted into WhatsApp.
(If WhatsApp cached an older preview, add `?v=2` to the end of the link the first time you share it.)

## Personalised invitations

Add `?to=` and the guest's name to the link:

```
https://YOUR-USERNAME.github.io/kanikabhi/?to=Sharma%20Family
https://YOUR-USERNAME.github.io/kanikabhi/#Sharma_Family     (also works; underscores become spaces)
```

The envelope then reads *Dear Sharma Family,* and that guest's WhatsApp RSVP message mentions their name.

Easiest way: open `https://YOUR-USERNAME.github.io/kanikabhi/guest-links.html`, paste one name per line, and each guest gets a **Copy link** and a **Send on WhatsApp** button. The names list is remembered only in your own browser.

Other handy link:

- `.../kanikabhi/#invite` skips the envelope and opens straight to the invitation (good for re-visits).

## Making changes

- **Text, times, names, phone numbers:** edit `index.html` directly on GitHub. Everything is plain text in the page.
- **Countdown target:** search for `2026-11-17T12:00:00+05:30` in `index.html`.
- **Calendar buttons:** search for `calLink(` in `index.html` (times there are in UTC; IST is UTC + 5:30).
- **Music:** replace `assets/song.mp3` with another MP3 of the same name. Keep it small (under 1 MB) so it loads quickly on mobile data.
- **Photos:** replace `assets/avatar.webp` (arch portrait) or `assets/jhoola.webp` (closing photo) with same-named files.

Changes go live about a minute after each commit.

## Custom domain (optional)

To use something like `kanikabhi.in`: buy the domain, then in **Settings → Pages → Custom domain** enter it and follow GitHub's DNS instructions. Update the two `SITE_URL` lines to the new address.

## Privacy note

The site is public to anyone who has the link (it includes RSVP phone numbers). It is marked so search engines don't index it, and nobody can find it unless the link is shared with them.
