# zmk-config-corneft

## PL

Konfiguracja ZMK dla **Corne FT** - klawiatury ergonomicznej FalbaTech.

## Hardware

- Shield: `corne` (oficjalny shield upstream ZMK)
- Kontrolery: 2x nice!nano v2
- Wyświetlacz: nice!view, Sharp Memory LCD o niskim poborze energii
- RGB: per-key WS2812, 27 LED na każdej połówce
- 6 LED underglow + 21 per-key LED
- 42 klawisze, 3 rzędy x 6 kolumn + 3 thumb na stronę

## Warstwy

| # | Nazwa | Funkcja |
|---|---|---|
| 0 | `DEF` | QWERTY base |
| 1 | `NAV` | Strzałki, nawigacja, numpad |
| 2 | `SYM` | Symbole, brackets |
| 3 | `ADJ` | F-keys, system, RGB controls, BT controls |
| 4 | `EXTRA` | Mouse emulation |

## ZMK Studio

ZMK Studio jest aktywne.

Procedura odblokowania jest taka sama we wszystkich klawiaturach FalbaTech FT:

> Trzymaj oba thumby aktywujące warstwy systemowe i wciśnij skrajny lewy górny klawisz.

Po odblokowaniu klawiatura jest edytowalna z poziomu przeglądarki:

https://zmk.studio

## Bluetooth - obsługa 5 urządzeń

Klawiatura obsługuje 5 niezależnych profili Bluetooth. Przełączanie między urządzeniami odbywa się w warstwie systemowej `ADJ`.

| Klawisz | Funkcja |
|---|---|
| `Z` | Profil BT 0, urządzenie #1 |
| `X` | Profil BT 1, urządzenie #2 |
| `C` | Profil BT 2, urządzenie #3 |
| `V` | Profil BT 3, urządzenie #4 |
| `B` | Profil BT 4, urządzenie #5 |
| `N` | Wyczyść aktywny profil BT |
| `M` | Wyczyść wszystkie profile BT |
| `,` | Tryb USB |
| `.` | Tryb Bluetooth |

### Przykładowe użycie

- `ADJ + Z` = przełącz na laptop
- `ADJ + X` = przełącz na telefon

### Parowanie nowego urządzenia

1. Wejdź do warstwy `ADJ`.
2. Wciśnij `Z` lub inny pusty profil.
3. Klawiatura rozpocznie nadawanie Bluetooth.
4. Znajdź „Corne FT” w ustawieniach Bluetooth.
5. Sparuj urządzenie.

### Reset sparowań

- `ADJ + N` = wyczyść aktualny profil
- `ADJ + M` = wyczyść wszystkie profile

Po wyczyszczeniu wszystkich profili urządzenia trzeba sparować ponownie od zera.

## RGB controls

Sterowanie RGB znajduje się w warstwie `ADJ`.

| Klawisz | Funkcja |
|---|---|
| `Q` | RGB on/off |
| `W` | Zmiana efektu |
| `E` | Hue + |
| `R` | Hue - |
| `T` | Brightness + |
| `Y` | Brightness - |
| `U` | Saturation + |
| `I` | Saturation - |

## Build

GitHub Actions automatycznie buduje 3 pliki firmware:

- `corne_left-nice_nano-zmk.uf2`
- `corne_right-nice_nano-zmk.uf2`
- `settings_reset-nice_nano-zmk.uf2`

## Flashowanie

1. Podłącz lewą połówkę przez USB.
2. Naciśnij RESET dwa razy szybko.
3. Przeciągnij `corne_left-...uf2` na dysk `NICENANO`.
4. Podłącz prawą połówkę przez USB.
5. Naciśnij RESET dwa razy szybko.
6. Przeciągnij `corne_right-...uf2`.
7. Połącz obie połówki przewodem TRRS.
8. Sparuj klawiaturę jako "Corne FT" przez Bluetooth.

## Wsparcie

FalbaTech  
https://falbatech.click

---

## EN

ZMK configuration for **Corne FT** - ergonomic FalbaTech keyboard.

## Hardware

- Shield: `corne` (official upstream ZMK shield)
- Controllers: 2x nice!nano v2
- Display: nice!view, low power Sharp Memory LCD
- RGB: per-key WS2812, 27 LEDs on each half
- 6 underglow LEDs + 21 per-key LEDs
- 42 keys, 3 rows x 6 columns + 3 thumb keys per side

## Layers

| # | Name | Function |
|---|---|---|
| 0 | `DEF` | QWERTY base |
| 1 | `NAV` | Arrows, navigation, numpad |
| 2 | `SYM` | Symbols, brackets |
| 3 | `ADJ` | F-keys, system, RGB controls, BT controls |
| 4 | `EXTRA` | Mouse emulation |

## ZMK Studio

ZMK Studio is enabled.

The unlock procedure is the same across all FalbaTech FT keyboards:

> Hold both thumb keys activating system layers and press the top left key.

After unlocking, the keyboard can be configured from your browser:

https://zmk.studio

## Bluetooth - 5 device support

The keyboard supports 5 independent Bluetooth profiles. Device switching is handled in the `ADJ` system layer.

| Key | Function |
|---|---|
| `Z` | BT Profile 0, device #1 |
| `X` | BT Profile 1, device #2 |
| `C` | BT Profile 2, device #3 |
| `V` | BT Profile 3, device #4 |
| `B` | BT Profile 4, device #5 |
| `N` | Clear active BT profile |
| `M` | Clear all BT profiles |
| `,` | USB mode |
| `.` | Bluetooth mode |

### Example usage

- `ADJ + Z` = switch to laptop
- `ADJ + X` = switch to phone

### Pairing a new device

1. Enter the `ADJ` layer.
2. Press `Z` or another empty profile.
3. The keyboard starts Bluetooth advertising.
4. Find “Corne FT” in Bluetooth settings.
5. Pair the device.

### Reset pairings

- `ADJ + N` = clear current profile
- `ADJ + M` = clear all profiles

After clearing all profiles, devices must be paired again from scratch.

## RGB controls

RGB controls are located in the `ADJ` layer.

| Key | Function |
|---|---|
| `Q` | RGB on/off |
| `W` | Change effect |
| `E` | Hue + |
| `R` | Hue - |
| `T` | Brightness + |
| `Y` | Brightness - |
| `U` | Saturation + |
| `I` | Saturation - |

## Build

GitHub Actions automatically builds 3 firmware files:

- `corne_left-nice_nano-zmk.uf2`
- `corne_right-nice_nano-zmk.uf2`
- `settings_reset-nice_nano-zmk.uf2`

## Flashing

1. Connect the left half via USB.
2. Press RESET twice quickly.
3. Drag `corne_left-...uf2` onto the `NICENANO` drive.
4. Connect the right half via USB.
5. Press RESET twice quickly.
6. Drag `corne_right-...uf2`.
7. Connect both halves using a TRRS cable.
8. Pair the keyboard as "Corne FT" over Bluetooth.

## Support

FalbaTech  
https://falbatech.click
