# Lekcja 5: Sieci, API i rozwiązywanie problemów (Debugowanie)

W tej lekcji nauczyliśmy się, jak Linux komunikuje się ze światem zewnętrznym i co zrobić, gdy "internet nie działa", mimo że jest podłączony.

## 1. Narzędzia sieciowe
- `ip a` – sprawdzanie adresu IP urządzenia.
- `ping <adres>` – testowanie połączenia (np. `ping 8.8.8.8`).
- `curl` – narzędzie do pobierania danych z serwerów i stron WWW.

## 2. Zarządzanie pakietami (Instalacja)
Jeśli w systemie brakuje narzędzia, instalujemy je za pomocą menedżera pakietów `apt`:
- `sudo apt update` – odświeżenie listy programów.
- `sudo apt install curl` – instalacja programu curl.

## 3. Rozwiązywanie problemów z DNS (Debugowanie)
Częsty problem w Linuxie: ping po IP działa, ale ping po nazwie (np. google.com) nie.
- **Plik `/etc/resolv.conf`**: Odpowiada za serwery DNS. Jeśli nie działa, dopisujemy:
  `nameserver 8.8.8.8`
- **Plik `/etc/hosts`**: Lokalna książka telefoniczna. Pozwala "na sztywno" przypisać IP do nazwy strony.

## 4. Pobieranie danych przez API
API to sposób na pobieranie czystych danych (JSON) zamiast całych stron WWW.
- **Przykład użycia:**
  `curl -s https://jsonplaceholder.typicode.com/users/1 > dane.json`
- **Ważna lekcja:** Literówki w adresie URL (np. `user` zamiast `users`) sprawiają, że serwer nie zwraca danych. Precyzja w terminalu to podstawa.

## 5. Łączenie komend (Potoki i logiczne AND)
Możemy łączyć akcje, aby działy się jedna po drugiej:
`curl -s <url> > plik.json && cat plik.json`
(Pobierz, zapisz do pliku, a jeśli się uda - wyświetl zawartość).
