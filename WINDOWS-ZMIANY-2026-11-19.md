# NeuroAltar — zmiany z 19 listopada 2026 do przeniesienia na Windows

Docelowe wspólne źródła: **1.0.1**. To aktualizacja istniejącej pracy Windows,
nie polecenie rozpoczęcia portu od nowa. Instalator i testy Windows są wykonywane
na domowym PC; wyniki z macOS ich nie zastępują.

## Lista dzisiejszych zmian

### 1. Karta BG: doświadczenie, edycja i pomoc (0.29.6)

- Dodawanie PD w osobnym oknie z potwierdzeniem kwoty, bez edycji całej karty i bez uzasadnienia. Działa przy szkicu, gotowej karcie i podczas potyczki.
- Usuwanie błędnego wpisu PD z potwierdzeniem; suma nigdy nie jest ujemna. Usunięcie PD nie usuwa poziomów ani wyborów postaci.
- Pasek postępu PD i przycisk prowadzący do rozwoju/awansu, uruchamiający edycję, jeśli jest potrzebna.
- Bursztynowy tryb edycji i zielony tryb gry; opis szkicu oraz przyczyny blokady akcji.
- Czerwone ostrzeżenia i wymagania Cech przy konkretnym poziomie/wyborze klasy.
- Wyszukiwany podgląd sztuczek obok ich wyboru: działanie, wymagania, premia Cechy i strona podręcznika; obsługa Escape i fokusu.
- Krótkie opisy 51 przeciwników głównego podręcznika oraz Zombie w Bestiariuszu i wyszukiwarce przeciwników. Bez nadpisywania własnych notatek i kopii w walce.
- Trwałe polecenie `experience` i migracja **015_character_experience.sql**. Ponowienie zapisu nie podwaja PD, odrzucenie szkicu nie cofa potwierdzonego wpisu.

### 2. Formalne wydanie 1.0

- Zakres 24E został zaakceptowany; aplikacja otrzymała numer 1.0.0 i uporządkowane instrukcje/status.
- Na Macu użytkownik jednorazowo poprosił o nowy profil `pl.neuroaltar.app` i pusty start. **Tego resetu nie przenoś na Windows.** Zachowaj jego obecny identyfikator, katalog danych, karty i potyczki.
- Dawne lokalne aplikacje macOS przeniesiono do Kosza. To działanie porządkowe na Macu, nie zadanie do wykonania na PC.

### 3. Ekwipunek i zdolności (1.0.1)

- Strzały i bełty w stosach, np. 20 szt., także w jednym slocie Przedmiot Podręczny; bez masy amunicji. Broń i osobny magazynek nadal pojedynczo w slocie.
- Brakujące źródłowe masy 22 zestawów narzędzi z podręcznika, s. 134–136. Mały kłusownik, Mały rzeźnik i Mały medyk: po **10 kg**. Uzupełnienie także przy odczycie wcześniejszych wpisów z pustą masą; jawne własne masy pozostają bez zmian.
- Mały medyk: **5 klikalnych ładunków**, użycie/przywrócenie kliknięciem. Wspólny licznik z Postojem; samo kliknięcie nie leczy ani nie pobiera materiałów.
- Usunięte pola „Pojemnik” i „W pojemniku”. Zachowana zgodność ze starymi zapisami.
- Ulubiona broń: selektor posiadanych modeli w slotach Broń Biała 1–4 / Broń Dystansowa 1–3, bez duplikatów tego samego modelu. Zachowanie wcześniejszego wyboru, jeśli broń chwilowo nie jest w slocie.
- Liczba modeli: Twardziel 1/2/3/4 na poziomach klasy 1/4/7/10; Złodziej 1 od poziomu 2 i wymagana biegłość; Zwiadowca 1 od poziomu 1, 2 od poziomu 9. Pierwszy model można wybrać już po publikacji karty i skompletowaniu sprzętu.
- Zmiana wybranego modelu wymaga potwierdzenia godziny treningu podczas Długiego odpoczynku. W aktywnej walce wybór jest zablokowany. Sam wybór nie wydaje amunicji ani akcji.
- Dodatkowy atak Ulubioną bronią rozpoznaje właściwe klasy, również Złodzieja i Zwiadowcę.
- Trwałe polecenie `favoriteWeapon`, migracja **016_character_favorite_weapon.sql**; zachowanie historii i obsługa ponowienia zapisu.
- Przywracanie zakończonej fobii i zmiana jej rodzaju; osobna zmiana Cechy jednorazowego początkowego bonusu. Zastępuje poprzednią premię, nie przyznaje następnej. Limit bazowej Cechy 18 pozostaje.
- Wersje aplikacji/pakietów/stopki: **1.0.1**.

