---
name: new-poem
description: Create a new empty markdown file for a poem in content/poems/. Use when the user wants to start a new poem. Takes the poem name as an argument.
---

# New Poem

Create an empty Hugo content file for a new poem.

## Input

The poem name is passed as the argument (e.g. `/new-poem My New Poem`). If no name is given, ask the user for one.

## Steps

1. Derive the filename slug from the poem name: lowercase, replace spaces with hyphens, strip any characters other than letters, numbers, and hyphens (e.g. "Forgotten Headphones" → `forgotten-headphones`).
2. Check that `content/poems/<slug>.md` does not already exist. If it does, tell the user and stop — do not overwrite it.
3. Get the current date and write the file with this frontmatter and an empty body:

```markdown
---
title: "<Poem Name>"
date: <current date in YYYY-MM-DDTHH:MM:SSZ format, UTC>
draft: true
description: ""
---
```

4. Confirm to the user that the file was created, with its path.

## Notes

- The title in the frontmatter should be the poem name as given (title case as the user typed it), not the slug.
- Leave `draft: true` so the empty poem doesn't get published; the user flips it to `false` when the poem is written.
- Do not add any placeholder body text — the body stays empty.
- Do not commit the file.
