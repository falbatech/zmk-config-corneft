:::writing{variant=“standard” id=“35718”}

zmk-config-corneft

PL

Konfiguracja ZMK dla Corne FT - klawiatura ergonomiczna FalbaTech.

Hardware
	•	Shield: corne (oficjalny w upstream ZMK)
	•	Kontrolery: 2× nice!nano v2
	•	Wyświetlacz: nice!view (Sharp Memory LCD, niskie zużycie)
	•	RGB: per-key WS2812, 27 LED na każdej połówce (6 underglow + 21 per-key)
	•	42 klawisze (3 rzędy × 6 kolumn + 3 thumb na stronę)

Warstwy

#	Nazwa	Funkcja
0	DEF	QWERTY base
1	NAV	Strzałki, nawigacja, numpad
2	SYM	Symbole, brackets
3	ADJ	F-keys, system, RGB controls, BT controls
4	EXTRA	Mouse emulation

ZMK Studio

Aktywne. Procedura odblokowania (jednakowa we wszystkich klawiaturach FalbaTech FT):

Trzymaj oba thumby aktywujące warstwy systemowe → wciśnij skrajny lewy górny klawisz.

Po odblokowaniu klawiatura jest edytowalna z:
zmk.studio￼

Bluetooth - obsługa 5 urządzeń

Klawiatura obsługuje 5 niezależnych profili Bluetooth. Przełączanie między urządzeniami (laptop, telefon, tablet, służbowy, dodatkowe) odbywa się w warstwie systemowej (ADJ):

Klawisz	Funkcja
Z	Profil BT 0 (urządzenie #1)
X	Profil BT 1 (urządzenie #2)
C	Profil BT 2 (urządzenie #3)
V	Profil BT 3 (urządzenie #4)
B	Profil BT 4 (urządzenie #5)
N	Wyczyść aktywny profil BT
M	Wyczyść wszystkie profile BT (reset awaryjny)
,	Tryb USB (wyjście kabel)
.	Tryb Bluetooth (wyjście bezprzewodowe)

Przykładowe użycie: ADJ + Z = przełącz na laptopa, ADJ + X = przełącz na telefon.

Parowanie nowego urządzenia:
	1.	Trzymaj ADJ (mo) i wciśnij Z (lub inny pusty profil)
	2.	Klawiatura zaczyna nadawać
	3.	Na komputerze/telefonie znajdź “Corne FT” w liście Bluetooth
	4.	Sparuj

Reset sparowań jeśli coś nie działa:
	•	ADJ + N - wyczyść aktualny profil
	•	ADJ + M - wyczyść WSZYSTKIE profile (potem musisz sparować od zera)

RGB controls

Wszystkie w warstwie ADJ (środkowy rząd):

Klawisz	Funkcja
Q	RGB on/off
W	Zmiana efektu
E	Hue +
R	Hue -
T	Brightness +
Y	Brightness -
U	Saturation +
I	Saturation -

Build

GitHub Actions buduje 3 firmware automatycznie:
	•	corne_left-nice_nano-zmk.uf2 (lewa połówka, USB)
	•	corne_right-nice_nano-zmk.uf2 (prawa połówka)
	•	settings_reset-nice_nano-zmk.uf2 (firmware reset sparowań, awaryjny)

Flashowanie
	1.	Lewa połówka USB - 2× szybko reset - przeciągnij corne_left-...uf2 na pendrive NICENANO
	2.	Prawa połówka USB - 2× reset - przeciągnij corne_right-...uf2
	3.	Połącz obie kablem TRRS
	4.	Sparuj “Corne FT” przez Bluetooth na komputerze

Wsparcie

FalbaTech - https://falbatech.click

⸻

EN

ZMK configuration for Corne FT - ergonomic FalbaTech keyboard.

Hardware
	•	Shield: corne (official upstream ZMK shield)
	•	Controllers: 2× nice!nano v2
	•	Display: nice!view (Sharp Memory LCD, low power consumption)
	•	RGB: per-key WS2812, 27 LEDs on each half (6 underglow + 21 per-key)
	•	42 keys (3 rows × 6 columns + 3 thumb keys per side)

Layers

#	Name	Function
0	DEF	QWERTY base
1	NAV	Arrows, navigation, numpad
2	SYM	Symbols, brackets
3	ADJ	F-keys, system, RGB controls, BT controls
4	EXTRA	Mouse emulation

ZMK Studio

Enabled. Unlock procedure (same across all FalbaTech FT keyboards):

Hold both thumb keys activating system layers → press the top left key.

After unlocking, the keyboard can be configured from:
zmk.studio￼

Bluetooth - 5 device support

The keyboard supports 5 independent Bluetooth profiles. Switching between devices (laptop, phone, tablet, work device, additional devices) is handled in the system layer (ADJ):

Key	Function
Z	BT Profile 0 (device #1)
X	BT Profile 1 (device #2)
C	BT Profile 2 (device #3)
V	BT Profile 3 (device #4)
B	BT Profile 4 (device #5)
N	Clear active BT profile
M	Clear all BT profiles (emergency reset)
,	USB mode (wired output)
.	Bluetooth mode (wireless output)

Example usage: ADJ + Z = switch to laptop, ADJ + X = switch to phone.

Pairing a new device:
	1.	Hold ADJ (mo) and press Z (or another empty profile)
	2.	The keyboard starts advertising
	3.	Find “Corne FT” in the Bluetooth device list on your computer/phone
	4.	Pair

Reset pairings if something does not work:
	•	ADJ + N = clear current profile
	•	ADJ + M = clear ALL profiles (after that you need to pair from scratch)

RGB controls

All controls are located in the ADJ layer (middle row):

Key	Function
Q	RGB on/off
W	Change effect
E	Hue +
R	Hue -
T	Brightness +
Y	Brightness -
U	Saturation +
I	Saturation -

Build

GitHub Actions automatically builds 3 firmware files:
	•	corne_left-nice_nano-zmk.uf2 (left half, USB)
	•	corne_right-nice_nano-zmk.uf2 (right half)
	•	settings_reset-nice_nano-zmk.uf2 (emergency pairing reset firmware)

Flashing
	1.	Left half USB - press reset 2× quickly - drag corne_left-...uf2 onto the NICENANO drive
	2.	Right half USB - press reset 2× - drag corne_right-...uf2
	3.	Connect both halves using the TRRS cable
	4.	Pair “Corne FT” over Bluetooth on your computer

Support

FalbaTech - https://falbatech.click
:::
