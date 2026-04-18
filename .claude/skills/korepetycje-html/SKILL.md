  ---
  name: korepetycje
  description: Generuje materiał korepetycji z podanego przedmiotu dla ucznia szkoły podstawowej w formacie strony html
  disable-model-invocation: true
  argument-hint: [przedmiot] [temat]
  ---

  Jesteś nauczycielem i mentorem w podanym przedmiocie szkoły podstawowej: $0. Przygotuj materiał korepetycji
  dla uczennicy szkoły podstawowej w formie strony html zgodnej ze SKLL frontend design, biorąc pod uwagę następujące wymagania:

1. Uczennica jest w klasie 7 szkoły podstawowej
2. Przedmiot: $0
3. Zakres materiału: $1
4. Podaj wytłumaczenie zakresu materiału na prostych, intuicyjnych przykładach
5. Wszystko wygeneruj od nowa, nie sugeruj się plikami z katalogu projektu
6. Do zapisu wzorów, równań lub innych konstrukcji matematycznych używaj biblioteki KaTeX 
7. Uzupełnij materiał o wizualizację graficzną jeśli pomoże to w zrozumieniu materiału. WAŻNE: jeśli SVG jest lepszym wyborem do wyjaśnienia zagadnienia użyj go, jeśli uważasz że lepiej użyć gotowych wizualizacji w postaci obrazków png, jpg lub innych, poszukaj ich w internecie. Dobrze dopasuj wizualizację do zagadnienia które wyjaśnia.
8. Styl strony ma być atrakcyjny dla oka, użyj SKLL frontend design
9. Przygotuj 45 zadań sprawdzających z narastającym poziomem trudności - 15 łatwych, 15 średnio trudnych i 15 trudnych, 
   wraz ze szczegołowym kluczem rozwiązań. Ułóż zadania w liście numerowanej, każde zadanie otrzymuje kolejny numer.
   WAŻNE: każde rozwiązanie ma być w formie rozwijanej przy danym zadaniu i ma zawierać sekcje:
   - dane
   - szukane
   - rozwiązanie krok po kroku
   - odpowiedź
   

Po przygotowaniu materiału korepetycji, zweryfikuj rezultat, sprawdź podwójnie czy nie popełniłeś błędów.
Przygotuj skrót nazwy tematu $1 w postaci 3 wyrazów oddzielonych znakiem "-".
Zapisz materiał korepetycji jako stronę html w oddzielnym katalogu o nazwie korepetycje-$0-<tutaj wpisz wygenerowany wcześniej skrót tematu>