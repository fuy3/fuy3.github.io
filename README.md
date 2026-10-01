# fuy3.github.io

Source of my personal academic website, **[fuy3.github.io](https://fuy3.github.io)**. It covers my research, publications, projects and experience.

The site is hand-written HTML, CSS and vanilla JavaScript, with no framework, build step or runtime dependencies. GitHub Pages serves the repository as it is.

## Highlights

- **Interactive experience timeline.** Roles are kept as a small data array and laid out at runtime on a scrollable time axis. Lanes separate education, research and industry. Roles that overlap in time are packed into rows, and roles that only touch sit side by side. The timeline opens at the most recent year, and selecting a bar shows its details in a live region. On narrow screens it switches to an accessible list.
- **Research-theme filter.** Selecting a theme highlights the matching projects. It also regroups the publication list under the selected theme, animated with the FLIP technique. A second filter separates academic from industry projects.
- **Responsive and themed.** Colours are defined as CSS custom properties, with a light and a dark theme that follow `prefers-color-scheme`. Animations respect `prefers-reduced-motion`. The layout is tested from 375 px to desktop widths without horizontal scrolling.
- **Accessible controls.** Filters are real buttons with `aria-pressed`. Images have descriptive `alt` text, and the timeline detail panel is announced with `aria-live`.
- **Performance:**
  - Images are resized to at most 1600 px and stored as progressive JPEGs with metadata removed.
  - Off-screen images load lazily.
  - The YouTube player on the PerceptEEG page loads only on click. It sets an explicit referrer policy, which avoids YouTube's embed error 153.
- **SEO.** Each page has Open Graph metadata, the homepage has `Person` structured data (JSON-LD), and the site ships `sitemap.xml` and `robots.txt`.
- **Privacy:**
  - Visits are counted with [GoatCounter](https://www.goatcounter.com), with no cookies.
  - The email address is assembled in script rather than written in the page.
  - Other people's names in event screenshots are blurred, and personal identifiers are removed from published documents.

## Structure

```
index.html          homepage: news, experience timeline, research themes, publications, projects
perceptEEG.html     project page for the PerceptEEG MSc dissertation
embroidery.html     project page for diffusion-based embroidery pattern design
activities.html     service, outreach and photo gallery
images/             figures and photos (optimised)
papers/             PDFs linked from the site
sitemap.xml, robots.txt, .nojekyll
```

## Run locally

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

Opening the files directly also works. The one difference is that the YouTube video then opens on youtube.com instead of playing inline, because YouTube needs a referrer that a `file://` page cannot send.

## Deployment

Pushing to `main` publishes the site through GitHub Pages (Settings → Pages → Deploy from a branch → `main`, `/ (root)`).

## Licence

The text, images and papers are © Yiming Fu, all rights reserved. Please ask before reusing them.
