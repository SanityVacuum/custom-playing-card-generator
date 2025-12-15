# Custom Playing Card Generator

![License](https://img.shields.io/badge/license-CC%20BY--SA%204.0-blue.svg)
![Version](https://img.shields.io/badge/version-5.2-green.svg)

A free, open-source web application for creating professional-quality custom playing cards. Design unique decks with custom suit icons, face cards, and jokers. Generate high-resolution cards optimized for print-on-demand services.

**🎴 [Try it now at capsaicin.com](https://www.capsaicin.com)**

---

## ✨ Features

### Card Generation
- **4-suit or 5-suit decks** - Traditional 52-card decks or unique 65-card 5-suit decks
- **Custom suit icons** - Upload your own OR select from 18 built-in designs
- **Face cards** - Blank, upload your own, OR select from library (13 designs)
- **Jokers** - None, 2 standard, OR 7 game jokers (WILD/SKIP/JOKER for Phase 10, Five Crowns)
- **Custom card backs** - Upload with resize control
- **Safety margins** - Tight or Safe mode (+50px extra for home printing)

### Professional Output
- **High-resolution** - 2448×3330px (MakePlayingCards) or 825×1125px (Game Crafter)
- **Auto-cropping** - Removes white borders from images
- **Auto-color detection** - Samples dominant color, darkens if too light
- **Individual resize controls** - Fine-tune every element
- **Cut/bleed overlay** - Preview print guidelines

### Output Options
- **Download ZIP** - All cards as PNG files
- **Game Crafter integration** - Direct upload to your account

---

## 🚀 Quick Start

### For Users
1. Visit **[capsaicin.com](https://www.capsaicin.com)**
2. Configure deck → Upload/select icons → Preview → Download/Upload
3. Done!

### For Developers
```bash
git clone https://github.com/SanityVacuum/custom-playing-card-generator.git
cd playing-card-generator
open index.html  # No build needed!
```

**Single HTML file** - No dependencies, no build process, runs entirely in browser.

---

## 📖 Usage Examples

**Traditional 4-Suit Deck**
- Select "4 Suits" → Choose Hearts/Diamonds/Clubs/Spades from library → Done

**5-Suit Game Deck (Five Crowns)**
- Select "5 Suits" → Upload custom icons → Add 7 jokers → Upload to Game Crafter

**Custom Themed Deck**
- Design suit icons → Upload 3 court cards → Add card back → Download ZIP

---

## 🎨 Included Assets

**18 Pip Designs:** Spades, Hearts, Diamonds, Clubs, Baseball, Basketball, Football, Soccer, Hockey, Dunk, Anchor, Crown, Star, Wine, Pharmacy, F-16, Bear, Wolf

**13 Court Cards:** Classic, Comic, Surrealist (Dali), Fantasy styles

**Joker Library:** Dynamic loading from server

---

## 🛠️ Technical Details

| Platform | Size | DPI | Format |
|----------|------|-----|--------|
| MakePlayingCards | 2448×3330 | 300 | PNG |
| Game Crafter | 825×1125 | 300 | PNG |
| PrinterStudio | 2448×3330 | 300 | PNG |

**Tech Stack:** HTML5 Canvas, TailwindCSS, JSZip, Vanilla JS, Game Crafter API

**Browser Support:** Chrome 90+, Firefox 88+, Safari 14+, Edge 90+

---

## 📋 Game Compatibility

**5-Suit Games:** Five Crowns, Phase 10, Skip-Bo
**4-Suit Games:** Poker, Bridge, Hearts, Rummy, Canasta, Pinochle

---

## 🤝 Contributing

1. **Report bugs** - Open an issue
2. **Suggest features** - Open an issue  
3. **Submit PRs** - Fix bugs or add features
4. **Improve docs** - Help others

---

## 📜 License

**Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)**

**You are free to:**
- ✅ Share and redistribute
- ✅ Remix and adapt (even commercially)

**Under these terms:**
- 📝 Give credit to Dan Atkins
- 🔄 Share derivatives under same license

[Full License](https://creativecommons.org/licenses/by-sa/4.0/)

---

## 💡 Best Practices

**For Print Quality:**
- Use PNG with transparency
- High-res images (1000-2000px)
- Enable cut/bleed overlay
- Use Safe margins for home printing

**For Game Crafter:**
- Get API key first
- Enable Linen Finish ($0.25/sheet)
- Consider UV coating

---

## 🆘 Support

**Found a bug?** [Open an issue](https://github.com/SanityVacuum/custom-playing-card-generator/issues)

**Questions?** Email: [dan.atkins@gmail.com](mailto:dan.atkins@gmail.com)

---

## 📊 Version History

**v5.2** (Dec 2024) - Enhanced showcase, footer, lightbox
**v5.1** (Dec 2024) - Real card images, bug fixes
**v5.0** (Dec 2024) - Orbitron font, UX improvements, CC license
**v4.0** (Dec 2024) - Margins, card backs, joker resize
**v3.0** (Dec 2024) - Game Crafter integration

---

## 🔗 Links

- **Live:** [capsaicin.com](https://www.capsaicin.com)
- **GitHub:** [SanityVacuum](https://github.com/SanityVacuum)
- **Issues:** [Report here](https://github.com/SanityVacuum/custom-playing-card-generator/issues)
- **License:** [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)

---

**Made with ❤️ by Dan Atkins**

⭐ **Star this repo if you find it useful!**

