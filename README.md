# MapBoard

**A lightweight world map board for Windows** — color the globe, mark positions, track forces, follow the news, and export a board you can share.

MapBoard is a desktop app for building interactive scenario boards: grand-strategy style maps, crisis dashboards, teaching aids, campaign notes, or personal geopolitics scratchpads. Everything lives in plain project files you own.

<a href="https://github.com/AppsByJames/MapBoard/releases/tag/v1.0.0" download style="font-size: 24px; font-weight: bold;">Download Here</a>

---

<img width="1919" height="1029" alt="MapBoard_US_IRAN_WAR" src="https://github.com/user-attachments/assets/7dbb82c5-925e-4c3f-88aa-c01ef03c3ac7" />

## Highlights

| | |
|---|---|
| **Paint the world** | Click countries to recolor them; style names, focus a nation, or clear back to the default fill. |
| **Place what matters** | Notes, free text, icons (markers, isometric sprites, emoji, flags), and force tokens. |
| **Draw freely** | Brush, pencil, lines, shapes, rail, spray, eraser, and more — strokes stay locked to geography under pan/zoom. |
| **Units in 2D & 3D** | Land, naval, air, and strategic tokens with faction colors, status, heading, and optional 3D figurines (including commercial infrastructure). |
| **Live context** | RSS headlines, market quotes, and a floating Journal (notes, objectives, notifications, news). |
| **AI-assisted boards** | Optional multi-provider LLM tab: describe what you want, generate map objects, apply them in one step. |
| **Your data, your files** | Projects are JSON under your Documents folder. Export a high-quality PNG or JPEG with a subtle watermark. |

---

## Who it’s for

- **Scenario builders** — wargames, campaign planning, alternate history
- **Analysts & hobbyists** — annotate theaters with notes, layers, and provenance-friendly fields
- **Educators & presenters** — paint regions, drop pins, export a clean map image
- **Anyone who thinks better on a map** — news, markets, and personal notes in one dark, focused workspace

---

<img width="1919" height="1029" alt="Screenshot 2026-07-29 114138" src="https://github.com/user-attachments/assets/735031f9-8890-4dbc-a470-3e0463990162" />

## Feature tour

### Interactive world map

- Natural Earth–based country outlines (including many small countries and islands)
- Pan, scroll-zoom toward the cursor, fit world (middle-click or zoom out)
- Focus on a selected country; toggle country names and ocean/sea labels
- Optional **cities & states** for a country (major cities and admin borders when enabled)
- Right-click the map for place / zoom / copy / export shortcuts

### Tools (one-shot placement)

Placement tools drop a single item, then return to **Select** so you don’t spam the board.

| Tool | Shortcut | What you can do |
|------|----------|-----------------|
| **Select** | `V` | Click countries or objects; edit them in the side panel; paint the selection |
| **Note** | `N` | Pin shapes (square, circle, triangle, diamond, hexagon) at S / M / L |
| **Text** | `T` | Free map labels with size, bold, italic, and outline |
| **Draw** | `D` | Freehand and shape strokes; width from XS–L |
| **Icons** | `I` | Libraries: Markers · Iso · Emoji · Flags |
| **Units** | `U` | Force / facility tokens; type filters; **3D** toggle; size, status, heading, national skins |

**Also useful**

- **Space + drag** or **left-drag** empty map → pan  
- **Ctrl+Z** → undo  
- Arrow keys nudge selected objects (**Shift** = larger step)  
- Right-click a note / icon / unit / text → delete  

### Colors & country data

- Palette swatches plus hex colors (`#RRGGBB` / `#AARRGGBB`)
- Clear to default fill (checkerboard / `none`)
- Per-country stats and metadata as editable JSON (currency, tags, style, optional analyst fields)
- Copy coordinates in familiar *latitude, longitude* order; **Import coordinates** accepts decimal or DMS and drops a pin

### Journal

A floating window over the map:

- **Notes** — free-form entries with accent color and timestamps  
- **Objectives** — track status (available / current / completed / failed)  
- **Notifications** — attention items become **map tiles** along the top (`!` = attention; left-click opens Journal, right-click dismisses)  
- **News** — clippings (including from RSS)

