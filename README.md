# EACC Website

Static HTML website for the Egyptian American Center / Egyptian American Cultural Center.

The project currently uses plain HTML pages with embedded CSS and embedded JavaScript. There is no build tool, package manager, framework, or shared external site script. Translation and page behavior are kept inside the HTML files.

## Current Structure

```text
create eacc website/
|
|-- index.html
|-- contactus.html
|-- README.md
|
|-- aboutus/
|   |-- who-we-are.html
|   |-- explore-our-camps.html        # empty placeholder
|   `-- faqs.html
|
|-- programs/
|   |-- summer-camp-2026.html         # custom MyVoice page, keep separate
|   |-- language.html
|   |-- activities.html
|   |-- english.html
|   |-- english-adults.html
|   |
|   `-- english/
|       |-- english.html
|       |-- adults/
|       |   `-- adults.html
|       |-- kids/
|       |   `-- kids.html
|       `-- youth/
|           `-- youth.html
|
`-- assets/
    |-- css/                          # currently empty
    |-- icons/                        # currently empty
    |-- js/                           # currently empty
    |-- videos/                       # currently empty
    |
    `-- images/
        |-- logo.png
        |-- logo-white.png
        |-- logo-crop.png
        |-- hero.png
        |-- hero2.avif
        |-- hero 3.avif
        |-- hero 4.avif
        |-- english.avif
        |-- english-hero.jpg
        |-- languages.png
        |-- adults.avif
        |-- adult-eng.jpg
        |-- Youth.avif
        |-- youth1.avif
        |-- youth2.avif
        |-- kids.avif
        |-- classroom.avif
        |-- private.avif
        |-- private course.avif
        |-- online.avif
        |-- contactus.avif
        |-- whoweare.avif
        |-- german.avif
        |-- french.avif
        |-- italian.avif
        |-- spanish.avif
        |-- ielts.avif
        |-- toefl.avif
        |-- oet.avif
        |-- pte.avif
        |-- arts.avif
        |-- music.avif
        |-- Young Ballerinas.avif
        |-- summer-camp.avif
        |-- summer-winter-camp.png
        |-- vangoh.jpg
        |-- 455890287_504292025516180_5487804810708685496_n.avif
        |
        `-- kids/
            |-- 4182503 (1).avif
            |-- 44736_edited.avif
            |-- Kid Painting.avif
            |-- Kids in Playground.avif
            |-- Kids Play.avif
            |-- kids-english-program.png
            `-- youth-english-program.png
```

## Active Pages

### `index.html`

Main homepage. Includes:

- Original loading screen.
- Hero image slider.
- Main EACC navigation.
- Programs overview.
- Language, preparation, activities, study modes, camps, and apply sections.
- Footer matching the inner pages.
- Embedded AR/EN toggle.
- Embedded site consistency style layer.

Important section anchors:

```text
#programs
#test-prep
#activities
#apply
```

### `contactus.html`

Standalone contact page. Includes:

- Contact hero.
- Request information form.
- Contact cards.
- Google Maps address section.
- Matching footer.
- Embedded AR/EN toggle.
- Embedded site consistency style layer.

### `aboutus/who-we-are.html`

Active About page. Includes:

- EACC identity content.
- Mission and vision sections.
- CTA and footer.
- Embedded AR/EN toggle.
- Embedded site consistency style layer.

### `aboutus/explore-our-camps.html`

Empty placeholder. It is linked from About navigation and footer but has no page content yet.

### `aboutus/faqs.html`

Active FAQ page. Includes:

- Hero using `whoweare.avif`.
- Searchable FAQ experience.
- TOEFL iBT category with 17 questions and answers.
- IELTS, PTE, and OET category tabs prepared as coming-soon panels.
- TOEFL/IELTS score comparison table.
- Embedded AR/EN toggle.
- Responsive accordion UI.

### `programs/language.html`

Language programs overview. Includes:

- English, German, French, Italian, and Spanish program cards.
- Contact/admissions routing for language paths that do not have individual pages yet.
- Embedded AR/EN toggle.
- Embedded site consistency style layer.

### `programs/activities.html`

Activities program overview. Current focus:

- Fine Arts.
- Creative activity family content.
- Embedded AR/EN toggle.
- Embedded site consistency style layer.

### `programs/english.html`

English program routing page. Shows:

- Adults English.
- Youth English.
- Kids English.
- Embedded AR/EN toggle.
- Embedded site consistency style layer.

### `programs/english-adults.html`

Older adults English distribution page. Shows:

- General English.
- Conversational English.
- Embedded AR/EN toggle.
- Embedded site consistency style layer.

### `programs/english/english.html`

English path page inside the nested English folder. Keep this in sync with the English program structure when possible.

### `programs/english/adults/adults.html`

Current adults English detail page. Includes:

- General English.
- Conversational English.
- Private one-to-one content.
- Embedded AR/EN toggle.
- Embedded site consistency style layer.

### `programs/english/kids/kids.html`

Kids English detail page. Includes:

- Kids learning structure.
- Summer and winter camp references.
- Placement and learning system content.
- Embedded AR/EN toggle.
- Embedded site consistency style layer.

### `programs/english/youth/youth.html`

Youth English detail page. Includes:

- Youth English course content.
- Age-aware learning and practical communication content.
- Embedded AR/EN toggle.
- Embedded site consistency style layer.

### `programs/summer-camp-2026.html`

