# Ronak & Devansha — Vivah Nimantran Website

**Type:** Interactive storytelling wedding invitation  
**Languages:** Hindi (primary), Gujarati, English  
**Tech:** Vanilla HTML5 + CSS3 + JS (no framework)  
**Style:** Traditional Vedic — red, gold, maroon, banana leaves, marigold garlands, Ganesha, auspicious symbols  

---

## 1. User Flow

```
[Language Selection] → [Splash / Ribbon Pull Animation] → [Storied Mode OR Text Mode]

STORIED MODE (default):
  → Roka Section (past event + photos + "Request More Photos" CTA)
  → Engagement Section (past event + photos + "Request More Photos" CTA)
  → Brahman Animation (families discussing → patrika reveal)
  → Event Timeline (all dates with animations)
  → Venue Details
  → Darshanabhilashi (family names)
  → Contact Form ("Share digital photos with me")

TEXT MODE (social card view):
  → Future events only (no past dates)
  → Clean card layout with animations/graphics
  → Venue + Family names + Contact form
```

---

## 2. Page Sections (Storied Mode — Hindi Version)

### Section 0: Language Gate
- Three cards/buttons: हिंदी | ગુજરાતી | English
- Decorative border with marigold garland motif
- Selection saves to localStorage, can be changed via floating language switcher
- Subtle entrance animation (fade + scale)

### Section 1: Splash Screen — Ribbon Pull
- Full-screen decorative splash with "|| श्री गणेशाय नमः ||" at top
- Visual: Bride silhouette (left) and Groom silhouette (right), separated
- A decorative ribbon/cord in the center with a pull handle
- **Interaction:** User drags/pulls the ribbon downward (touch + mouse)
- **Animation sequence:**
  1. Ribbon pulls → bride and groom silhouettes slide toward center
  2. They meet → flower/confetti burst (CSS particle animation)
  3. "|| शुभ विवाह ||" text reveals with golden glow
  4. Names appear: "रोनक & देवांशा"
  5. Auto-scroll down to next section after 2s pause

### Section 2: Roka (Past Event)
- Header: "|| रोका समारोह ||"
- Date: [PLACEHOLDER_ROKA_DATE]
- Decorative divider with kalash motif
- Photo grid (3-4 placeholder images) with subtle parallax
- "और तस्वीरें देखें" (See More Photos) button
- → Opens modal with name, email, phone fields
- → Submits to Google Sheet via Apps Script webhook
- Scroll-triggered entrance animations

### Section 3: Engagement (Past Event)
- Header: "|| सगाई समारोह ||"
- Date: [PLACEHOLDER_ENGAGEMENT_DATE]
- Similar layout to Roka — photos + request form
- Different decorative elements (rings, flowers)

### Section 4: Brahman / Patrika Animation
- **Scene:** Illustrated/silhouette animation
  1. Two family groups sitting on either side
  2. Brahman (pandit) in center with open book/patrika
  3. Families lean in, discussing
  4. Brahman begins writing on patrika
  5. Camera zooms into the patrika
  6. Patrika fills the screen — handwritten-style text reveals dates

- **Tech:** CSS keyframe animation + scroll-triggered transforms
- Fallback for reduced-motion: static illustration with dates listed

### Section 5: Event Timeline (Patrika View)
- Styled as a traditional patrika/invitation card
- Handwritten-style Hindi font (Google Fonts: Tiro Devanagari Hindi or Noto Serif Devanagari)
- Each date reveals with a writing animation (stroke-dasharray for SVG text, or sequential character reveal)

```
|| शुभ लग्न पत्रिका ||

गणेश स्थापना     — 15 नवम्बर 2026
तेल / हल्दी       — 16 नवम्बर 2026
माता पूजन        — 17 नवम्बर 2026
गरबा / संगीत      — 18 नवम्बर 2026
बारात प्रस्थान    — 20 नवम्बर 2026
खेत लगुन         — 21 नवम्बर 2026, सुबह 11:30 AM से 2:00 PM
बारात            — 21 नवम्बर 2026, शाम 9:00 PM से 10:00 PM
रिसेप्शन          — 29 नवम्बर 2026, शाम 7:30 PM
```