Saved with your user data so boards and personal notes stay separate when you want them to.

### Side panel tabs

| Tab | Purpose |
|-----|---------|
| **JSON** | Edit the selected country or object; import one or many annotation objects when nothing is selected |
| **RSS** | Color-coded multi-feed headlines, unread dots, manage subscriptions, refresh, open links, send to Journal |
| **Markets** | Spot quotes (indices, FX, rates, commodities, crypto, ETFs, equities); green/red day change; search catalog or add custom symbols; drag to reorder |
| **Layers** | Show/hide and lock built-in layers and project groups |
| **LLM** | Generate board objects from a prompt (optional map context + web search when supported); apply results to the map |

### AI generation (optional)

Bring your own API key for a supported provider (OpenAI, SpaceXAI / xAI, Anthropic, or Google Gemini). Write a prompt, generate structured map objects, preview, and apply. Multi-turn history and provider preferences stay in your Documents folder — keys are never baked into the app.

### Projects & export

| Action | Shortcut |
|--------|----------|
| New | `Ctrl+N` |
| Open | `Ctrl+O` |
| Save | `Ctrl+S` |
| Save As | `Ctrl+Shift+S` |

- Unsaved changes show a `•` in the title and prompt before discard  
- Export image: high-resolution PNG or JPEG (map context menu or export action)  
- Branding: discreet **MapBoard** / **Apps By James** watermark on exports  

### Power-user automation

A small headless **CLI** can validate project files and apply annotation batches — handy for scripts and pipelines without opening the UI.

---

## Requirements

- **Windows**
- [.NET 8](https://dotnet.microsoft.com/download/dotnet/8.0) (or a self-contained build that includes the runtime)

---

## Get started

### Run from source

```bash
dotnet run --project MapBoard.csproj
```

Or open the solution in Visual Studio / Rider and start the MapBoard app project.

### Portable build

A self-contained single-file publish embeds map data and icon assets so one executable is enough on another PC. Folder-style publishes need the full output folder (app + `Data` + `Assets`).

### First launch

MapBoard creates a friendly tree under your user documents:

```
Documents/MapBoard/
  maps/       ← project boards (default board seeded once)
  journal/    ← notes, objectives, notifications, news
  llm/        ← optional AI settings & chat history
  markets/    ← market panel preferences
  rss/        ← feed lists & settings
```

Your boards stay visible for backup, sync, and sharing. Country geometry ships with the app; it is not copied into Documents.

---

## Tips

1. **Select first** — paint and JSON editing follow the current selection.  
2. **One-shot tools** — pick an icon or unit from the bottom strip, place once, then refine under Select.  
3. **Zoom smart labels** — markers scale with zoom to reduce clutter; unit/icon callsigns hide when zoomed far out.  
4. **Batch import** — with nothing selected, paste a JSON array of notes/texts/icons/units/drawings into the Object panel and Apply (one undo undoes the batch).  
5. **Full projects vs. snippets** — use **Open** for complete board files; use **Apply** only for annotation objects.  
6. **RSS + Journal** — follow feeds in-panel, then push a headline into Journal News when you want it kept with the campaign.  

---

## Privacy & data

- Map projects and journal content live on **your machine** under Documents.  
- RSS and Markets fetch only what you configure (your feeds and symbols).  
- LLM calls go to the provider **you** choose, with **your** key; the app does not require an account.  
- No telemetry is required to use core board features.

---

## What’s next (publicly)

Ideas under consideration (not commitments):

- Easier sharing of boards between users  
- Professional installers and clearer download packages for Windows  
- Continued unit, icon, and journal polish  

Feature requests and feedback are welcome wherever the project is published.

---

## Credits

**MapBoard** — *Apps By James*

Country boundaries derived from [Natural Earth](https://www.naturalearthdata.com/) data. Market quotes may use public quote providers configured in the app. Icon and flag assets are bundled for offline use on the board.

---

## License & support

Use and distribution terms follow the project repository. Support and donation options may appear in-app as they become available.

---

*Paint the board. Mark the world. Own the file.*
