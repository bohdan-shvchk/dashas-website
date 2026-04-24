# Handoff: Webinar Landing Site — "Автоматизуйте рутину за допомогою ШІ"

## Overview
A mobile-first landing page and registration form for a free webinar about AI automation tools. The site consists of two pages:
1. **Landing page** (`index.html`) — explains the value proposition, shows a time-waste table, lists automation ideas, and drives sign-ups
2. **Registration form** (`register.html`) — collects participant info and submits to a Google Forms endpoint

## About the Design Files
The files in this bundle are **HTML design prototypes** — high-fidelity references showing intended look, copy, and behavior. The task is to **recreate these designs in your target codebase** (e.g. Next.js, React, Vue, etc.) using its established patterns, routing, and component libraries — not to ship the HTML directly.

## Fidelity
**High-fidelity.** Pixel-accurate colors, typography, spacing, border radii, and interactions are all defined. Recreate the UI as close as possible to the reference files.

---

## Screens / Views

### 1. Landing Page (`index.html`)

**Purpose:** Convince visitors to register for the free webinar.

**Layout:**
- Max content width: `480px`, centered
- Background: `#F0EDE6` (warm beige)
- All sections are white cards (`border-radius: 18px`, `background: #fff`) with `12px` gap between them
- Horizontal padding on cards: `22px`; page side margins: `16px`

**Sections (top to bottom):**

#### Sticky Nav
- `position: sticky; top: 0`
- Background: `rgba(240, 237, 230, 0.92)` + `backdrop-filter: blur(12px)`
- Left: logo with green dot (`#3DB87A`, 8×8px circle) + text "ШІ для роботи"
- Right: dark pill button "Реєстрація" → links to `register.html`
- Border-bottom: `1px solid rgba(0,0,0,0.06)`

#### Hero Card
- Cover area: `height: 180px`, warm gradient placeholder (`#DDD8CF → #C5BDB2`) with ⌛ emoji centered at 48px
- Body padding: `24px 22px 28px`
- Tag chip: "Безкоштовний вебінар" with green dot, `background: #F0EDE6`, `border-radius: 50px`, `font-size: 12px`
- Title: `font-size: 28px; font-weight: 700; letter-spacing: -0.5px`
- Subtitle: `font-size: 15px; color: #6B6760`
- CTA button: dark pill → `register.html`
- Info chips: "🆓 Безкоштовно" and "⏱️ Без технічного досвіду"

#### Problem Card
- Label: "Проблема" (uppercase, 11px, muted)
- Title in orange accent: `color: #D27A2D; font-size: 20px`
- Body text + 3 ❌ bullet items
- Quote block: `border-left: 3px solid #D27A2D; background: #FBF0E4; border-radius: 0 12px 12px 0; font-style: italic`

#### Time Table Card
- Custom HTML table with header row: "Задача" / "На тиждень"
- 7 rows of tasks + time estimates
- Total row: dark card `background: #1C1A17; color: white; border-radius: 12px`
  - Left label `font-size: 13px`, right value `font-size: 20px; font-weight: 700`

#### Mid CTA (dark card)
- `background: #1C1A17; border-radius: 18px`
- Badge chip (white 15% opacity background)
- Title white `font-size: 22px`
- Subtitle `color: rgba(255,255,255,0.65)`
- White pill button (full width) → `register.html`

#### Automation Ideas Section (6 accordion cards)
Each card is a `<details>` accordion:
- Icon in `44×44px` rounded square (`background: #F0EDE6; border-radius: 12px`)
- Title `font-size: 16px; font-weight: 700`
- Summary toggle: `+` rotates to `×` when open
- Body: description text + dash-list + green result tag (`color: #2A7A52; background: rgba(42,122,82,0.08)`)

Items: ✉️ Пошта, 💰 Фінанси, 📚 Навчання, 📱 Контент, 🗓️ Планування, ✈️ Подорожі

#### How to Start (3 steps card)
- Numbered circles: `width: 32px; height: 32px; background: #1C1A17; color: white; border-radius: 50%`
- Step title `font-size: 15px; font-weight: 600`
- Step text `font-size: 14px; color: #6B6760`

#### Final CTA (same as mid CTA)

#### Author Card
- Flex row, `gap: 16px`
- Avatar: `56×56px` circle, gradient placeholder + 👩‍💼 emoji
- Name `font-size: 16px; font-weight: 700`
- Role `font-size: 13px; color: #6B6760`
- Instagram link chip → `https://www.instagram.com/darya_moreno/`

#### Sticky Bottom Bar
- `position: fixed; bottom: 0; left: 0; right: 0; z-index: 200`
- Gradient fade: `linear-gradient(to top, #F0EDE6 70%, transparent)`
- Full-width dark pill button "Зареєструватись на вебінар — безкоштовно" → `register.html`
- `box-shadow: 0 4px 24px rgba(0,0,0,0.2)`
- Pointer events: only button is clickable (`pointer-events: none` on bar, `all` on button)

---

### 2. Registration Form (`register.html`)

**Purpose:** Collect participant data for webinar invitation.

**Layout:** Same max-width/card system as landing page. No sticky bottom bar.

**Sections:**

#### Form Header Card
- Badge + title + description paragraph + orange note box

#### Form Fields (split across 3 cards with dividers between fields)

