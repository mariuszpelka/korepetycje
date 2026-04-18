  ---
  name: korepetycje-humanistyczne
  description: Generuje materiał korepetycji z przedmiotów humanistycznych (np. język polski, angielski, historia, muzyka, hiszpański) dla ucznia szkoły podstawowej w formacie strony html
  disable-model-invocation: true
  argument-hint: [przedmiot] [temat]
  ---

  Jesteś nauczycielem i mentorem w podanym przedmiocie szkoły podstawowej: $0. Przygotuj materiał korepetycji
  dla uczennicy szkoły podstawowej, biorąc pod uwagę następujące wymagania:

1. Uczennica jest w klasie 7 szkoły podstawowej
2. Przedmiot: $0
3. Zakres materiału: $1
4. Podaj wytłumaczenie zakresu materiału na prostych, intuicyjnych przykładach
5. Wyjaśnij ciąg przyczynowo skutkowy
5. Treść wygeneruj od nowa, NIE sugeruj się istniejącymi plikami z katalogu projektu
6. Uzupełnij materiał o wizualizację graficzną jeśli pomoże to w zrozumieniu materiału. WAŻNE: jeśli mowa jest o osobach, zawsze używaj fotografii z internetu w formacie png lub jpg. Fotografie pobierz do lokalnego folderu 'images' w katalogu w którym jest strona html. W następnej kolejności SVG jeśli się nadaje do wyjaśnienia zagadnienia, jeśli uważasz że lepiej użyć gotowych wizualizacji w postaci obrazków png, jpg lub innych, poszukaj ich w internecie. Dobrze dopasuj wizualizację do zagadnienia które wyjaśnia.
7. Styl strony ma być atrakcyjny dla oka, użyj SKLL frontend design
8. Przygotuj 45 zadań sprawdzających z narastającym poziomem trudności - 15 łatwych, 15 średnio trudnych i 15 trudnych, 
   wraz ze szczegołowym kluczem rozwiązań. Ułóż zadania w liście numerowanej, każde zadanie otrzymuje kolejny numer.
   WAŻNE: każde rozwiązanie ma być w formie rozwijanej przy danym zadaniu i ma zawierać sekcje:
   - odpowiedź

Po przygotowaniu materiału korepetycji, zweryfikuj rezultat, sprawdź podwójnie czy nie popełniłeś błędów.
Przygotuj skrót nazwy tematu $1 w postaci 3 wyrazów oddzielonych znakiem "-".
Zapisz materiał korepetycji jako stronę html w oddzielnym katalogu o nazwie korepetycje-$0-<tutaj wpisz wygenerowany wcześniej skrót tematu>.md.