Rickert jest indywidualną kartą użytkownika na Macu. Przywrócenie jego Arachnofobii
i zamiana początkowej premii Siła +1 na Inteligencja +1 nie są migracją dla wszystkich
postaci. Nie dodawaj takiej zmiany do seedów ani do globalnych migracji Windows.

## Polecenie dla GPT/Codexa na Windows

Pracuj na istniejącym lokalnym projekcie NeuroAltar dla Windows. Przeczytaj jego
AGENTS.md, sprawdź Git i wersję. Zachowaj bieżące zmiany Windows oraz dane użytkownika;
zrób checkpoint przed integracją. Porównaj otrzymane źródła 1.0.1 z własnym checkoutem,
a następnie przenieś powyższe zmiany. Nie zastępuj całego projektu bez porównania.

Źródło z Maca miało bazę `03f119ce025cdc83e599d170e02836c0cb392122` (0.29.5).
Dzisiejsze kolejne commity to `e39774b8daf180420a725be4a75901fa5fd9f8f1` (0.29.6)
i `998a85ba622ac788c4bc6a160badba903449a40b` (1.0.0); dokładny końcowy commit 1.0.1
znajduje się w `MANIFEST.json` paczki. Historia źródeł jest w dołączonym pliku Git bundle.
Jeśli obie gałęzie mają wspólną bazę, możesz wczytać bundle do osobnej gałęzi i świadomie
połączyć zmiany. Najpierw obejrzyj różnice; nie nadpisuj lokalnej gałęzi ani katalogu danych.

Zachowaj działające ustawienia Windows/NSIS i obecny identyfikator aplikacji Windows.
Plik `src-tauri/tauri.macos.conf.json`, ścieżki `/Users/...` i skrypty lokalnego toolchainu
Maca nie są ustawieniami dla PC. Nie resetuj ani nie odtwarzaj bazy. Migracje 015 i 016
wykonaj w istniejącej kolejności i transakcji; nie zmieniaj migracji 001–014 ani numerów
zastosowanych migracji. Jeśli Windows ma już własną migrację o numerze 015/016, najpierw
porównaj treść i rozwiąż konflikt wersji, bez ponownego zastosowania innej treści pod
numerem już zapisanym w bazie.

Pobierz asset **NeuroAltar-1.0.1-source.zip** z wydania GitHub. Automatyczne linki
GitHuba „Source code (zip/tar.gz)” dotyczą repozytorium dystrybucyjnego i nie są tą paczką.
Repo `Ppdnox/NeuroAltar` przechowuje wydania i archiwa; nie zastępuj jego historii historią
lokalnego projektu bez osobnej decyzji.

Ważne obszary porównania:

- `src/features/character/`, `src/domain/character/`, `src/stores/characterStore.ts`.
- `src-tauri/src/character*.rs`, `src-tauri/src/lib.rs`, migracje 015/016.
- `src/data/bestiary/descriptions.v1.json`, podgląd i wyszukiwanie Bestiariusza.
- `src/data/equipment/tool-weights.v1.json`, `src/domain/toolWeights.ts`, `medicineWeight.ts`, odczyt katalogu ekwipunku.
- Nowe testy i fixtures; dokumentacja bieżąca oraz changelog.
- Numer wersji w package.json, Cargo.toml, Cargo.lock, tauri.conf.json i stopce.

## Odbiór po integracji

1. Zainstaluj zależności z lockfile; uruchom `pnpm check`, `cargo fmt --manifest-path src-tauri/Cargo.toml --check` i `cargo test --manifest-path src-tauri/Cargo.toml --release --lib --locked`.
2. Zbuduj instalator przez `pnpm build:windows`. Nie traktuj samej kompilacji jako testu aktualizacji.
3. Na kopii istniejących danych sprawdź aktualizację 14/15→16, historię operacji, karty i pięć potyczek; zamknięcie/ponowne otwarcie musi zachować stan.
4. Sprawdź dodanie/usunięcie PD przy szkicu i gotowej karcie; odrzucenie szkicu nie może cofać zapisanych PD.
5. Dodaj 20 strzał do slotu podręcznego; sprawdź masy narzędzi oraz własną jawnie ustawioną masę.
6. Kliknij ładunek medyka, sprawdź ten sam licznik w Postoju, przywróć i uruchom aplikację ponownie.
7. Sprawdź wybór Ulubionej broni dla trzech klas, limity, biegłość Złodzieja, zmianę po treningu i zachowanie modelu po przeniesieniu broni do plecaka.
8. Przywróć zakończoną fobię i zmień jednorazową premię; suma bonusów nie może wzrosnąć przez powtarzanie operacji.
9. Sprawdź klawiaturę, skalowanie Windows 100%/150%, widoczność ostrzeżeń, ikony i polskie znaki.
10. W raporcie podaj finalny commit, wersję instalatora, wyniki prób i ścieżkę gotowego `.exe`. Nie deklaruj wyniku bez faktycznego testu na Windows.