**Card 1 — Contact:**
| Field | Type | Required | Notes |
|---|---|---|---|
| Email | `email` input | ✅ | Auto-copies to invite email field |
| Ваше імʼя | `text` input | ✅ | |
| Пошта для запрошення | `email` input | ✅ | Auto-filled from email, editable |
| Роль або сфера | `text` input | ✅ | Hint: "коротко, у вільній формі" |

**Card 2 — Questions:**
| Field | Type | Required |
|---|---|---|
| Задачі, що набридли | `textarea` (4 rows) | ✅ |
| Питання про ШІ | `textarea` (4 rows) | ✅ |

**Card 3 — AI Experience (radio):**
Options:
- Ще не пробував(ла) нічого
- Спробував(ла) кілька інструментів, але не розібрався(лась)
- Використовую регулярно кілька інструментів
- Вже маю досвід і хочу дізнатись більше

**Card 4 — Time Preference (radio + other):**
Options:
- 📅 Будній день 18:00–21:00
- ☀️ Вихідний день 10:00–12:00
- 🌤️ Вихідний день 14:00–17:00
- Інший варіант (free text, clicking focuses radio)

**Input styling:**
- Background: `#F0EDE6` (unfocused), `#fff` (focused)
- Border: `1.5px solid transparent` → `1.5px solid #D27A2D` on focus
- Border-radius: `12px`
- Padding: `13px 15px`
- Font: DM Sans 15px

**Radio options:**
- Full-width row with icon + label
- Background: `#F0EDE6`; border: `1.5px solid transparent`
- Selected: `border-color: #D27A2D; background: #FBF0E4`

**Submit button:**
- Full-width dark pill, same as landing page

**Form submission:**
- `fetch()` with `method: POST, mode: no-cors` to Google Forms endpoint:
  `https://docs.google.com/forms/d/e/1FAIpQLSdEzPIKaEFSzI1XcfnciomzxKBhKPYcZLAUW0J40IVAF3fRTg/formResponse`
- ⚠️ **Important:** The `entry.*` field IDs in the prototype are approximate — verify them from the actual Google Form source before deploying. Alternatively, replace with your own backend endpoint.

**Success state:**
- All cards hidden, success card shown with 🎉 + thank-you message + Instagram link

---

## Interactions & Behavior

| Interaction | Behavior |
|---|---|
| Nav CTA / sticky button | Navigate to `register.html` |
| Back button (register page) | Navigate to `index.html` |
| Accordion items | Toggle open/close; `+` rotates to `×` |
| Email field input | Auto-fills invite email field (until user edits it manually) |
| Radio option click | Styles selected option with orange border + light bg |
| "Other time" text focus | Auto-selects its radio button |
| Form submit (valid) | Shows loading state, submits to Google Forms, shows success screen |
| Form submit (invalid) | Highlights first empty field with red border, scrolls to it |

---

## Design Tokens

### Colors
```
--bg:           #F0EDE6   /* warm beige page background */
--card:         #FFFFFF   /* card background */
--text:         #1C1A17   /* primary text */
--muted:        #6B6760   /* secondary text */
--accent:       #D27A2D   /* orange accent (headings, borders, focus) */
--accent-bg:    #FBF0E4   /* orange tint background */
--btn-dark:     #1C1A17   /* dark button / dark card background */
--green-dot:    #3DB87A   /* live/online indicator */
--green-result: #2A7A52   /* result tag text */
```

### Typography
- **Font family:** DM Sans (Google Fonts)
- **Weights used:** 300, 400, 500, 600, 700

| Role | Size | Weight |
|---|---|---|
| Page title (hero) | 28px | 700 |
| Section title | 20–22px | 700 |
| Card label | 11px uppercase | 600 |
| Body text | 15px | 400 |
| Small/muted | 13–14px | 400–500 |
| Button | 15–16px | 600 |
| Nav | 15px | 600 |

### Spacing & Radii
```
Card border-radius:       18px
Input border-radius:      12px
Pill button border-radius: 50px
Gap between cards:        12px
Card padding:             22px (sides), 24px (top/bottom)
Page side margin:         16px
Max content width:        480px
```

### Shadows
```
Sticky button: 0 4px 24px rgba(0,0,0,0.2)
Sticky button hover: 0 8px 30px rgba(0,0,0,0.25)
```

---

## Assets
- **Cover image:** Placeholder gradient `#DDD8CF → #C5BDB2` with ⌛ emoji. Replace with a real photo — recommended size: `480×360px` (`2:1.5` ratio for mobile).
- **Author avatar:** Placeholder circle gradient with 👩‍💼 emoji. Replace with Daryna's real photo.
- **Icons:** All emoji-based, no external icon library needed.

---

## Files
| File | Description |
|---|---|
| `index.html` | Landing page — complete self-contained HTML+CSS+JS |
| `register.html` | Registration form page — complete self-contained HTML+CSS+JS |

---

## Notes for Developer
1. Replace Google Forms `entry.*` IDs with verified ones from the actual form source (inspect the form HTML, search for `entry.`).
2. If you want proper form submission confirmation, replace the `no-cors` fetch with a serverless function (e.g. Next.js API route) that proxies the submission.
3. The cover image placeholder and author avatar are intentionally left as gradients — swap them for real images before launch.
4. Both pages are fully self-contained with inline styles and no external dependencies beyond Google Fonts and the form endpoint.
