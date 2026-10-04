# Final DS

A design system extracted from the Figma file **`2026 Design system_Final.fig`** (page `Page-1`, 2,207 nodes, 47 component families). The file was attached to this project as a virtual filesystem; there is no public link, no repository and no codebase behind it. Everything here — every hex value, radius, gap and type size — was read out of that file, not from memory of any published system.

## What the file contains

Two distinct surfaces live in one document:

1. **A travel booking product** — a large component library (headers, seat maps, ticket offers, hotel packages, checkout fields, badges, ~40 icons) drawn at a **1440 px** desktop width in **Averta**. The Figma layer names call these "Ticketmaster Travel" components. They are reproduced here verbatim as the file authored them; the marks and lockups (`TicketmasterBrandMark`, `TicketmasterTravelLogos`, `Logos`) are copied from the file, and they remain the property of their owner — treat them as reference material for recreating this product, not as a brand you may re-use elsewhere.
2. **A designer portfolio site** — the frame `hero page 1-1` (node `1:1706`), 1920 px wide with a 1260 px content column, in **Space Grotesk / IBM Plex Sans / Inter / Instrument Sans**, signed "Seora Lee". This is the case-study wrapper around the product work.

Both are first-class here: the tokens carry both palettes, and `[data-theme="portfolio"]` flips the semantic aliases from the product surface to the portfolio surface.

## Sources

- Figma: `2026 Design system_Final.fig`, mounted read-only. Page `Page-1`; frames `hero page 1-1` (`1:1706`), `CTA` (`5:5558`), `Navi` (`5:1950`). Component definitions live off-canvas and were extracted by name.
- No GitHub repo, no local codebase, no slide deck, no brand guidelines document was provided.
- The file declares **no Figma Variables and no text styles** — so there are no token or typography collections to import. Every token in `tokens/` was derived by measuring the components themselves.

---

## Content fundamentals

**Product copy (booking flow)** is flat, transactional and sentence-cased. Labels are verbs or nouns, never slogans: "Apply", "Next", "Continue to checkout", "Select a package to see details", "or from $42/mo". Badges name a fact — "Top hotel", "Preferred partner", "Exclusive deal", "Promo code applied". Second person is implied rather than stated; the UI rarely says "you" and never says "we". No exclamation marks, no emoji, no marketing adjectives. Numbers do the persuading: percentages, prices, night counts.

**Portfolio copy** is first person, warm, and slightly informal — it is the one place the file allows personality:

> "Hello there  I'm Seora Lee. A curious seeker crafting human-oriented experiences with a strong focus on research and storytelling."

> "How It Would Feel Like Working With Me?"

> "@ 2026 Seora Lee. Designed with pixels, passion, and plenty of coffee. ☕✨"

Notes on the file's own conventions, preserved as authored: section headings are Title Case ("Selected Work", "Side Project"); the double space after "Hello there" is in the source; the footer is the only place emoji appear (☕✨) and the copyright uses `@` rather than `©`. Case-study cards pair a short kicker (the client or workstream) with a one-line outcome sentence, then three hard metrics, then three skill tags. Metrics are always `value + label`, e.g. `10% / Conversion Rate`.

**Rules of thumb.** Product: name the thing, state the number, stop. Portfolio: one sentence of voice, then evidence. Do not write copy in the product voice for the portfolio, or vice versa.

---

## Visual foundations

**Colour.** The product surface is white-on-white with an ink-black text colour (`#121212`) and a single accent hue — blue, from `#EBF2FF` tint through `#024DDF` (primary) to `#002DA1`. Greys do the structural work (`#E3E3E3` hairlines, `#646464` secondary text, `#F6F6F6` sunken panels). Status colours are conventional and used sparingly: green `#01A465`, red `#EB0000`, amber `#FFB932`. A handful of low-frequency accents appear on seat-map categories (`#A733FF`, `#C56BFF`, `#904EBA`) and one coral (`#EB5545`); the acid yellow `#FBFF2C` appears once as a highlight. The portfolio surface is warm grey paper `#F5F5F5`, ink `#2E2E2E`, hairline `#D0D0D0`, muted `#686868`, with a slate navy `#34465E` for every interactive element and `#243245` as its hover. Never more than one accent hue per screen.

