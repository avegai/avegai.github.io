# avegai.com

Personal portfolio site for Alejandro Vega: music producer, mixer, sound designer and creative coder. Hosted on GitHub Pages at [avegai.com](https://avegai.com).

## Editing the site text

All the words on the homepage live in [`_data/content.yml`](_data/content.yml). There are two ways to change them:

- **Pages CMS (easiest):** go to [app.pagescms.org](https://app.pagescms.org), sign in with GitHub and pick this repo. The form is set up in [`.pages.yml`](.pages.yml), and every field has a short explanation.
- **Directly on GitHub:** edit `_data/content.yml`. Keep the indentation as it is, and keep text inside `"quotes"`.

Changes go live about a minute after you save.

From the CMS you can edit:

- page title, share title and description (browser tab, Google, link previews)
- headline, reel player (label + MP3) and client list
- menu note
- the About section (Markdown links and *italics* work)
- disciplines, each with an optional audio loop
- work entries: title, year, client, description, filter categories, link, YouTube video, audio clip and thumbnail pattern. Drag to reorder; the first one shows at the top.
- contact line, email and social links

Audio and image uploads go to `/assets`.

## How it works

There is no build setup in the repo. GitHub Pages runs Jekyll on push, with its default settings.

| Path | What it is |
| --- | --- |
| `index.html` | The homepage: layout, styles and scripts in one file. Liquid tags pull text from `site.data.content`, and the full content object is also passed to the page's JavaScript as `window.SITE`. |
| `_data/content.yml` | All homepage text and media references. |
| `.pages.yml` | Pages CMS config, which defines the editing form for `content.yml`. |
| `work/investment-app/` | A standalone case study page (plain HTML, not data-driven) with its UI sound files in `audio/`. |
| `CNAME` | Custom domain (`avegai.com`). |

## Running locally

Plain static hosting won't render the Liquid tags in `index.html`, so use Jekyll:

```sh
gem install jekyll
jekyll serve
```

Then open http://localhost:4000.

## To do

- `index.html` points to `/assets/og.jpg` for link previews. Add a real 1200×630 image there.
- Media in `content.yml` (for example `/assets/reel.mp3`) is served from `/assets`, which isn't in the repo yet. Upload the files through Pages CMS or commit them.