- Each line staggers in with 300ms delay
- Decorative borders: paisley, banana leaves, lotus

### Section 6: Venue
- Header: "|| विवाह स्थल ||"
- Venue name: [PLACEHOLDER_VENUE_NAME]
- Address: [PLACEHOLDER_ADDRESS]
- Google Maps embed (placeholder link)
- "दिशा-निर्देश प्राप्त करें" (Get Directions) button
- Decorated with rangoli patterns

### Section 7: Darshanabhilashi (Family Names)
- Header: "|| दर्शनाभिलाषी ||"
- Ornate frame/card with family names

**Groom's Side:**
```
पितश्री: [PLACEHOLDER_NAME]
मातश्री: [PLACEHOLDER_NAME]
दादाश्री: [PLACEHOLDER_NAME]
दादीश्री: [PLACEHOLDER_NAME]
ताऊजी: [PLACEHOLDER_NAME]
ताईजी: [PLACEHOLDER_NAME]
चाचाजी: [PLACEHOLDER_NAME]
चाचीजी: [PLACEHOLDER_NAME]
बुआजी: [PLACEHOLDER_NAME]
फूफाजी: [PLACEHOLDER_NAME]
```

**Kids:**
```
[PLACEHOLDER_KID_1], [PLACEHOLDER_KID_2], [PLACEHOLDER_KID_3]
```

**Closing words:**
```
[PLACEHOLDER — traditional blessing/closing text]
सर्वे भवन्तु सुखिनः सर्वे सन्तु निरामयाः
```

### Section 8: Contact / Photo Request
- Header: "यदि आप इस शुभ विवाह संस्कार में उपस्थित नहीं हो पाए, तो अपना संपर्क विवरण दें — हम आपको डिजिटल फ़ोटो भेजेंगे"
- Form: नाम, ईमेल, फ़ोन नंबर, संदेश (optional)
- Submit → Google Sheet
- Success animation: marigold petals falling
- Decorated with toran/bandanwar motif

---

## 3. Text-Only Mode (Social Card View)

Triggered by toggle at top: "कार्ड दृश्य" / "कहानी दृश्य"

- **Shows ONLY future events** (no Roka, no Engagement, no past dates)
- Clean card-style layout — still beautiful, not plain text
- Subtle entrance animations, decorative borders
- All wedding dates in a styled card
- Venue info
- Family names
- Contact form
- Shareable — works great as a WhatsApp/social forward

---

## 4. Design System

### Colors
- **Primary Red:** #C41E3A (sindoor red)
- **Deep Maroon:** #800020 (burgundy)
- **Gold:** #D4A017 (turmeric gold)
- **Light Gold:** #F5E6CC (cream/parchment)
- **Saffron:** #FF6600
- **White:** #FFF8F0 (warm white)
- **Dark Text:** #2D1810 (dark brown)
- **Green Accent:** #2E7D32 (banana leaf)

### Decorative Elements (CSS/SVG)
- Marigold garland borders (repeating SVG pattern)
- Banana leaf dividers
- Paisley corners
- Ganesha icon at section starts (|| श्री गणेशाय नमः ||)
- Rangoli patterns as section backgrounds
- Toran/Bandanwar (door hanging) motifs
- Kalash with coconut icons
- Lotus flowers
- Mango leaf toran

### Typography
- **Display/Headers:** Tiro Devanagari Hindi (serif, traditional) or Noto Serif Devanagari
- **Body:** Noto Sans Devanagari
- **Decorative:** Yatra One (for special headings)
- **Numbers/Dates:** Tabular figures, slightly larger
- **English fallback:** Playfair Display (serif)

