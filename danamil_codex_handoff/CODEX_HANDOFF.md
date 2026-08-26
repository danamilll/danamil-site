# CODEX HANDOFF — danamil.ru

## Read first
Open and obey `AGENTS.md` in this repository.

This handoff comes from a long ChatGPT design/debugging session. The latest GitHub repository is the source of truth. Do not overwrite current work with an older archived version.

## Current project goal
Maintain and extend Артур Виноградов's personal site `danamil.ru`.

The site should remain visually the same unless the owner explicitly requests a visual change. Most future requests will be small edits, travel additions, interaction fixes, or technical SEO/GEO/AEO improvements.

## Most recent completed work
The latest iteration discussed in ChatGPT included:

1. Travel window behavior repaired after several regressions.
   Desired final behavior:
   - centered opening;
   - old compact window size;
   - 4:3 photo crop with `object-fit: cover`;
   - small photo gap;
   - exactly 2 photos centered;
   - windows may overlap;
   - maximum 6 simultaneously open;
   - seventh closes oldest;
   - draggable;
   - red close;
   - yellow minimize;
   - topmost / focus behavior;
   - no top-left spawn regression.

2. Added travel entry:
   - Переславль-Залесский
   - июль 2026
   - review:
     `Вайб! Несколько часов от Москвы — и есть возможность покататься на сапах, на велике и вкусно поесть.`
   - three user photos.

3. Added favicon using the owner's face.
   This should be used both by browser tabs and search engines where they choose to show it.

4. Technical SEO / GEO / AEO work was added without visible SEO text.
   Core association to strengthen:
   `Артур Виноградов → Danamil → маркетинг, брендинг, стратегии`

   Desired neutral machine-readable description:
   `Артур Виноградов (Danamil) — маркетолог, занимающийся маркетингом, брендингом, коммуникационными стратегиями, B2B-коммуникациями, email-маркетингом и контентом.`

   Expected technical pieces may include:
   - canonical metadata;
   - unique title/description;
   - Open Graph;
   - Twitter metadata;
   - JSON-LD / schema.org Person + ProfilePage + WebSite;
   - canonical person ID `https://danamil.ru/#artur-vinogradov`;
   - sameAs links;
   - sitemap.xml;
   - robots.txt;
   - person.jsonld;
   - profile.json;
   - llms.txt;
   - llms-full.txt;
   - feed.xml;
   - site.webmanifest;
   - empty notes page `noindex,follow`;
   - `data-nosnippet` may be used on personal list sections so search snippets focus on useful identity/professional content.

## First action in Codex
Before editing anything, perform a repository audit and report only material issues.

Suggested sequence:
1. inspect repository tree;
2. inspect `index.html`, `travel.html`, `about.html`, `work.html`, `contacts.html`, `notes.html`;
3. inspect `robots.txt`, `sitemap.xml`, JSON-LD/profile files and favicon/manifest;
4. inspect recent commits to understand current version;
5. confirm there are no broken internal asset links;
6. confirm the Pereslavl entry and its three images are present;
7. confirm travel modal behavior in code matches `AGENTS.md`;
8. if browser access exists, smoke-test `https://danamil.ru`.

Do not change anything during that first audit unless the user asks you to fix issues immediately.

## Important historical failure modes
Avoid repeating these:
- Uploading only `index.html` while deleting the other page files.
- Deleting `CNAME`.
- Making travel modal width enormous.
- Making travel photos natural-height / uncropped when the requested style is uniform crop.
- Opening travel modals at top-left instead of centered.
- Preventing windows from overlapping.
- Losing touch dragging.
- Allowing minimized windows to overlap in bad positions.
- Loading every large travel image eagerly.
- Non-ASCII image filenames breaking on GitHub Pages.
- Adding visible SEO paragraphs when the user asked for no visible change.
- Keyword stuffing / hidden spam text.

## How to handle future user requests
When the owner says something like:
- "добавь поездку" → edit the existing travel system, preserve window behavior and image style;
- "улучши SEO" → improve technical discoverability without visible redesign;
- "почини окно" → patch the existing implementation, do not rewrite unrelated pages;
- "сделай архив" → only if explicitly requested; otherwise commit clean source changes directly if allowed.

## Communication
The owner prefers:
- short Russian explanations;
- exact files changed;
- direct statement of what was tested;
- no long tutorials unless asked.

If a task is ambiguous but the repository itself answers the question, inspect the repository instead of asking the user to repeat information.
