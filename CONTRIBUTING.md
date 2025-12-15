# Contributing to Custom Playing Card Generator

Thank you for your interest in contributing! This document provides guidelines for contributing to this project.

---

## 🤝 Ways to Contribute

### 1. Report Bugs
Found a bug? Please [open an issue](https://github.com/SanityVacuum/custom-playing-card-generator/issues/new) with:
- **Browser & version** (e.g., Chrome 120, Firefox 115)
- **Steps to reproduce** (numbered list)
- **Expected behavior** (what should happen)
- **Actual behavior** (what actually happens)
- **Screenshots** (if applicable)

**Example:**
```
Browser: Chrome 120 on Windows 11

Steps to reproduce:
1. Select "5 Suits"
2. Upload custom image for Suit 1
3. Click "Apply Configuration"

Expected: Image should appear in preview
Actual: Image doesn't load, console shows error

Screenshot: [attached]
```

---

### 2. Suggest Features
Have an idea? [Open an issue](https://github.com/SanityVacuum/custom-playing-card-generator/issues/new) with:
- **Feature description** (what you want)
- **Use case** (why it's useful)
- **Possible implementation** (optional, how it might work)

**Example:**
```
Feature: Export to PDF instead of ZIP

Use case: Some print services accept PDF uploads directly

Possible implementation: Use jsPDF library to create multi-page PDF
```

---

### 3. Submit Pull Requests

#### Before You Start
1. Check if an issue exists for your change
2. If not, create one and discuss the approach
3. Fork the repository
4. Create a branch: `git checkout -b feature/your-feature-name`

#### Code Guidelines

**JavaScript:**
- Use clear, descriptive variable names
- Comment complex logic
- Follow existing code style
- Use `const` and `let` (not `var`)
- Keep functions focused (single responsibility)

**Good:**
```javascript
function calculateCardDimensions(aspectRatio, maxWidth) {
    // Calculate height to maintain aspect ratio
    const height = maxWidth / aspectRatio;
    return { width: maxWidth, height };
}
```

**Avoid:**
```javascript
function calc(ar, mw) {
    var h = mw / ar;
    return { width: mw, height: h };
}
```

**HTML/CSS:**
- Use semantic HTML
- Follow TailwindCSS utility-first approach
- Keep inline styles minimal
- Maintain accessibility (alt text, ARIA labels)

#### Testing Your Changes
1. Test in multiple browsers (Chrome, Firefox, Safari, Edge)
2. Test on mobile devices (or use browser dev tools)
3. Test both 4-suit and 5-suit configurations
4. Test with different image formats (PNG, JPG, SVG)
5. Verify download ZIP works
6. If touching Game Crafter integration, test upload flow

#### Commit Messages
Use clear, descriptive commit messages:

**Good:**
```
Fix: Card back resize appearing on court cards
Add: Lightbox modal for card showcase
Update: Increase pip library to 18 designs
```

**Avoid:**
```
fix bug
update
changes
```

#### Pull Request Process
1. Update README.md if needed (features, usage)
2. Test thoroughly (see above)
3. Create PR with description:
   - What changed
   - Why the change was needed
   - How to test it
4. Link related issues: "Fixes #123"

**Example PR Description:**
```
## Changes
Added lightbox modal for card showcase

## Why
Users requested ability to view cards full-size before generating

## Testing
1. Click any card in showcase banner
2. Verify lightbox opens with full-size image
3. Click anywhere to close
4. Press Escape to close
5. Test on mobile

Fixes #45
```

---

## 🎨 Adding New Assets

### Adding Pip Designs
1. Create/obtain image (PNG with transparency recommended)
2. Upload to `/pips/` directory on server
3. Image automatically appears in library (PHP script lists all files)
4. No code changes needed!

**Image specs:**
- Format: PNG (with transparency) or SVG
- Size: 500-1000px recommended
- Aspect: Square works best
- Background: Transparent

### Adding Court Cards
1. Create/obtain court card image
2. Name format: `style-Rank.png` (e.g., `steampunk-K.png`)
3. Upload to `/courts/` directory
4. Appears automatically in gallery

**Image specs:**
- Format: PNG (with transparency)
- Size: 1000-2000px tall recommended
- Aspect: Roughly 2:3 (playing card ratio)

### Adding Jokers
1. Upload to `/jokers/` directory
2. Appears automatically in joker gallery

---

## 📖 Documentation

### Updating README.md
When adding features, update:
- Features section (brief description)
- Usage examples (if relevant)
- Version history (at bottom)

### Code Comments
Add comments for:
- Complex algorithms
- Non-obvious decisions
- Browser-specific workarounds
- Math calculations (explain the formula)

**Example:**
```javascript
// Luminance formula: 0.299*R + 0.587*G + 0.114*B
// If too light (>180), darken by 40% for readability
const luminance = 0.299 * r + 0.587 * g + 0.114 * b;
if (luminance > 180) {
    const darkFactor = 0.6;
    r = Math.round(r * darkFactor);
}
```

---

## 🐛 Debugging Tips

### Browser Console
Open with F12, check for:
- JavaScript errors (red text)
- Network errors (failed image loads)
- CORS issues (cross-origin requests blocked)

### Common Issues

**Images not loading:**
- Check CORS headers on server
- Verify URL is correct (case-sensitive)
- Check file exists in directory

**Canvas not rendering:**
- Verify dimensions are valid
- Check if image.onload fired
- Ensure image crossOrigin set if sampling pixels

**ZIP download fails:**
- Check all blobs created successfully
- Verify JSZip library loaded
- Check browser console for errors

---

## 📝 Style Guide

### Variable Naming
- Use camelCase: `cardWidth`, `suitIndex`
- Boolean variables: prefix with `is`, `has`, `should`
  - Good: `isLoaded`, `hasImage`, `shouldCrop`
  - Avoid: `loaded`, `image`, `crop`

### Function Naming
- Use verb + noun: `drawCard()`, `uploadImage()`, `calculateDimensions()`
- Avoid generic names: `doStuff()`, `process()`, `handle()`

### Constants
- Use UPPER_SNAKE_CASE for true constants:
```javascript
const MAX_CARD_WIDTH = 2448;
const DEFAULT_MARGIN = 170;
```

---

## 🔒 Security

### Never Commit:
- Personal credentials
- API keys
- Passwords
- `dan.html` (personal version with hardcoded credentials)

### If You Accidentally Commit Secrets:
1. Immediately change the password/key
2. Rewrite git history (or contact repo owner)
3. Never assume "deleted" means "gone" from git history

---

## 📄 License

By contributing, you agree that your contributions will be licensed under the same Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0) license as the project.

This means:
- ✅ Your code can be used commercially
- ✅ Your code can be modified
- 📝 Credit will be given to you
- 🔄 Derivatives must use same license

---

## 🙏 Code of Conduct

- Be respectful and constructive
- Welcome newcomers and help them learn
- Focus on the issue, not the person
- Assume good intentions
- Give credit where due

**Not acceptable:**
- Personal attacks
- Harassment
- Discrimination
- Spam
- Off-topic discussions in issues/PRs

---

## 📞 Questions?

- 💬 Open a [GitHub Discussion](https://github.com/SanityVacuum/custom-playing-card-generator/discussions) (coming soon)
- 📧 Email: [dan.atkins@gmail.com](mailto:dan.atkins@gmail.com)

---

**Thank you for contributing!** 🎉
