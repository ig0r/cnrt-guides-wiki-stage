# cnrt-guides-wiki-stage

Staging build of the CP Tech **guides** wiki — cross-guide concept pages synthesized from the
National CP Tech Center / FHWA concrete-pavement guide corpus.

Live: https://ig0r.github.io/cnrt-guides-wiki-stage/

| Page | What it is |
|---|---|
| `concrete-overlay-v2.1.html` | Practitioner framing — role-based entry points, a six-step selection path, a release-to-placement hold-point checklist. |
| `concrete-overlays-v3.html` | Full-corpus synthesis — design values carrying the guide page they come from, cross-guide disagreements, the PennDOT Pub. 242 eligibility layer. |
| `concrete-overlays-v4.html` | The merge of the two, over one IEEE reference list of 29 sources. |

Three drafting approaches to the same subject, kept side by side to compare what a wiki page
adds over the guides themselves.

## How this repo is produced

Generated; do not hand-edit the HTML. In the `wiki-brainstorm` working copy:

```
python3 brainstorm/claude/_tools/md2wiki_html.py     # markdown -> brainstorm/claude/html/
python3 brainstorm/claude/_tools/deploy_pages.py     # html/ -> this directory
```

`deploy_pages.py` is independent of the page builder. It stages already-built HTML and rewrites
only what a local build cannot know: it drops sidebar entries for pages this site does not ship,
turns links into the local guide corpus into muted text, and generates `index.html`. It replaces
only the files it manages — `.git` and this README are left alone.

## Sources

The guide extractions behind these pages are **not republished here** — they are third-party
documents totalling roughly a gigabyte. Reference entries name the extraction each claim was read
from, in muted text, so it can be traced in the working copy.

Citations are IEEE-numbered. `[1, p. 44]` is the *printed* page of the cited guide; `[3, §12.2.C.2]`
is a section of PennDOT Publication 242.

Draft status: nothing here substitutes for a project-specific pavement design or the governing
agency specification.
