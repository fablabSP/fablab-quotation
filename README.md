# SP FabLab — Quotation Generator

A self-contained, browser-based quotation tool for **SP FabLab** staff. No installation, no server, no internet connection required — just open the HTML file and go.

---

## Features

### Quote Builder
- **Three quote types** — Internal, External (Preliminary), and External Workshop / Course
- **Colour-coded interface** — blue for Internal, amber for External, green for Workshop / Course
- **Live cost summary** sidebar that updates in real time as you fill in the form
- **Auto-generated reference number prefix** (`SP-TTC/`) for Internal and External quotes

### Materials & Pricing
| Material | Options |
|---|---|
| Acrylic | A7–A0, 3 / 5 / 10mm |
| Acrylic Mirror — Silver | A7–A0, 2mm (TF-SM Optical) |
| Acrylic Mirror — Gold | A7–A0, 2mm (TF-GM Optical) |
| Plywood | A7–A0, 3 / 5 / 15 / 20 / 28mm |
| Vinyl (Large Format) | Small / Medium / Large / Extra Large — flat rate |
| Cardboard Single Wall | A0–A3, 1 / 3 / 5 / 10 / 15mm |
| Cardboard Double Wall | A0–A3, 5 / 10 / 15mm |
| 3D Print — PLA / PETG | Weight (g) + 🎨 Colour Mode surcharge |
| Gypsum Powder | Round / Hexagon / Cube / Others |

### Machine Rates
| Machine | Rate |
|---|---|
| 3D Printer | $5.00 / hr |
| Laser Cutter | $40.50 / hr |
| Large Format Printer | $45.00 / hr |
| Cardboard Cutter | $45.00 / hr |
| CNC | $45.00 / hr |

All rates are editable in the **Materials & Rates** tab.

### Fees & Extras
- **Design Fee** — percentage or fixed amount
- **Expedited Work** — 50% / 75% / 100% urgency surcharge
- **Student Helpers** — $11.00/hr
- **Staff Charges** — rate × hours × number of staff *(External / Workshop only)*
- **Project Expenses** — lump sum *(External / Workshop only)*

### 3D Print Colour Mode
| Mode | Surcharge |
|---|---|
| Single Colour | None |
| Multi-Colour, Same Material | +10% of filament cost |
| Multi-Colour, Different Materials | +15% of filament cost |

### External Quotation
- SP Charge Rate (18.5%) and GST (9%) applied automatically
- TIE portion (11.5%) shown in sidebar for staff reference — never printed on the client document

### Workshop / Course Quotation
- Continuous (date range) or specific dates scheduling
- Course module selector: 3D CAD, 3D Printing, Laser Cut, Programming, Cardboard Sculpt, FabLab Equipment Usage, Custom Item
- Single overall course fee

### Quote Log
- All saved quotes stored in browser localStorage
- Filter by type (All / Internal / External / Workshop)
- Per-entry actions: **View**, **Generate Delivery Order**, **Duplicate**, **Edit**, **Delete**
- **Edit mode** — loads quote back into builder; Save becomes Update; yellow banner shown
- **FY Summary** sidebar — grand total, count, and breakdown by category per financial year (Apr–Mar)
- **Download FY Summary (CSV)** — spreadsheet of all quotes in the selected FY

### Backup & Restore
- **⬇ Backup** — exports all saved quotes as a dated CSV file
- **⬆ Restore** — imports a backup CSV and writes quotes into localStorage; new entries are added, existing entries are updated

### Delivery Order (DO)
- Generated from any saved quote in the log
- Lists all items and quantities (no pricing)
- Includes client signature / acknowledgement block
- Filename auto-formatted as `DO_RefNo_ClientName`

### Materials & Rates Tab
- Edit all material prices and machine rates live
- Add or remove machines
- Changes apply for the current session; update the HTML source for permanent changes

### Other
- **Light / Dark mode** toggle (🌙 / ☀️) — preference saved to localStorage
- **↺ Reset** — full clear of all builder fields, fees, workshop data, and edit state
- **Preview** modal always renders in light mode (print-ready document)
- Works fully **offline** — no CDN or external dependencies at runtime

---

## Usage

1. Download `fablab-quotation-v2.html`
2. Open it in **Chrome** or **Edge** (recommended for best print-to-PDF experience)
3. Select a quote type, fill in project details, add line items, and review the live summary
4. Click **💾 Save** to log the quote, then **🖨 Print** to save as PDF

> **Tip:** Use *Save as PDF* in the browser print dialog. The filename is pre-filled as `RefNo_ClientName`.

---

## Backup & Restore (Changing PCs)

Quote Log data is stored in your browser's localStorage and does **not** sync across computers automatically.

**To move your data to a new PC:**

1. On the old PC → Quote Log → **⬇ Backup** → save the `.csv` file
2. Copy both `fablab-quotation-v2.html` and the backup CSV to the new PC
3. Open the HTML file → Quote Log → **⬆ Restore** → select the CSV
4. All quotes are restored instantly

---

## File Structure

```
fablab-quotation-v2.html   ← entire application (single file, no dependencies)
README.md                  ← this file
```

---

## Quotation Types — Quick Reference

| | Internal | External | Workshop / Course |
|---|---|---|---|
| Interface colour | Blue | Amber | Green |
| Ref No. prefix | `SP-TTC/` | `SP-TTC/` | None |
| SP Charge Rate (18.5%) | ✗ | ✓ | ✓ |
| GST (9%) | ✗ | ✓ | ✓ |
| Internal Vires block | ✓ | ✗ | ✗ |
| Staff Charges | ✗ | ✓ | ✓ |
| Project Expenses | ✗ | ✓ | ✓ |
| Course module selector | ✗ | ✗ | ✓ |
| Line items & accessories | ✓ | ✓ | ✗ |

---

## Printing

- Always use **Save as PDF** in the browser print dialog
- Quotation filename format: `SP-TTC-2026-001_John_Tan.pdf`
- Delivery Order filename format: `DO_SP-TTC-2026-001_John_Tan.pdf`
- Store PDFs in SharePoint under `quotation/internal` or `quotation/external`

---

## Notes

- Quote Log is **browser-local** — use the same browser and computer, or back up regularly
- Prices edited in the Materials & Rates tab apply to the **current session only**; edit the HTML source for permanent price changes
- The printed quotation is client-ready; the TIE charge note and internal Vires details are only shown where relevant

---

## Developed For

**SP FabLab**  by Louis Goh & Claude AI
