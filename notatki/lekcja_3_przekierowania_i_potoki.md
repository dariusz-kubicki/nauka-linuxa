# Lekcja 3: Przekierowanie i Potoki (Rury)

Linux pozwala łączyć proste komendy w potężne narzędzia za pomocą przekierowań.

## 1. Przekierowanie do pliku (Strzałki)
- `>` - Zapisuje wynik do pliku (uwaga: kasuje starą treść pliku!).
  *Przykład:* `ls > lista.txt`
- `>>` - Dopisuje wynik na sam koniec pliku (bezpieczniejsze, nic nie kasuje).
  *Przykład:* `echo "Kolejny wpis" >> lista.txt`

## 2. Potoki (Pipe `|`)
Znak `|` służy do przesyłania wyniku jednej komendy jako dane wejściowe dla drugiej.
*Przykład:* `ls -l | grep "rwx"`
(Wyświetl pliki , ale "przefiltruj" je tak, by pokazać tylko te z pełnymi uprawnieniami).

## 3. Ważne narzędzia filtrowania 
- `grep` - szuka konkretnego słowa w tekście lub wyniku komendy.
- `cat` - wyświetla zawartość pliku na ekranie.

## 4. Supermoce GREP (Opcje dodatkowe)
Sam `grep` to tylko początek. Prawdziwa zabawa zaczyna się z opcjami.

- `grep -i "tekst"` - ignoruje wielkość liter (znajdzie i "Linux" i "linux").
- `grep -v "tekst"` - **wyklucza** linie zawierające dane słowo (pokaż wszystko OPRÓCZ tego).
- `grep -n "tekst"` - pokazuje, w której linii pliku znajduje się szukane słowo.
- `grep "^d"` - szuka tylko linii zaczynających się od litery "d" (przydatne do szukania folderów w `ls -l`).

## 5. Łączenie wielu potoków
Możesz łączenie dowolną ilość rur `|`. Dane płyną przez nie jak przez taśmociąg w fabryce:
`ls -l | grep -v "notatka" | grep "rwx" > gotowe_programy.txt`
1. Pobierz listę.
2. Odzuć notatki.
3. Zostaw tylko programy.
4. Zapisz do pliku.

---
### Moje doświadczenie:
Dziś nauczyłem się, że jeśli komenda ze strzałką `>` nic nie wyświetla na ekranie, to znaczy, że wykonała zadanie i zapisała dane do pliku. Aby je
zobaczyć, muszę użyć `cat`.
