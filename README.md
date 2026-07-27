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

## Not here

The plumbing — submission Worker, admin dashboard, renderer, queue schema — is in
a separate private repo (`the-hub-engine`).

## Status

Not built yet.