Custom MyVoice Summer Camp 2026 page.

Important rule: keep this page separate from the shared design consistency layer. It has its own custom layout, navigation, language switcher, page scripts, and campaign styling.

Current status:

- Uses its own embedded CSS and JavaScript.
- Uses its own EN/AR language controls.
- Has restored UTF-8 symbols, Arabic text, and emoji icons.
- Does not include `eacc-design-consistency`.
- Should not receive the shared page styling unless explicitly requested.

## Navigation Rules

The main site navigation should keep this structure:

```text
Home
About Us
  - Who We Are
  - Explore Our Camps
  - FAQs
Programs
  - Summer Camp 2026
  - Languages
  - Activities
Preparation Courses
Contact
AR/EN toggle
Apply Now
```

Activities should stay inside the Programs dropdown. Do not add Activities as a separate top-level navbar link.

## Translation System

All active standard pages have an embedded AR/EN toggle:

```html
<button class="language-toggle eacc-language-toggle">...</button>
```

The translation logic is embedded in each HTML page inside:

```html
<script id="eacc-arabic-toggle-script">
```

The styling is embedded in each HTML page inside:

```html
<style id="eacc-arabic-toggle-style">
```

There are no external translation files. Do not create `language-toggle.js`, `language-toggle.css`, or a shared translation folder unless the project direction changes.

Summer Camp 2026 is the exception. It uses its own embedded language system based on `data-en`, `data-ar`, and `setLang(...)`.

## Shared Design Consistency

Standard active pages include:

```html
<style id="eacc-design-consistency">
```

This embedded style layer keeps the standard pages aligned on:

- EACC navy and gold palette.
- Container widths.
- Mobile spacing.
- Card radius and shadows.
- CTA button styling.
- Footer structure.
- Responsive behavior.

Summer Camp 2026 intentionally does not include this layer.

## Brand Colors

Main EACC colors:

```css
--navy: #1a237e;
--navy-dark: #0d1457;
--navy-mid: #283593;
--gold: #f5a623;
--gold-light: #ffd54f;
--white: #ffffff;
--off-white: #f8f9ff;
--gray-light: #eef0f8;
--gray: #9096b0;
--text: #1a1d2e;
```

Use navy for trust and structure. Use gold for CTAs, highlights, and key actions. Avoid introducing unrelated dominant colors on standard pages.

## Typography

Primary fonts:

```text
Headings: Playfair Display
Body/UI: DM Sans
```

Use large Playfair headings for hero and section titles. Keep card headings smaller and controlled so text does not overflow on mobile.

## Footer

Standard pages should use the same footer shape:

```text
Brand/about column
About EACC links
Programs links
Contact links
Copyright row
```

The homepage footer has already been adjusted to match the other standard pages.

Summer Camp 2026 has its own campaign footer and should remain separate.

## Image Rules

Use assets from:

```text
assets/images/
```

Relative path examples:

```html
<!-- from index.html -->
assets/images/logo-white.png

<!-- from aboutus/who-we-are.html or programs/language.html -->
../assets/images/logo-white.png

<!-- from programs/english/adults/adults.html -->
../../../assets/images/logo-white.png
```

Image guidance:

- Use `logo-white.png` on dark/navy backgrounds.
- Use `logo.png` on light backgrounds.
- Use `logo-crop.png` for the favicon.
- Use `.avif` image assets for cards where available.
- Use responsive images with `max-width: 100%`.
- Keep important subjects visible on both desktop and mobile.

## Inline Scripts

Current JavaScript features are embedded per page:

- Loader fade out.
- Scroll-based navbar state.
- Mobile menu toggle.
- Homepage hero slider.
- AR/EN translation on standard pages.
- Custom Summer Camp interactions on the Summer Camp page.

There is currently no shared JavaScript file in `assets/js/`.

## External Dependencies

The site uses CDN resources:

```text
Google Fonts
Font Awesome on some standard pages
```

Internet access is required for those remote fonts/icons to load. If offline support is needed later, self-host them in `assets/`.

## Quality Checklist

Before finishing any page, check:

- Correct title and meta description.
- Correct favicon path.
- Loader appears and fades.
- Navbar links use the right relative paths.
- Programs dropdown keeps Activities inside Programs.
- AR/EN toggle is present on standard active pages.
- Summer Camp keeps its own language system and custom design.
- Images load on desktop and mobile.
- Text does not stick to the screen edge on mobile.
- Cards stack cleanly on mobile.
- Footer matches the standard pages, except Summer Camp.
- No mojibake text such as `ðŸ`, `Ø`, `Ù`, `Â`, or `â` appears visibly.

## Current Contact Information

```text
Phone: +20106 553 3240
Email: info_eacc@eacc-egy.com
Location: Alexandria, Egypt
```

Long address currently used:

```text
117 Ahmed Shawqi, Mustafa Kamel WA Bolkli,
Sidi Gaber, Alexandria Governorate 5433141
```

## Future Work

Good next steps:

- Build `aboutus/explore-our-camps.html`.
- Decide whether to keep both `programs/english-adults.html` and `programs/english/adults/adults.html`, or consolidate.
- Create individual language pages for German, French, Italian, and Spanish.
- Create individual preparation course pages for IELTS, TOEFL, OET, and PTE.
- Create more activity detail pages if needed.
- Consider moving repeated standard-page CSS and JS into shared files only if the no-external-files requirement changes.
