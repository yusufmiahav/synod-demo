# General Synod Title Controller — Interactive Demo

A standalone interactive demo of the [General Synod Title Controller](https://github.com/yusufmiahav/synod-titles) for client presentations.

**No server. No Node.js. No installation.** A single HTML file that runs entirely in the browser.

🔗 **[View live demo →](https://yusufmiahav.github.io/synod-demo)**

---

## What this is

This is a UI prototype built for demonstrating the operator workflow to clients and stakeholders before deployment. All interactions are simulated in the browser — buttons respond, state updates, and the session history fills up exactly as they would in the real system. It does not connect to VMix.

---

## What you can demonstrate

### Member search
- **26 real GS members** across Bishops, Clergy, and Laity from the February 2026 data
- Type a GS number in the Quick Entry field — the grid filters in real time as you type
- `0` shows all members starting with 0, `00` narrows to 001–009, `245` selects Ms Christina Baron directly
- Filter by house using the pill buttons: Bishops, Clergy, Laity
- Search by name or diocese using the search bar
- Click any name card to send to preview

### Speaker workflow (Layer 1)
- Click a name card → member appears in the **Preview** slot
- **Send data only** → member moves to the **Live** slot, status shows "Overlay off — data loaded" (amber). Simulates loading the graphic without triggering it — VMix operator controls timing
- **Send + go live** → member moves to Live, then after a simulated 650ms delay the overlay fires, status turns teal "~ On screen"
- **Clear data + hide** → clears the graphic, on-air panel resets to Blank
- **Overlay in / Overlay out** → manually toggle overlay state

### Item / Question (Layer 2)
- Toggle between **Item** and **Question** mode — the hint text updates to show which VMix GT input would fire
- Type any number (e.g. `5`) → displays as `005`
- **Go live** → number appears in the on-air panel with mode label
- **Overlay in / out** and **✕ clear** work as expected

### Session history
- Every action is logged in the right sidebar with a timestamp
- Colour-coded: green for LIVE events, red for CLEARED
- **New session** resets the log

### Companion dot
- The Companion button in the sidebar flashes and changes state on every take/clear — demonstrates StreamDeck/Companion integration

---

## How to host on GitHub Pages

1. Fork or clone this repository
2. Ensure `index.html` is in the root of the `main` branch
3. Go to your repository **Settings → Pages**
4. Under **Source**, select `Deploy from a branch` → `main` → `/ (root)`
5. Save — your demo will be live at `https://YOUR-USERNAME.github.io/synod-demo` within a minute

---

## How to run locally

No build step needed. Just open `index.html` in any browser:

```bash
# macOS / Linux
open index.html

# Windows
start index.html
```

Or drag the file into a browser window.

---

## Differences from the full system

| Feature | Demo | Full system |
|---------|------|-------------|
| Member database | 26 sample members | 505 GS members |
| VMix connection | Simulated | Real API integration |
| Overlay status | Simulated (650ms delay) | Polls VMix XML every 2s |
| Session log export | Not available | Excel export (.xlsx) |
| Setup / config | Not available | Full Setup tab |
| Keyboard shortcuts | Not active | Fully configurable |
| Multi-operator | Single browser | WebSocket multi-operator |
| Companion/StreamDeck | Visual only | Live WebSocket events |

---

## Full system

The production application is at **[synod-titles](https://github.com/YOUR-USERNAME/synod-titles)** — a Node.js local server with the complete 505-member database, real VMix API integration, Excel session log export, keyboard shortcuts, and multi-operator WebSocket support.

---

## License

MIT
