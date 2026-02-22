# Quran Tajweed

Open-source tajweed rule annotations for the entire Quran, with configurable color mapping for developers building color-coded Mushaf displays.

## What's Included

### Tajweed Annotations
Character-level tajweed rule markers for every ayah in the Quran (Hafs an Asim). Each annotation specifies:
- The **tajweed rule** being applied
- The **start/end character offsets** within the ayah text

### Supported Rules

| Rule | Description | Default Color |
|------|------------|---------------|
| `madd` | Elongation (2/4/6 harakah) | Red `#DD0008` |
| `ghunnah` | Nasalization | Green `#169777` |
| `idgham_ghunnah` | Assimilation with nasalization | Green `#169777` |
| `idgham_no_ghunnah` | Assimilation without nasalization | Green `#169200` |
| `idgham_shafawi` | Lip assimilation | Green `#58B800` |
| `qalqalah` | Echo/bounce on certain letters | Dark Blue `#4050FF` |
| `ikhfa` | Concealment | Purple `#9400A8` |
| `ikhfa_shafawi` | Lip concealment | Pink `#D500B7` |
| `iqlab` | Conversion (noon to meem) | Orange `#FF7E1E` |
| `hamzat_wasl` | Silent hamza | Gray `#AAAAAA` |
| `lam_shamsiyyah` | Solar lam | Gray `#AAAAAA` |
| `silent` | Unpronounced letters | Gray `#AAAAAA` |

### Color Schemes
- **Dar Al-Maarifa standard** — Matches the printed Mushaf Al-Tajweed
- **AlQuran Cloud standard** — Widely used digital standard
- **Colorblind-safe palette** — Alternative for deuteranopia, protanopia, tritanopia

## Directory Structure

```
annotations/      # Tajweed rule annotations per surah (JSON)
colors/           # Color scheme definitions (JSON)
flutter/          # Dart utilities for rendering tajweed in Flutter
```

## Usage

```json
{
  "surah": 1,
  "ayah": 1,
  "annotations": [
    { "rule": "madd_6", "start": 12, "end": 14 },
    { "rule": "ikhfa", "start": 20, "end": 22 }
  ]
}
```

```dart
// Apply color for a tajweed rule
Color color = TajweedColors.forRule('ikhfa'); // Returns #9400A8
```

## Data Sources & Attribution

- Primary annotations: [cpfair/quran-tajweed](https://github.com/cpfair/quran-tajweed) (CC BY 4.0)
- Color standard reference: [AlQuran Cloud](https://alquran.cloud/tajweed-guide)
- Flutter tokenizer reference: [rovshan-b/Quran-flutter-tajweed](https://github.com/rovshan-b/Quran-flutter-tajweed)

## License

MIT — Free for personal and commercial use. See [LICENSE](LICENSE).
