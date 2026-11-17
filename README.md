# marconieddu.net

Personal academic website, built with [Hugo](https://gohugo.io) (version 0.169.0) and published on GitHub Pages. No external theme: the layout lives in `layouts/` and the styling in `assets/css/main.css`.

## Where things are

| To change | Edit |
|---|---|
| Bio paragraphs on the home page | `content/_index.md` |
| Text at the top of the Research page | `content/research.md` |
| Papers (published, working, in progress) | `data/papers.yaml` |
| Coauthor links | `data/coauthors.yaml` (any name listed here is linked automatically) |
| News | `data/news.yaml` (newest first; home page shows five) |
| Bio page: positions, education, other things | `data/bio.yaml` |
| Teaching page: intro text / courses | `content/teaching.md` / `data/teaching.yaml` |
| Workshops page | `content/workshops.md` |
| Profile links, contact details, menu | `hugo.toml` |

## Before publishing

1. **Photo:** save it as `static/img/photo.jpg` (portrait, about 600×725 px). The home page shows it automatically once the file exists.
2. **CV:** save it as `static/files/cv.pdf`. Until then the CV links point to the old Wix file, which stops working when the Wix plan ends.
3. **Abstracts:** each paper in `data/papers.yaml` has an empty `abstract: ""` field. Paste the text between the quotes; an "Abstract" toggle appears for every paper that has one.

## Add a paper

Copy an existing entry in `data/papers.yaml` and edit the fields. Only `title` is required; the comment at the top of the file lists the others.

## Preview on your computer

```
hugo server
```

then open http://localhost:1313. Install Hugo first (`brew install hugo` on a Mac).

## Publish on GitHub Pages

1. Create a GitHub repository (it must be public on the free plan) and push this folder to its `main` branch.
2. In the repository: **Settings → Pages → Build and deployment → Source: GitHub Actions**. The workflow in `.github/workflows/hugo.yml` builds and publishes the site on every push.
3. **Settings → Pages → Custom domain:** enter `www.marconieddu.net` and save. Tick **Enforce HTTPS** once it becomes available (can take up to 24 hours).
4. At your domain registrar, set these DNS records:
   - `A` records for `marconieddu.net` → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `CNAME` record for `www` → `<your-github-username>.github.io`

   GitHub then redirects `marconieddu.net` to `www.marconieddu.net`. DNS changes can take up to 24 hours.
5. Once the new site is live at your domain, cancel the Wix plan.

## Fonts

Instrument Serif is self-hosted from `static/fonts/` under the SIL Open Font License (`static/fonts/OFL-LICENSE.txt`), so the site makes no requests to Google. It has one weight (regular and italic), so the site uses no bold.
