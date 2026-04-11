# Lekcja 4: Zmienne, grawisy i automatyzacja (.bashrc)

W tej lekcji dowiedziałem się, jak Linux przechowuje dane w pamięci oraz jak zmusić system do wykonywania obliczeń przy każdym uruchomieniu.

## 1. Zmienne Środowiskowe
Zmienne to "pudełka" na dane. W terminalu wywołujemy je znakiem `$`.
- `$USER` - nazwa aktualnego użytkownika.
- `$HOME` - ścieżka do katalogu domowego.
- `$PATH` - lista folderów, w których system szuka programów.

## 2. Podstawianie komend (Grawisy i $())
Linux pozwala wstawić wynik jednej komendy do drugiej.
- Stara metoda: `` `komenda\` `` (użycie grawisów).
- Nowa metoda: `$(komenda)`.
*Przykład:* `echo "Dzisiaj jest $(date)"` - system najpierw sprawdza datę, a potem wstawia ją do zdania.

## 3. Plik .bashrc - Moje Centrum Dowodzenia
Plik `.bashrc` to ukryty skrypt w folderze domowym, który odpala się przy każdym starcie terminala. Pozwala na:
- Tworzenie własnych powitań.
- Ustawianie zmiennych na stałe.
- Tworzenie aliasów (skrótów do komend).

## 4. Matematyka w Bashu i Case Study: Licznik Celu
Bash potrafi liczyć za pomocą składni `$(( działanie ))`.

Wykorzystałem to do stworzenia licznika dni do mojej 20-stki w pliku `.bashrc`:
- Przeliczyłem datę docelową na sekundy (Unix Epoch).
- Obliczyłem różnicę między "teraz" a "cel".
- Podzieliłem wynik przez 86400 (liczba sekund w dobie).

**Mój wynik:** 1562 dni do 20-stki. Każde logowanie do systemu przypomina mi teraz o upływającym czasie i motywuje do nauki.

---
*Notatka: Umiejętność automatyzacji prostych zadań to fundament pracy inżyniera Embedded i droga do wysokich zarobków w IT.*
