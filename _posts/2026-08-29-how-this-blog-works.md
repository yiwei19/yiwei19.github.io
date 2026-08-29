---
title: "How this blog works"
description: "A starter post that doubles as a formatting reference. Delete it once you've written a real one."
---

This post exists so you can see what the blog looks like with something in it, and
so you have a formatting reference to copy from. **Delete this file once you've
written your first real post** — it lives at `_posts/2026-08-29-how-this-blog-works.md`.

## Writing a new post

Create a file in `_posts/` named `YYYY-MM-DD-some-slug.md`. The date in the filename
is what orders the blog; the `title` in the front matter is what people see. Push, wait
a minute or two, and it appears at the top of the list.

Full instructions are in `docs/09-blog.md`.

## What Markdown gives you

Regular paragraphs need no markup. *Italic* and **bold** work as you'd expect, as do
[links](https://arxiv.org/abs/2608.26076) and `inline code`.

Lists:

- A bullet
- Another bullet
- A third one

1. Numbered
2. When order matters

A blockquote, useful for pulling out a claim you want to sit with:

> The iterative nature of generative models makes them flexible and generalizable;
> however, multi-step sampling impedes the time-critical operation required in robotics.

Code blocks keep their whitespace:

```python
# average velocity on the product Lie group
u_bar = (log_map(x_1) - log_map(x_t)) / (1.0 - t)
```

Images go in `assets/` and are referenced from the site root:

```markdown
![What the picture shows](/assets/some-figure.png)
```

## What to write about

You said research notes, paper reading, and thinking out loud. A few formats that tend
to age well:

- **A bug and its diagnosis.** The hand-eye frame-convention error is exactly this kind
  of story: a number that was wrong, how you noticed, what it turned out to be.
- **A paper you read closely**, in your own words, with the part you had to work hardest
  to understand written out properly.
- **A decision you made and why**, so future-you can check whether the reasoning held.

Posts don't need to be long. A tight 400 words on one real thing beats a survey.
