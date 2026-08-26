# AGENTS.md — danamil.ru

## Project
Personal website of Артур Виноградов / Danamil.

Canonical production domain:
- https://danamil.ru

Repository:
- GitHub repository connected to Codex is the source of truth.
- Before making any change, inspect the current repository and current production site.
- Do NOT assume archived ZIP versions mentioned in old chats are newer than GitHub.
- If repository state and this file disagree, preserve the repository implementation and ask only if the difference is material.

## Owner / working style
The site owner is non-technical and prefers concrete outcomes over explanations.
When reporting changes:
- say exactly what changed;
- say which files changed;
- mention anything the owner must do manually;
- avoid long theory unless asked.

## Core design intent
The site is a dark desktop / macOS-window-style personal portfolio and archive.
Visual references / direction:
- sharyap.com-like desktop/window interaction;
- a little tema.ru-ish hypertext/archive energy;
- modern, not retro;
- minimal, authored, not template-like.

Critical rule:
**Do not visually redesign the site unless explicitly requested.**
For SEO / GEO / AEO work, prefer metadata, structured data, crawlability and machine-readable files. Do not add visible SEO copy unless the user explicitly approves it.

## Main page
Expected title / identity:
- Артур Виноградов. Danamil.
- RANEPA
- Маркетинг, брендинг, медиа, стратегии.

Primary navigation:
- 01 Работа
- 02 Заметки
- 03 Обо мне
- 04 Путешествия
- 05 Контакты

Interaction:
- navigation opens macOS-like floating windows;
- windows are draggable;
- red closes;
- yellow minimizes;
- green opens the corresponding full HTML page where applicable;
- Esc may close the top floating window;
- returning to index should not leave stale floating windows open;
- profile card is not meant to be closable with a normal red close action.

Keep interactions working with mouse and touch.
Keep windows bounded to the viewport.

## Pages

### work.html
Current intended content:
- one main 11tactical / Strike Force card;
- date: `ноябрь 2025 — н.в.`
- copy:
  `Научился делать email-рассылки, раздаточную и наружную рекламу, организовывать стенды на выставках, презентации для B2B, вертикальный контент.`
- tags may include email / B2B / content / events / Ozon.
Do not restore old placeholder side cards or giant decorative `01` block unless explicitly requested.

### notes.html
The page is intentionally visually empty for now.
Do not add visible placeholder copy.
For SEO it may remain `noindex,follow` while empty.

### about.html
Keep the current repository text as source of truth.
Important historical preferences:
- no political-views section;
- LOVE / HATE / TATTOOS / HOBBIES are personal lists;
- do not invent extra biography;
- keep typography smaller than the original oversized version.

Known intended texts from prior iteration:

BIOGRAPHY:
`Родился в Москве 20 ноября в 2007 году в роддоме на улице Новаторов.`

TATTOOS:
`Всего 8 штук (пока): сколопендра, креветка, муравей, скорпион, фрин, мухоловка, уховёртка, муха.`

HOBBIES:
`Стикербомбинг, всевозможные ремонтные работы, готовка и игры на компьютере.`

For search snippets, personal taste/tattoo/hobby lists may use `data-nosnippet`, but they must remain visible to the user.

### photo.html
Keep the current minimal photo page.
Historical heading:
`Первоначально этой страницы не должно было быть, но я её оставил.`
No extra placeholder copy.
No unnecessary macOS green/yellow controls.

### contacts.html
Expected links:
- Telegram: @danamil → https://t.me/danamil
- Instagram: @danamilll → https://instagram.com/danamilll
- VK: cuclas → https://vk.com/cuclas
- Email: artur@vinogradov.su
- Discord: danamil
- résumé download: `vinogradov_artur_resume.pdf`

Keep cards compact.

### travel.html
Travel page is interaction-sensitive. Preserve current working dimensions and behavior unless asked otherwise.

Key rules:
- modal windows must open centered in the viewport;
- they must NOT spawn at top-left;
- modal size should remain the established compact size, not full-screen / giant;
- photos use a consistent crop;
- most recently requested crop style was the old established style from the historical working HTML: `aspect-ratio: 4 / 3` + `object-fit: cover`;
- spacing between photos should be small (around 8px);
- if a trip has exactly 2 photos, center the pair;
- windows may overlap;
- maximum 6 open travel windows;
- opening a seventh closes the oldest;
- clicking / focusing an existing window should bring it to front;
- yellow minimizes;
- red closes;
- Esc closes topmost;
- mouse and touch dragging should work;
- window must stay within the viewport;
- lazy-load travel images when practical.

Known travel timeline / copy:
1. Санкт-Петербург — ноябрь 2024
   `Возможно, именно эта поездка стала причиной, почему я начал так часто ездить в Питер.`
2. Ереван — март 2025
   `Впервые был в Армении. Очень понравилось.`
3. Стамбул — июль 2025
   `Отличная остановка перед Черногорией и Сербией.`
4. Черногория: Котор, Будва, Тиват — июль 2025
   `Наверное, лучшая поездка в жизни. Полтора месяца у моря, городов и нормального ощущения свободы.`
