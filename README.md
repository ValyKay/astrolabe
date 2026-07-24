# ✦ Astrolabe — Offline Birth Chart

A private, offline natal (birth) chart generator in a **single HTML file**. No accounts, no server, no tracking, no dependencies — your birth details never leave your device.

## Features

- **Single file, zero dependencies** — the entire app (markup, styles, astronomy engine, chart renderer) lives in `index.html`. Open it in any modern browser, even without an internet connection.
- **Full natal chart** — geocentric ecliptic positions for the Sun, Moon, and all eight planets (Mercury through Pluto), rendered as an interactive SVG chart wheel.
- **Optional birth time** — turning on birth time (with UTC offset, longitude, and latitude) unlocks your Ascendant and equal houses.
- **Honest about uncertainty** — without a birth time, the app uses a local-noon estimate and tells you when the Moon changes sign during your birth date or when an aspect depends on the exact time, instead of pretending to more precision than it has.
- **Major aspects** — conjunctions, sextiles, squares, trines, and oppositions with standard orbs, drawn on the wheel and summarized in the reading.
- **Chart summary & reading** — the "big three" (Sun, Moon, Rising), dominant element and mode, Moon phase, and a short reflective interpretation.
- **Print / save as PDF** — a dedicated print stylesheet produces a clean, ink-friendly chart page.
- **Private by design** — inputs are saved only in your browser's `localStorage` (with a one-click clear button). Nothing is ever sent anywhere.

## Usage

1. Open `index.html` in a browser (or visit the live demo).
2. Enter a name and date of birth (1900–2100).
3. Optionally toggle **birth time** and fill in the time, UTC offset, longitude, and latitude to reveal the Ascendant and houses.
4. Click **Reveal my birth chart**.

## How the astronomy works

- Planetary positions are computed from the Keplerian orbital elements in **Standish's JPL "Approximate Positions of the Planets" Table 1** (valid 1800–2050), solved with Newton–Raphson iteration on Kepler's equation and converted to geocentric ecliptic longitudes of date. Accuracy is roughly **±1°** within 1800–2050; dates from 2051–2100 are extrapolated and unverified.
- The Sun and Moon use compact trigonometric series; the Ascendant comes from the local sidereal time and the standard rising-sign formula.
- Houses use the **equal house** system. Latitudes are limited to ±66° — polar-region charts are not supported.

## Limitations

- Not intended for professional-grade ephemeris accuracy (positions can be off by up to ~1°, which matters near sign cusps).
- Equal houses only; no Placidus or other quadrant systems.
- No time-zone database — you supply the UTC offset yourself (remember historical daylight saving rules for your birth date).

## Disclaimer

Astrolabe offers symbolic, reflective interpretations for personal exploration — not scientific prediction or professional advice.