### Animations
- Scroll-triggered reveals (IntersectionObserver)
- CSS keyframes for confetti/petals
- Smooth parallax on photo sections
- Text reveal (character-by-character for patrika)
- Spring-physics for interactive elements (ribbon pull)
- Respect `prefers-reduced-motion`

---

## 5. Technical Architecture

```
ronak-devansha-vivah/
├── index.html              # Main page (Hindi)
├── css/
│   ├── styles.css          # Core layout + components
│   ├── animations.css      # All keyframe animations
│   ├── decorations.css     # SVG patterns, borders, motifs
│   └── responsive.css      # Mobile breakpoints
├── js/
│   ├── app.js              # Main controller
│   ├── language.js          # i18n / language switching
│   ├── ribbon.js           # Splash screen interaction
│   ├── timeline.js         # Scroll-triggered timeline reveals
│   ├── patrika.js          # Brahman → patrika animation
│   ├── photos.js           # Photo gallery + lightbox
│   ├── forms.js            # Google Sheets integration
│   └── particles.js        # Confetti / petal effects
├── assets/
│   ├── images/             # Photos (placeholders for now)
│   ├── icons/              # Ganesha, kalash, lotus SVGs
│   └── patterns/           # Repeating SVG patterns
├── i18n/
│   ├── hi.json             # Hindi translations
│   ├── gu.json             # Gujarati translations
│   └── en.json             # English translations
├── PLAN.md                 # This file
└── README.md               # Project documentation
```

### Google Sheets Integration
- Google Apps Script web app as webhook endpoint
- POST request with form data (name, email, phone, message, type: "roka" | "engagement" | "photos")
- No API key needed — public Apps Script URL
- Success/error handling with visual feedback

### Performance
- No build tools — ship raw files
- Lazy-load photos (IntersectionObserver)
- Inline critical CSS
- SVG for all decorative elements (no raster images for decorations)
- Total page weight target: < 500KB (excluding photos)

---

## 6. Content Placeholders to Replace Later

| Placeholder | What Goes Here |
|---|---|
| `[PLACEHOLDER_ROKA_DATE]` | Actual Roka ceremony date |
| `[PLACEHOLDER_ENGAGEMENT_DATE]` | Actual engagement date |
| `[PLACEHOLDER_VENUE_NAME]` | Wedding venue name |
| `[PLACEHOLDER_ADDRESS]` | Full venue address |
| `[PLACEHOLDER_MAPS_LINK]` | Google Maps link |
| `[PLACEHOLDER_NAME]` x10 | Family member names with relationships |
| `[PLACEHOLDER_KID_1/2/3]` | Kids' names |
| `[PLACEHOLDER_PHOTO_x]` | Actual ceremony photos |
| `[PLACEHOLDER_GSHEET_URL]` | Google Apps Script webhook URL |
| `[PLACEHOLDER_CLOSING_TEXT]` | Traditional blessing/closing |
| `[PLACEHOLDER_GROOM_SURNAME]` | Groom's family name |
| `[PLACEHOLDER_BRIDE_SURNAME]` | Bride's family name |

All placeholders are marked with `[PLACEHOLDER_...]` in HTML and `__PLACEHOLDER__` in JS/JSON for easy find-and-replace.

---

## 7. Build Phases

### Phase 1: Hindi Storied Version
- Language gate (Hindi only active, others show "जल्द आ रहा है")
- Splash + ribbon pull animation
- All 8 sections with placeholder content
- Confetti/petal particle effects
- Photo request form (UI only, Google Sheet integration ready)
- Mobile responsive

### Phase 2: Text-Only Mode + Polish
- Toggle between storied/card view
- Card view with future dates only
- Animation polish + reduced-motion support

### Phase 3: Gujarati + English
- i18n system with JSON translation files
- Gujarati and English versions
- Language switcher fully functional

### Phase 4: Final Content + Deploy
- Replace all placeholders with real data
- Add real photos
- Connect Google Sheet webhook
- Deploy to domain
- Test on mobile (WhatsApp sharing)

---

*Ready for review. Once approved, I'll start building Phase 1.*