**Type.** Five faces, each with one job. Averta 400/600 for all product UI (14 px is the base; 12 px for meta, 16 px for buttons, 24 px for page titles). Space Grotesk 700/500 for portfolio headings (32 px section, 24 px card kicker). IBM Plex Sans 400 for portfolio long-form (24 px intro, 18 px footer). Inter 400/500 for portfolio interface text (20/16/14). Instrument Sans 700 for the wordmark (47.5 px) and 600 for the closing question (32 px). Line-height is `100%` almost everywhere — this system sets tight, single-line type and relies on gaps rather than leading. Odd sizes are real: 13 px, 17.65625 px, 47.5 px, 23.9215 px. Do not round them.

**Spacing.** A loose 4-based rhythm with deliberate exceptions: 4, 8, 10, 12, 16, 20, **21**, 24, 32, 40, **56**, 60. The 21 px gap is the portfolio footer stack; 56 px separates portfolio metrics. Product padding is typically `10px` or `12px` inside controls; portfolio cards are `24px` all round.

**Borders.** Almost every "border" in this file is an **inset box-shadow ring**, not a CSS border — `inset 0 0 0 1px #E3E3E3` on product cards, `inset 0 0 0 1px #D0D0D0` on portfolio frames, `inset 0 0 0 1.188px #34465E` on the logo mark. The portfolio project-card body is the exception and uses a real 1 px border, because the top image frame owns the ring. Ring tokens live in `tokens/shadows.css`.

**Corners.** 4 px is the default (buttons, chips, badges, inputs). 8 px for panels, 12 px for portfolio cards, 2–3 px for tiny indicators, 100 px pills for the portfolio CTA and the desktop/mobile toggle, 30 px circles for social buttons. Portfolio project cards use asymmetric radii: image frame `12px 12px 8px 8px`, body `0 0 12px 12px`, so the two halves read as one card.

**Cards.** Product: white fill, 8 px radius, hairline ring, no shadow by default; `0px 2px 8px rgba(0,0,0,.1)` when raised, `0px 2px 6px rgba(0,0,0,.25)` when pressed, `0px 1px 40px 10px rgba(0,0,0,.15)` for overlays. Portfolio: paper fill on paper background — the card is defined by its hairline alone, never by a shadow or a tint.

**Backgrounds.** Flat colour only. No gradients, no textures, no patterns, no illustration. The product sits on white; the portfolio sits on `#F5F5F5`. Full-bleed elements (header, event banner, footer) span the full 1440/1920 and are separated by a single hairline.

**Imagery.** The file carries almost no bitmaps: two 50 px social icons in the footer, five interior product images, and one 6.2 MB event-banner photograph that exceeded the extractor's budget and is therefore absent. Project image frames in the portfolio are **empty in the source** — the designer had not placed captures yet. The UI kits leave those areas blank with a note rather than substituting stock imagery.

**Transparency and blur.** Used only for scrims and shadows (`rgba(0,0,0,.1)` … `rgba(0,0,0,.6)`, one `rgba(38,38,38,.65)` overlay). No backdrop blur anywhere. The one systematic use of opacity is `0.6` on the entire "Side Project" card row — the file dims a whole section to signal secondary content.

**States.** Hover is a darker fill of the same hue, never a shadow or a scale: `#34465E → #243245` on the portfolio CTA; product hover states are separate Figma variants with a deeper grey ring. Disabled is a grey fill with grey text (`#E3E3E3` / `#999999`). Focus is a blue ring (`inset 0 0 0 1px #024DDF`). Selection is the blue tint `#EBF2FF` with a `#024DDF` ring.