5. Белград — август 2025
   `Очень понравились город и люди. Рекомендую.`
6. Санкт-Петербург — август 2025
   `Встретился с друзьями. Смак.`
7. Нижний Новгород — октябрь 2025
   `Недооценённый город. И очень вкусная еда.`
8. Стамбул — ноябрь 2025
   `Попал случайно. Было круто.`
9. Ереван / Гюмри — декабрь 2025
   `Прилетал на Новый год. Гюмри — хороший город.`
10. Шри-Ланка — февраль 2026
    `Грелся и научился сёрфить.`
11. Ярославль — май 2026
    `Не рекомендую. Остался без связи.`
12. Переславль-Залесский — июль 2026
    `Вайб! Несколько часов от Москвы — и есть возможность покататься на сапах, на велике и вкусно поесть.`

Pereslavl images should already exist in the latest repository. Verify rather than recreating blindly.

## Images / assets
Historical root assets include:
- `profile-photo.png`
- `vinogradov_artur_resume.pdf`
- `travel-images/`
- favicon / touch-icon / manifest assets

Travel image filenames were normalized to ASCII because non-ASCII/mojibake filenames previously broke on GitHub Pages.
Do not reintroduce Cyrillic or malformed filenames for image assets.

Optimize new travel photos sensibly:
- strip needless metadata if appropriate;
- resize to web-friendly dimensions;
- preserve good visual quality;
- avoid bloating the repository.

## Favicon
The favicon is the owner's face, derived from the profile portrait.
Expected assets may include:
- favicon.ico
- favicon-16x16.png
- favicon-32x32.png
- favicon-48x48.png
- apple-touch-icon.png
- android-chrome-192x192.png
- android-chrome-512x512.png
- site.webmanifest

Preserve them unless explicitly changing the portrait/icon.

## SEO / GEO / AEO goal
Primary identity target:
**Артур Виноградов → Danamil → маркетинг, брендинг, стратегии.**

Desired machine understanding:
- Артур Виноградов (Danamil) is a marketer;
- he works with marketing, branding, communication strategies, B2B, email marketing and content.

Important:
- never guarantee rankings or AI answers;
- never use spammy hidden body text, keyword stuffing, opacity:0 SEO paragraphs, off-screen text, etc.;
- user must not see new SEO copy unless explicitly approved;
- metadata / JSON-LD must not contradict visible site content.

Preferred canonical entity:
- `https://danamil.ru/#artur-vinogradov`

Useful structured-data concepts already explored:
- WebSite
- ProfilePage
- Person
- Occupation / hasOccupation
- Organization for 11tactical / Strike Force
- CollegeOrUniversity for РАНХиГС / RANEPA
- sameAs
- knowsAbout
- author / creator
- primaryImageOfPage

Machine-readable files may already exist:
- robots.txt
- sitemap.xml
- person.jsonld
- profile.json
- llms.txt
- llms-full.txt
- feed.xml
- site.webmanifest

Before editing SEO:
1. inspect all of these;
2. remove duplicates or contradictions rather than piling more tags on;
3. validate canonical URLs;
4. make sure `notes.html` being empty does not compete with the homepage;
5. preserve crawl access to important public pages;
6. preserve favicon discovery.

Potential official-profile URLs:
- https://t.me/danamil
- https://instagram.com/danamilll
- https://vk.com/cuclas
- https://github.com/danamilll

Do not fabricate additional profiles or third-party authority signals.

## Domain / deployment
- Production: `danamil.ru`
- historically GitHub Pages
- CNAME is important and must not be deleted accidentally.

When changing files:
- never delete `CNAME`;
- avoid deleting existing pages just to replace them;
- modify / overwrite the intended files in place;
- verify all internal links after changes.

## Quality / regression checklist
After each meaningful change:
1. inspect the actual diff;
2. check all local HTML links / asset paths;
3. make sure every expected page still exists;
4. verify no accidental giant modal sizes;
5. verify travel modal opens centered;
6. verify 2-photo trip layout centers;
7. verify 3-photo layout remains consistent;
8. verify red/yellow/green controls do what the UI suggests;
9. test mouse drag and touch/pointer drag;
10. verify at most 6 travel windows can be open;
11. check mobile layout;
12. verify favicon links resolve;
13. verify `robots.txt`, sitemap and canonical URLs;
14. do not change visual styling while doing SEO-only tasks;
15. if feasible, run a local static server and smoke-test before committing.

## Coding preferences
This is a small static site. Prefer:
- simple HTML/CSS/vanilla JS;
- no framework migration unless explicitly requested;
- minimal dependencies;
- readable code;
- no unnecessary build step.

Do not solve a small visual/interaction bug by rewriting the entire site.

## Source-of-truth rule
The latest GitHub state wins.

When Codex starts a new task:
1. inspect repository tree;
2. inspect current relevant HTML/CSS/JS;
3. inspect recent commits if useful;
4. if the task concerns production behavior, inspect `https://danamil.ru` too when network access is available;
5. make the smallest safe patch;
6. test it;
7. explain the result concisely.
