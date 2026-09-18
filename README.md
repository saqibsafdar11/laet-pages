# laet-pages

Static pages LAET shares with staff, served by GitHub Pages from `main` at
<https://saqibsafdar11.github.io/laet-pages/>.

## The rule

**This repository is public by design.** Everything committed here is world-readable,
immediately and permanently, whatever `robots.txt` says. That is the point of it: it exists so
that shareable material never has to be served out of a private repository alongside things
that must not be.

Never commit here:

- pupil or staff personal data, names, marks, or anything identifying
- safeguarding material
- security audits, penetration test output, or vulnerability detail
- GDPR reports, DPIAs, or signed governance records
- unpublished strategy, or anything not yet seen by SLT
- credentials, keys, tokens, or internal URLs that are not already public

Those live in the private repositories, such as `laet-digital-strategy`.

## Adding a project

One folder per project, served at that path. Add a card to `index.html` pointing at it.

```
laet-pages/
  index.html              the landing page listing what is published
  robots.txt
  a-star-toolkit/
    index.html            the A* Toolkit
  dashboard/              (for example) the LAET dashboard prototype
    index.html
```

A project's folder should hold the built, self-contained page, not its source. Keep the source
and the build scripts in whichever repository owns that project, and copy the output here.

For the A* Toolkit the source of truth is `Instructional Coaching/` in the private
`laet-digital-strategy` repository. Rebuild and copy with:

```bash
python3 scripts/build_html.py sources LAET-A-star-toolkit.html
cp LAET-A-star-toolkit.html <path-to>/laet-pages/a-star-toolkit/index.html
```

## Taking something down

Delete the folder, remove its card from `index.html`, and push. The page stops serving within
a minute or so. Assume anything already fetched or cached is still out there.
