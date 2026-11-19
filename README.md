# NeuroAltar

Lokalna aplikacja do **Neuroshimy: Ostatniej Ery**: karty postaci, Panel MG,
pięć potyczek, Bestiariusz, Ekwipunek, Pojazdy, Wiedza MG i kości.

## Aktualna wersja: 1.0.1 — 19 listopada 2026

[Pobierz wydanie 1.0.1](https://github.com/Ppdnox/NeuroAltar/releases/tag/v1.0.1)

- [Aplikacja macOS — Apple Silicon](https://github.com/Ppdnox/NeuroAltar/releases/download/v1.0.1/NeuroAltar-1.0.1-macOS-Apple-Silicon.zip)
- [Źródła projektu 1.0.1](https://github.com/Ppdnox/NeuroAltar/releases/download/v1.0.1/NeuroAltar-1.0.1-source.zip)
- [Lista zmian i instrukcja dla Windows](WINDOWS-ZMIANY-2026-11-19.md)
- [Changelog](CHANGELOG.md)
- [Sumy SHA-256](https://github.com/Ppdnox/NeuroAltar/releases/download/v1.0.1/SHA256SUMS.txt)

Wydanie poprawia stosy amunicji, masy narzędzi, ładunki medyka, wybór Ulubionej
broni i przywracanie fobii. Zawiera także dzisiejsze poprawki doświadczenia,
trybów edycji/gry, podglądu sztuczek i opisów przeciwników.

Weryfikacja: **618 testów TypeScript i 121 testów Rust**, kontrole kodu,
build macOS i próby natywne — PASS. macOS 13.3 lub nowszy, Apple Silicon.
Podpis aplikacji jest ad hoc, bez notaryzacji. Instalator i testy Windows
są prowadzone oddzielnie; nie ma ich w tym wydaniu.

## Instalacja i dane

Rozpakuj aplikację i zastąp dotychczasowy NeuroAltar po jego zamknięciu.
Aktualizacja z 1.0.0 zachowuje profil i dane. Nie kasuj katalogu danych.
Historyczne przejście z 24E do 1.0.0 na Macu było jednorazowym pustym startem,
wybranym przez użytkownika; nie należy go powtarzać przy 1.0.1 ani na Windows.

## Praca nad wersją Windows

Pobierz **NeuroAltar-1.0.1-source.zip** i przekaż je GPT/Codexowi razem z
[WINDOWS-ZMIANY-2026-11-19.md](WINDOWS-ZMIANY-2026-11-19.md).
Zachowaj lokalne poprawki Windows i bazę, a następnie porównaj i połącz zmiany.
Paczka zawiera katalog źródeł, `MANIFEST.json` i kompletną historię w Git bundle.
Commit źródeł: `f975256b63a45cb6a168e2ac6df4416b5f2c6246`.

To repozytorium służy **dystrybucji**. Automatyczne archiwa GitHuba „Source code”
obejmują repo dystrybucyjne, a nie właściwy projekt aplikacji. Właściwe źródła są
osobnym załącznikiem wydania. Starsze paczki 0.29.5 zachowano jako archiwum.
Bazy użytkowników oraz prywatne PDF/Excel nie są udostępniane.

Made by Dominik *„Polakko”* Stanisławski.
