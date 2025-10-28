# Wikipedia Dark Theme Automatic

![Tampermonkey](https://img.shields.io/badge/Userscript-Tampermonkey-black)
![License: MIT](https://img.shields.io/badge/License-MIT-green)

## Description

This userscript enforces and preserves Wikipedia’s **dark theme** across page reloads and navigations.
It works with both **Vector (desktop)** and **Minerva (mobile)** skins, prevents the initial white flash with inline anti-flash CSS, and keeps the UI consistent even when the DOM changes dynamically.

The goal is to deliver a comfortable, distraction-free **dark reading** experience that simply sticks.

---

## ✨ Features

- **Always-on dark mode**: forces the `skin-theme-clientpref-night` class and updates skin query params.
- **Vector & Minerva** support: handles `?vectornightmode=1` (desktop) and `?minervanightmode=1` (mobile).
- **Anti-flash**: minimal inline CSS at `document-start` to avoid the white flash.
- **Resilient to DOM changes**: watches class and theme link mutations (MutationObserver).
- **Local preference hint**: stores `wikimedia-ui-theme=dark` in `localStorage`.
- **Optional auto mode**: can follow the OS theme via `prefers-color-scheme`.
- **Auto-updates** via GitHub `@updateURL`.

---

## Installation

1. Install a userscript manager:
   - [Tampermonkey](https://www.tampermonkey.net) (recommended)
   - [Violentmonkey](https://violentmonkey.github.io)
   - [Greasemonkey](https://www.greasespot.net)

2. Click here to install the script:  
   **[Wikipedia Dark Theme Automatic](https://raw.githubusercontent.com/ImElio/wikipedia-dark-theme-automatic/main/wikipedia-dark-theme-automatic.user.js)**

3. Confirm the installation when prompted by your userscript manager.

---

## Development

- Language: JavaScript (ES6)
- Userscript managers tested: Tampermonkey ≥ v4.19
- Browsers: Chrome, Edge, Firefox, Brave, Opera
- File: `wikipedia-dark-theme-automatic.user.js`

**Script header** (auto-update ready):

```
@homepageURL  https://github.com/ImElio/wikipedia-dark-theme-automatic
@supportURL   https://github.com/ImElio/wikipedia-dark-theme-automatic/issues
@updateURL    https://raw.githubusercontent.com/ImElio/wikipedia-dark-theme-automatic/main/wikipedia-dark-theme-automatic.user.js
@downloadURL  https://raw.githubusercontent.com/ImElio/wikipedia-dark-theme-automatic/main/wikipedia-dark-theme-automatic.user.js
```

---

## ❓ FAQ

**Q: Will this interfere with Wikipedia’s own theme selector?**  
A: The script forces dark mode by default for consistency. You can switch it to “Automatic (OS)” in the config, or temporarily disable the script from your userscript manager.

**Q: Does it modify my account settings?**  
A: No. It only affects your local browser session. It doesn’t change server-side preferences.

**Q: Will it break the layout or images?**  
A: It only tweaks classes/theme assets and adds minimal anti-flash CSS. If you notice a theme glitch on a particular language wiki, please open an issue.

**Q: Does it work on mobile?**  
A: Yes—Minerva skin is supported. The script adds `?minervanightmode=1` when needed.

**Q: How do I stop the anti-flash black background?**  
A: Set `ANTI_FLASH_INLINE_CSS` to `false` in the config at the top of the script.

---

## Support

- Submit issues and enhancements here: **[Issues](https://github.com/ImElio/wikipedia-dark-theme-automatic/issues)**
- Contributions are welcome—feel free to open PRs.

---

## License

This project is licensed under the **MIT License**.
