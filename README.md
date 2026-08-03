# The Hub

A blog hub where anyone can publish and nobody is allowed to use AI to write.

Manifesto: https://drakegriffith.github.io/drakes-website/pledge.html

**This repo holds published posts only.** Every file here is writing that a human
read and approved. Nothing pending, nothing rejected, no drafts — those live in a
private Cloudflare D1 queue and never reach git.

Served by GitHub Pages at https://drakegriffith.github.io/the-hub

## How a post gets here

1. Author signs the pledge registry, then submits plain text or Markdown through
   a form. No GitHub account required.
2. The submission lands in a private review queue.
3. A human — Drake — reads it and approves or rejects it, with a reason.
4. Approved posts get rendered to static HTML and committed here.

There is no AI detector. A person reads every post. That person's accuracy at
spotting machine-written prose is measured against a blind labelled set and
published, because an enforcement mechanism nobody can check is just a mood.

Rejected? You can appeal, and you get the reason.

## `index.html` is machine-owned once the generator ships

Hard rule. Today `index.html` is hand-made: a shell written to be the
generator's template, with the post list empty and hand commits expected. Once
the publish pipeline lands its first `publish:` commit, that file belongs to the
machine. No hand edits after that.

The reason is the failure this pipeline exists to prevent. A page that is partly
generated and partly hand-corrected drifts from the queue that is supposed to be
its only source, and then you cannot trust either copy. After that point,
changing what the front page says means changing the generator's template in
`the-hub-engine` and republishing.

`style.css` is a vendored byte-identical copy of `drakes-website/style.css`,
carrying a `/* synced from drakes-website@<sha> */` marker on the first line.
Hub-specific rules go in `hub.css`, which loads after it. Never edit the
vendored file; a drift check compares it against the live copy.

## Not here

The plumbing — submission Worker, admin dashboard, renderer, queue schema — is in
a separate private repo (`the-hub-engine`).

## Status

Intake is live: sign the pledge, confirm your email, submit a post. The publish
pipeline that turns an approved submission into a page here is not built yet, so
the post list is empty and every file in this repo is hand-made.
