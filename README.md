# zmk-config-corneft

Konfiguracja ZMK dla **Corne FT** (klasyczny Corne 6×3+3) - upgrade z `zmk-config-cornekbh` na ZMK main.

## Hardware

- Shield: `corne` (oficjalny, w upstream ZMK)
- Kontrolery: 2× nice!nano v2
- Wyświetlacze: 2× nice!view (po jednym na każdej połówce)
- Per-key RGB: 27 LED WS2812 na każdej połówce (6 underglow + 21 per-key)
- 42 klawisze (3 rzędy × 6 kolumn + 3 thumb na stronę)

## Co się zmieniło względem `zmk-config-cornekbh`

| | cornekbh (stare) | corneft (nowe) |
|---|---|---|
| ZMK revision | `v0.3` | `main` |
| Board | `nice_nano_v2` | `nice_nano//zmk` |
| Workflow | `@v0.3` | `@main` |
| Nazwa BT | `CorneKBH` | **`Corne FT`** |
| RGB | zakomentowany | **aktywny** |
| nice!view config | zakomentowany | **aktywny** |
| RGB controls | brak w keymapie | **dodane w ADJ** |

## Warstwy

| # | Nazwa | Funkcja |
|---|-------|---------|
| 0 | DEF | QWERTY base |
| 1 | NAV | Strzałki, numpad, BT |
| 2 | SYM | Symbole, brackets |
| 3 | ADJ | F-keys, system, **RGB controls**, bootloader |
| 4 | EXTRA | Mouse emulation |

## RGB w warstwie ADJ (prawa strona)

| Pozycja | Funkcja |
|---------|---------|
| U | RGB toggle (włącz/wyłącz) |
| I | następny efekt |
| O | hue + (kolor) |
| P | hue − |
| J | brightness + |
| K | brightness − |
| L | saturation + |

## ZMK Studio

Aktywne. Lewa połówka ma snippet `studio-rpc-usb-uart`.

`studio_unlock` jest w warstwie ADJ pod klawiszem `G` (lewa ręka, środkowy rząd).

## Build

GitHub Actions buduje 3 firmware automatycznie:
- `corne_left-nice_nano-zmk.uf2`
- `corne_right-nice_nano-zmk.uf2`
- `settings_reset-nice_nano-zmk.uf2`

## Flashowanie

1. Lewa USB → 2× reset → przeciągnij `corne_left-...uf2` na pendrive `NICENANO`
2. Prawa USB → 2× reset → `corne_right-...uf2`
3. Połącz TRRS → klawiatura **"Corne FT"** w BT
