# CLAUDE.md — repo korepetycje

## 1. Opis projektu

Zbiór kart powtórzeniowych dla uczniów klasy 7 szkoły podstawowej, po polsku (chemia, fizyka, historia). Każda karta to pojedynczy statyczny plik HTML zawierający teorię, przykłady i zadania z kluczem odpowiedzi. Całość hostowana przez GitHub Pages z katalogu głównego repo. Brak build systemu — czysty HTML/CSS/JS.

## 2. Struktura repo

```
/index.html                                 strona startowa z listą kart
/korepetycje-<przedmiot>-<temat>/index.html karta = jeden katalog
/korepetycje-<przedmiot>-<temat>/images/    lokalne zasoby (opcjonalnie)
```

Obecne karty:
- `korepetycje-chemia-prawa-reakcje-chemiczne/` (~1700 linii)
- `korepetycje-chemia-atomy-uklad-okresowy/` (~1230 linii)
- `korepetycje-fizyka-dynamika-sily-ruch/` (~2300 linii)
- `korepetycje-historia-swiat-po-wojnie/` (~780 linii, + `images/`)

Strona startowa `/index.html` grupuje karty w sekcje per przedmiot — każda sekcja to `<section class="subject-group">` z nagłówkiem `.subject-head.<chem|phys|hist>` i licznikiem `.count`, a wewnątrz własna siatka `.courses` z kafelkami `<a class="course …">`.

## 3. Stack

- Czysty HTML5 z `lang="pl"`, osadzony `<style>` i inline `<script>`
- Brak `package.json`, brak build tooling, brak testów automatycznych
- CDN: Google Fonts (Fraunces / Inter / Manrope), KaTeX (formuły w chemii i fizyce)
- Obrazy (np. wizerunki przywódców w historii) hostowane lokalnie w `images/` — nie używać hotlinków do Wikimedia Commons ani innych zewnętrznych źródeł

## 4. Konwencje

- Nazwa katalogu karty: `korepetycje-<przedmiot>-<temat-kebab-case>/` (bez polskich znaków)
- Język treści: wyłącznie polski — tytuły, opisy, komunikaty, nazwy commitów
- Styl: osadzony CSS w `<style>` (nie zewnętrzne pliki), zmienne w `:root`
- Typowe klasy: `.container`, `.hero`, `.card`, `.section`, `.kicker`, `.pill`, `.timeline`, `.grid`, `.info`, `.warn`, `.ex`
- Każda karta ma własną paletę (ciemny motyw z gradientami dla chemii i historii, jasny „vintage journal" dla fizyki) — nie narzucać jednolitego stylu między kartami
- Zadania: rozwijane `<details class="q">` z poziomem trudności (`.level.easy` / `.mid` / `.hard`) i kluczem odpowiedzi w `<div class="answer">`
- Chronologia: w treściach historycznych sekcje i timeline'y mają być uporządkowane rosnąco wg dat

## 5. Dodawanie nowej karty

1. Utwórz katalog `korepetycje-<przedmiot>-<temat>/` z plikiem `index.html`
2. Wzoruj się na istniejącej karcie z tego samego przedmiotu (tożsamy motyw kolorystyczny i struktura sekcji)
3. Dodaj kafelek do głównego `/index.html` **wewnątrz odpowiedniej sekcji** `<section class="subject-group">` (Chemia / Fizyka / Historia) — nie tworzyć nowej sekcji dla istniejącego przedmiotu, nie wrzucać kafelka poza sekcje. Kafelek to `<a class="course <chem|phys|hist>">` z linkiem `<katalog>/index.html` (bezpośredni link do pliku, nie do katalogu). Pamiętaj o aktualizacji licznika `.count` w `.subject-head` (np. „3 karty")
4. Nowy przedmiot (inny niż chemia/fizyka/historia) — dodaj nową `<section class="subject-group">` z własnym headerem i zdefiniuj zmienną koloru (`--<subject>`) oraz modyfikatory `.course.<subject>` / `.subject-head.<subject>` w `<style>`
5. Treść wyłącznie po polsku; klasa docelowa podana w nagłówku `.kicker`

## 6. Git / PR workflow

- Branch główny: `main`; zawsze pracuj na osobnym branchu feature
- Commit messages po polsku, opisują „dlaczego" bardziej niż „co"
- PR title i body po polsku; struktura: `## Summary` (1–3 bullet) + `## Test plan` (checklista)
- Nie commitować katalogu `.claude/` (lokalne ustawienia)

## 7. Weryfikacja zmian UI

- Otwórz zmodyfikowany `index.html` w przeglądarce — to jedyny sposób weryfikacji (brak testów)
- Sprawdź: rozwijanie zadań, działanie linków z głównej strony, poprawność renderowania KaTeX
- Brak type-checkera i linterów — poprawność oceniamy wzrokowo