**Motion.** The source is a static document — no prototype flows, no transitions, no easing curves. `tokens/motion.css` therefore holds *house defaults*, clearly marked as such: 120/180/280 ms, `cubic-bezier(0.2,0,0.2,1)`, and opacity/colour transitions only. Do not invent springs, bounces or entrance animations for this brand.

**Layout.** Product screens are 1440 px wide with a full-bleed 50 px header and a two-column body (1006 px seat map + 410 px offer rail, 24 px gutter). Portfolio pages are 1920 px with a centred 1260 px column and 24 px inner padding; the footer is full-bleed with 60 px side padding. Nothing is fixed or sticky in the source.

---

## Iconography

The file uses **outlined vector icons drawn as Figma components**, not an icon font and not a third-party set. Two grids coexist: **24 × 24** for interface icons (menu, close, check, plus, minus, info, help, user, tickets, calendar, dropdown arrow) and **16 × 16** for content/amenity icons (hotel, food & bev, alcohol, merch, restaurant, transportation, location, time, cost, VIP, tickets, special entry, yoga, charity, book, check). Stroke weight is a consistent ~1.5 px at 24 px, corners are rounded, and everything is monochrome — icons inherit the surrounding text colour rather than carrying their own.

Two icons in the file are borrowed from open sets and named accordingly: `ic:sharp-arrow-back` (Material, used as the portfolio CTA's trailing arrow, rotated) and `mingcute:fire-line` (used to flag high-demand offers). Stars come in filled and unfilled pairs for ratings. No emoji are used in the product; the portfolio footer uses ☕✨ once.

All 40 glyphs were extracted from the file into `components/icons/icon-data.js` as raw `{ viewBox, body }` SVG data. There is no `Icon` component — the source defines none, so nothing is exported; read the data file directly or paste a glyph's markup inline. **No CDN icon set is linked and nothing was substituted.** Caveat: a minority of these icons were authored as *stroked* vectors, and the extractor could only recover fill geometry for some of them — a few (notably the simple calendar, transportation and restaurant glyphs) render thin or partially. Where a glyph matters, re-export it from Figma as SVG and drop it into `assets/`.

`assets/` holds the raw material copied straight out of the file: `portfolio-logo-mark.svg` (the boxed S of the wordmark), `play-cursor-ellipse.svg` and `play-cursor-ellipse-stroke.svg`, and the two footer social bitmaps `social-linkedin.png` / `social-google.png`. Product interior images live beside the components in `components/kit/assets/` and are painted through the generated `.fig-asset-*` classes in `components/kit/fig-assets.css`.

**Logos.** The file *does* define marks, so nothing was drawn from memory: `PortfolioLogo` (type + the copied `Vector-36.svg`), `TicketmasterBrandMark`, `TicketmasterTravelLogos` (primary/black/white) and `Logos` (three lockups). All are extracted geometry.

---

## Typography substitutions — please read

**Instrument Sans is real.** You supplied the variable TTFs; weights 400–700 (upright and italic, widths 75–100%) are self-hosted from `fonts/` and declared in `tokens/fonts.css`. It replaces Tomato Grotesk as the brand face; the portfolio wordmark and closing headline render in it.

One face is still substituted:

| File uses | Substituted with | Where it shows |
| --- | --- | --- |
| **Averta** (400, 600) | **Figtree** (Google) | All product UI — the majority of the system |

Space Grotesk, IBM Plex Sans and Inter are the real faces and load from Google Fonts. The macOS window-chrome mock uses `--font-system-ui` (the native `-apple-system` stack) rather than a webfont, by design.

**If you have the Averta webfonts, send them over** — dropping the files in and adding `@font-face` rules to `tokens/fonts.css` will make every product component render in the true face. Components reference `var(--font-product)`, so the swap is a one-line change.

---

## Index

| Path | What it is |
| --- | --- |
| `styles.css` | Global entry point — `@import` list only |
| `tokens/fonts.css` | Font stacks, self-hosted Instrument Sans `@font-face` rules + Google Fonts import |
| `tokens/colors.css` | Both palettes, plus semantic aliases and the `[data-theme="portfolio"]` scope |
| `tokens/typography.css` | Type scale and weights |
| `tokens/spacing.css` | Gaps, paddings, layout constants |
| `tokens/radius.css` | Corner radii |
| `tokens/shadows.css` | Inset rings and the four elevations |
| `tokens/motion.css` | House defaults (not from the source) |
| `guidelines/*.card.html` | 18 foundation specimen cards (Colors, Type, Spacing) |
| `components/kit/` | 68 components: `<Name>.jsx`, `.d.ts`, `.prompt.md`, plus 2 `@dsCard` sheets |
| `components/icons/` | `icon-data.js` — 40 glyphs extracted from the file as `{ viewBox, body }` SVG data |
| `ui_kits/portfolio/` | Portfolio home page at 1920 px |
| `templates/portfolio-home/` | Portfolio home as a reusable template |
| `fonts/` | Instrument Sans variable TTFs (upright + italic), self-hosted |
| `assets/` | Logos, cursor vectors, social bitmaps copied from the file |
| `SKILL.md` | Agent Skills wrapper for use outside this project |

### Components

**Actions** — `Button`, `PrimaryButton`, `CTA`, `BYOCTAWithIcon`, `OrFromText`, `ControlsClear`

**Forms** — `InputField`, `BASEInputField`, `FieldInputValidationBASE`, `DateRange`, `Radio`, `CheckboxCheckmark`, `PromoCode`

**Feedback** — `FeedbackError`, `FeedbackSuccess`

**Badges & tags** — `HotelBadges`, `Badge`, `Tag`, `Group`, `StarFilled`, `StarUntfilled`, `Tickets16`, `VIP16`, `Frame42475`, `Frame1321322181`

**Navigation & chrome** — `DesktopHeader`, `ProductTabs20`, `DesktopTicketsTab`, `DesktopPackagesTab`, `LanguageSelector`, `Navi`, `NaviToggle`, `Footer`, `Frame8`

**Offers & packages** — `TicketOffers20`, `TicketOfferCards20`, `TicketOffersDrawer20`, `TicketDetails120`, `ProductSummary20`, `PackageOptionCards`, `SelectPackage`, `PDPDesktop`, `SeatMapDesktop`, `EventBannerDesktop`, `PackagesSearchBarDesktop`

**Brand** — `Logos`, `TicketmasterTravelLogos`, `TicketmasterBrandMark`, `PortfolioLogo`, `PlayCorsor`, `CoreTrafficLightsCatalina`

**Icons** — the extracted component glyphs `IcSharpArrowBack`, `IconTickets`, `IconsTickets`, `IconsCalendarSimple`, `IconsCheck`, `IconsClose`, `IconsDropdownArrow`, `IconsHelp`, `IconsHelp2`, `IconsHelp3`, `IconsInfo`, `IconsMenu`, `IconsMinus`, `IconsPlus`, `IconsUser`, `BTIconsLanguage`, `MingcuteFireLine`

### Naming notes

Component names come from the Figma layer names, transliterated to valid identifiers. Families whose Figma name starts with a number gain a trailing digit pair instead: `2.0 product summary → ProductSummary20`, `2.0 product tabs → ProductTabs20`, `2.0 ticket details #1 → TicketDetails120`, `2.0 ticket offer cards → TicketOfferCards20`, `2.0 ticket offers → TicketOffers20`, `2.0 ticket offers drawer → TicketOffersDrawer20`. Components the file named after their frame ID keep that name (`Frame8`, `Frame42475`, `Frame1321322181`, `Group`) — renaming them would break the link back to the source. `StarUntfilled` is spelled as authored.

### Intentional additions

- **`tokens/motion.css`** — the source specifies no motion. These are marked house defaults, not extracted values.

Nothing else was added. There is no Toast, Tooltip, Modal, Avatar or Accordion here because the file does not define them. The 40 extracted glyphs live in `components/icons/icon-data.js` as raw SVG data with no React wrapper — the source defines no icon component, so none is exported.
