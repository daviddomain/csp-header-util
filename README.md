# csp-header-util

Small local utility to parse, edit, and merge **Content-Security-Policy** headers.

## What this app does

The app is a single file: **`index.html`**.
It runs fully local in the browser (including directly via `file://`, with no dev server, no build step, no framework, and no external libraries).

Features:

- Two input fields for **CSP A** and **CSP B**
- Accepts either:
  - a full header line like
    `Header set Content-Security-Policy "..."`
  - or a raw CSP string
- **Analyze** button:
  - only one field filled → parses that single CSP
  - both fields filled → merges both CSPs
- Directives with the same name are merged
- Entries inside each directive are deduplicated (while keeping order as stable as possible)
- Parsed directives are shown in a clear list
- Entries can be removed per directive
- New entries can be added per directive
- Output is regenerated immediately after every change:
  - raw CSP string
  - full `.htaccess` header line
- Both outputs include a **Copy** button

## Usage

1. Open `index.html` in your browser
2. Paste CSP into field A and optionally field B
3. Click **Analyze**
4. Edit entries (remove/add)
5. Copy the generated result
