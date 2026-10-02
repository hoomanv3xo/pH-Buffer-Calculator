# pH & Buffer Calculator

A single-page, dependency-free HTML/CSS/JS tool for computing pH and exploring
buffer chemistry.

## Features

- **Strong acid/base mode** — exact pH from a concentration, including water's
  own autoionization (matters below ~10⁻⁶ M).
- **Weak acid/base mode** — presets for common weak acids and bases (acetic
  acid, ammonia, etc.) or a custom pKa/pKb. Solves the charge balance
  numerically rather than relying on the √(Ka·C) approximation, and shows
  that approximation alongside the exact answer.
- **Buffer mode** — Henderson–Hasselbalch calculator from [HA], [A⁻], and
  volume. Includes:
  - A slider to add strong acid or base and see the resulting pH shift and
    buffer capacity (β).
  - Warnings when the buffer is exhausted or the ratio falls outside the
    effective range (pKa ± 1).
  - A "design a buffer" helper that converts a target pH and total
    concentration into the [HA]/[A⁻] amounts needed.
- Live pH scale indicator, dark/light theme support, responsive layout.

## Usage

Open `ph-buffer-calculator.html` directly in any modern browser — no build
step, server, or dependencies required. All calculations run client-side in
vanilla JavaScript.

## Assumptions & limitations

- Calculations assume 25 °C and ideal (dilute) solutions; activity
  coefficients are not modeled, so accuracy degrades above ~0.5 M.
- The buffer slider ignores dilution from the volume of acid/base added.
- Covers monoprotic acids/bases only (no polyprotic systems like phosphate
  or carbonic acid yet).

## Possible extensions

- Polyprotic acid/base support (phosphate, carbonic acid systems).
- A live titration curve reusing the same solver.
- Export/share a given scenario via URL parameters.

## Tech

Plain HTML, CSS (custom properties for theming), and JavaScript. No
frameworks, no build tools, no external JS libraries.

