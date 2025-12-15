# Changelog

All notable changes to the Custom Playing Card Generator will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

---

## [5.2] - 2024-12-15

### Added
- **Enhanced card showcase** - 15 cards (was 5), half the size, 2 rows
- **Click-to-enlarge lightbox** - Click any showcase card to view full size
- **Professional footer** with:
  - About section with project description
  - GitHub links (profile, source code, issues)
  - Contact info (email) with icon
  - "Found this useful?" section with engagement prompts
  - Bottom bar with copyright, domains, printer links
- **"Creative Commons" spelled out** in license text (was just "CC BY-SA 4.0")
- **Escape key support** to close lightbox modal

### Changed
- Card showcase grid: 5 columns → 10 columns (responsive: 5 on mobile, 10 on desktop)
- Card showcase cards: Reduced size by 50% to fit more cards
- Lightbox modal styling: Black background with opacity, centered image

### Fixed
- None (this is an enhancement release)

---

## [5.1] - 2024-12-14

### Added
- **Real card showcase images** using actual generated cards from capsaicin.com/images/
- Cards displayed: Ace of Spades, 8 of Clubs, 10 of Stars, King of Diamonds, Joker

### Changed
- Replaced placeholder text showcase with actual card images

### Fixed
- **Card back resize control** appearing on court cards (J, Q, K)
  - Added explicit `display: none` for card back resize on regular cards
  - Now only shows when previewing actual card back

---

## [5.0] - 2024-12-14

### Added
- **Orbitron header font** ("SERPENTINE" style) for "CUSTOM PLAYING CARD GENERATOR"
- **Clear terminology labels**:
  - "Suits (Pips)" instead of just "Pip Source"
  - "Face Cards (Courts)" instead of just "Face Cards"
- **Creator attribution** in subtitle: "Created by Dan Atkins"
- **CC BY-SA 4.0 license** displayed in subtitle with link
- **5-card showcase banner** with placeholder examples

### Changed
- **Safety Margins moved** from its own section to Configuration section
- Header styling: Added gradient background, increased font size
- Subtitle styling: Added opacity, smaller font

### Fixed
- UX clarity issues with confusing labels

---

## [4.0] - 2024-12-13

### Added
- **Safety margin modes**: Tight (standard) or Safe (+50px extra margin)
  - Addresses home printer bleed issues
  - Repositions indices and pips accordingly
- **Custom card back upload** with resize slider
  - Upload your own design
  - Resize from 50% to 150%
  - Preview before generating
  - Default blue gradient if not uploaded
- **Individual joker resize controls**
  - Separate resize for WILD, SKIP, JOKER (when using 7 jokers)
  - Resize from 50% to 150%
- **Card back preview button** in card grid

### Changed
- Margin system: Single value system → Configurable Tight/Safe modes
- Card back generation: Always included (required for Game Crafter)

### Fixed
- Court cards overlapping corner elements in some cases

---

## [3.0] - 2024-12-12

### Added
- **Game Crafter API integration**
  - Direct upload to your Game Crafter account
  - Auto-creates game, deck, and folder
  - Auto-resizes cards from MPC (2448×3330) to GC (825×1125)
  - Progress tracking with detailed logging
- **7-joker support** for game decks (Phase 10, Five Crowns)
  - 4 WILD cards
  - 2 SKIP cards
  - 1 JOKER card
  - Individual images for each type
- **Joker library selection** from server
  - Upload jokers to /jokers/ directory
  - Auto-loads via PHP index.php
  - Select individual jokers for WILD/SKIP/JOKER
- **Court card library** (13 designs)
  - cl1, cl2 (classic)
  - comic-J, comic-Q, comic-K
  - dali-J, dali-Q, dali-K (surrealist)
  - fant-J, fant-Q, fant-K (fantasy)
  - Loaded dynamically from /courts/ directory
- **Individual court card upload** (12-15 cards)
  - Upload unique image for each suit's J, Q, K
  - Separate from "3 shared images" option

### Changed
- Joker options: 0 or 2 → 0, 2, or 7 (depending on suit count)
- Face card options: blank/three → blank/library/three/individual

### Fixed
- CORS issues with court card library (added crossOrigin headers)
- Court card scaling to avoid overlapping indices

---

## [2.0] - 2024-12-11

### Added
- **Pip library** (18 designs)
  - Traditional suits: Spades, Hearts, Diamonds, Clubs
  - Sports: Baseball, Basketball, Football, Soccer, Hockey, Dunk
  - Themed: Anchor, Crown, Star, Wine, Pharmacy, F-16, Bear, Wolf
  - Dynamically loaded from /pips/ directory via PHP
- **Pip source selection**: Upload your own OR Select from library
- **Auto-color detection** from uploaded images
  - Samples dominant color
  - Darkens if too light (luminance check)
  - Ensures readability on white cards
- **Auto-cropping** of uploaded images
  - Removes pure white (#FFFFFF) borders
  - Removes transparent borders
  - 1px padding to avoid edge clipping
- **Individual pip resize** controls
  - Separate resize slider for each suit
  - Range: 50% to 150%
  - Applies to both corner pips and body pips

### Changed
- Suit icon upload: Direct upload only → Upload OR Library selection
- Color detection: Fixed colors → Sampled from images

### Fixed
- White borders causing layout issues
- Light-colored pips being unreadable on white cards

---

## [1.0] - 2024-12-10

### Added
- **Initial release** of Custom Playing Card Generator
- **4-suit or 5-suit deck generation**
  - 4 suits: 52 cards (+ optional 2 jokers)
  - 5 suits: 65 cards (+ optional 7 jokers)
- **Custom suit icon upload**
  - PNG, JPG, SVG support
  - Manual color picker for each suit
- **Face card options**:
  - Blank (add later in image editor)
  - Upload 3 shared images (J, Q, K)
- **Joker options**:
  - None
  - 2 jokers (standard deck)
- **High-resolution output**:
  - MPC specs: 2448×3330px @ 300 DPI
  - Proper aspect ratio (2.5:3.5)
- **Card layout rendering**:
  - Indices in corners
  - Corner pips below indices
  - Body pips for 2-10 (traditional patterns)
  - Large center pip for Aces
  - Face cards rendered blank or with uploaded images
- **Preview system**:
  - Click any rank button to preview
  - Preview canvas with zoom
  - Download individual card
- **ZIP download**:
  - All cards exported as separate PNG files
  - Organized by rank and suit
  - Uses JSZip library
- **Cut/bleed overlay** toggle
  - Shows trim lines (red)
  - Shows safe zones (blue)
  - Shows border guides (orange)
  - Transparent PNG template overlay

### Known Limitations
- No direct printer integration
- Manual color selection only
- No library of pre-made designs
- Court cards not included in library

---

## Format

### Types of Changes
- **Added** - New features
- **Changed** - Changes in existing functionality
- **Deprecated** - Soon-to-be removed features
- **Removed** - Removed features
- **Fixed** - Bug fixes
- **Security** - Security vulnerabilities

### Version Numbering
- **Major.Minor.Patch** (Semantic Versioning)
- Major: Breaking changes, complete rewrites
- Minor: New features, backward compatible
- Patch: Bug fixes, small improvements

---

**Note:** Versions prior to 1.0 were development/alpha releases and are not documented here.
