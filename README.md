# KDP Market Intelligence — v1.0.0 (Standalone Windows Edition)

A local-first desktop research and publishing suite for Amazon KDP. Runs as a single self-contained Windows executable (`KDP_Intel.exe`) with a local SQLite database—no cloud accounts, subscriptions, or external database setup required.

---

## Key Features

### Market Research & Tracking
- **Keyword Research & Autocomplete:** Pulls Amazon autocomplete suggestions with 24-hour local TTL caching and demand/opportunity scoring (US, UK, DE).
- **BSR Tracker & SERP Analyzer:** Capture and track book BSR, pricing, review velocity, and competition scores over time.
- **Niche Watchlist:** Pin top keywords and ASINs from anywhere in the dashboard with one-click star toggles and marketplace filtering.
- **One-Click CSV Exports:** Export researched keywords or tracked books directly to `.csv` for Excel or Amazon Ads bulk sheets.

### KDP Publishing Tools
- **7-Slot Backend Keyword Packer:** Strips title/subtitle duplicates and stop-words, then packs unique terms into Amazon's exact 7 slots (≤ 50 UTF-8 bytes each).
- **Cover & Spine Dimension Calculator:** Computes full cover dimensions (inches, mm, and 300 DPI pixels) and spine-text eligibility for Paperback and Hardcover (Case Laminate).
- **Royalty & Break-Even ACOS Calculator:** Estimates net royalty per sale, print/delivery cost, minimum list price, break-even ACOS, and max Ads CPC for eBook, Paperback, and Hardcover.
- **Metadata Compliance Checker:** Audits titles, subtitles, and backend slots for KDP-prohibited terms, 200-character title caps, and 50-byte overflows.
- **Description HTML Formatter:** Converts lightweight Markdown (`##`, `**bold**`, `*italic*`, `- bullets`) into KDP-allowed HTML with a live preview and 4,000-character validator.

### Desktop & Data Reliability
- **System Tray Integration:** Single-instance protection, one-click dashboard launch, manual SQLite backup/restore (with automatic `pre_restore_*.db` safety snapshots), and a **Start with Windows** toggle.
- **Automated Maintenance:** Weekly background SQLite backups (pruned after 30 days) and rotating application logs (`kdp_intel.log`).

---

## Installation & Quick Start

1. Download `KDP_Intel_Release_YYYYMMDD.zip` from the **Assets** section below.
2. Extract the archive to a permanent folder (e.g., `C:\Tools\KDP_Intel\`).
3. Double-click **`KDP_Intel.exe`**. The local server starts at `http://127.0.0.1:8000` and opens automatically in your browser.
4. *(Optional)* Right-click the indigo **K** icon in the Windows system tray and enable **Start with Windows** to launch silently (`--no-browser`) on login, or run `install_startup.ps1`.

> **Note:** All data (`kdp_intel.db`, `backups\`, and `kdp_intel.log`) is stored locally in the same folder as `KDP_Intel.exe`.

---

## SHA256 Checksum Verification

Verify the integrity of the downloaded archive in PowerShell before extracting:

```powershell
Get-FileHash .\KDP_Intel_Release_20261121.zip -Algorithm SHA256
