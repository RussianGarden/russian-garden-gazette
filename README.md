# The Russian Garden Gazette

A digital journal of the Russian Cultural Garden, Cleveland.
Published at https://gazette.russianculturalgarden.com

## How this repository is built

Every page is a **single self-contained HTML file**. Images and CSS are
embedded inside each file, so there are no folders and nothing can break
by being moved. Upload or replace files individually; nothing depends on
anything else.

    index.html          Redirects to the current issue
    issue-9-en.html     Issue #9, English
    issue-9-ru.html     Issue #9, Russian
    founders-en.html    Full text of the founders' letter, English
    founders-ru.html    Full text of the founders' letter, Russian
    issue-8.html        Issue #8 (published August 2026)
    archive.html        The Archive, English
    archive-ru.html     The Archive, Russian
    og-issue-9.jpg      Facebook/social preview image for Issue #9
    social-preview.jpg  Facebook/social preview image for Issue #8
    netlify.toml        Build settings (there is no build step)

Social preview images are the one exception: Facebook cannot read an
image embedded in a page, so those two stay as separate files.

## Where the "current issue" is defined

The bare domain redirects to the newest issue. That redirect lives in
`netlify.toml` — change the `to =` lines there and nothing else decides it.
`index.html` carries the same target as a fallback, so update it too.

`/current` and `/current-ru` are permanent shortcuts that always resolve to
the newest issue; they are safe to print or share.

## Publishing a new issue

1. Add `issue-10-en.html` and `issue-10-ru.html`.
2. Add cards for them in `archive.html` and `archive-ru.html`, and move
   the "Current issue" label.
3. Update the redirect targets in `netlify.toml` (four lines) and in `index.html`.
4. Commit with a message naming the issue. Netlify deploys within a minute.

## The rule that keeps this an archive

**Never edit a published issue file.** Each issue carries its own styling
inside itself, so a future redesign cannot change how an older issue
looks. Correcting a factual error is the exception — make that change in
its own commit so it is on the record.
