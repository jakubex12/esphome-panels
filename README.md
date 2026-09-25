# esphome-panels

Panele dotykowe LVGL do sterowania muzyką (Music Assistant w Home Assistant), ESPHome 2026.9.

| Plik | Płytka | Co robi |
|------|--------|---------|
| `sc01-plus.yaml` | WT32-SC01 Plus (ESP32-S3, 480x320, PSRAM) | Salon: „Teraz gra” z okładką pobieraną z HA i animowanym korektorem w tle, zakładki Radio (4 stacje) i Muzyka (6 playlist) |
| `round-cyd.yaml` | ESP32-2424S012 „Round CYD” 1.28" (ESP32-C3, 240x240 okrągły) | Biuro: 3 ekrany przesuwane palcem – „Teraz gra” (głośność na łuku, przyciski −/+), Radio, playlisty do pracy |

## Uruchomienie

1. Skopiuj `secrets.yaml.example` do `secrets.yaml` i uzupełnij.
2. W `substitutions` na górze pliku ustaw swój `player` (encja `media_player` z Music Assistant),
   URI stacji/playlist, a w `sc01-plus.yaml` także `ha_url` (adres HA w LAN – z niego idą okładki).
3. Skompiluj i wgraj z ESPHome.
4. W HA → Ustawienia → Urządzenia → ESPHome → (panel) → koło zębate zaznacz
   **„Zezwól urządzeniu na wykonywanie akcji Home Assistant”** – bez tego przyciski nic nie robią.

URI radia i playlist zwracają akcje `music_assistant.get_library` / `music_assistant.search`.

`images/` – logotypy stacji radiowych używane na przyciskach (znaki towarowe należą do ich właścicieli).
