# 🐧 Moja Nauka Linuxa (Debian) - Notatki

Ten plik zawiera podsumowanie moich pierwszych kroków w systemie Debian, przygotowujących mnie do pracy z systemami Embedded.

## 🛠 Konfiguracja Systemu
- **Instalacja:** Debian w wersji CLI (bez środowiska graficznego).
- **Zarządzanie:** Dodanie użytkownika do grupy `sudo` i wyłączenie GUI komendą:
  `sudo systemctl set-default multi-user.target`
- **Dostęp:** Skonfigurowany serwer SSH (`openssh-server`), co pozwala na pracę z poziomu Windows PowerShell.

## 📂 Podstawowe Komendy Terminala

| Komenda | Opis | Przykład |
| :--- | :--- | :--- |
| `pwd` | Pokazuje aktualną ścieżkę (gdzie jestem) | `pwd` |
| `ls -la` | Listuje wszystkie pliki (również ukryte) | `ls -la` |
| `cd` | Zmienia folder (`..` to wyjście w górę) | `cd projekt/` |
| `mkdir` | Tworzy nowy folder | `mkdir nowe_lekcje` |
| `touch` | Tworzy pusty plik | `touch notatka.txt` |
| `cp` | Kopiuje plik | `cp kod.c backup.c` |
| `mv` | Przenosi plik lub zmienia jego nazwę | `mv stary.c nowy.c` |
| `rm -r` | Usuwa plik lub folder (bezpowrotnie!) | `rm -r stare_smieci/` |

## 📝 Edycja Tekstu i Programowanie

Do edycji plików w terminalu używam edytora **Nano**:
- `nano nazwa_pliku` - otwarcie
- `Ctrl + O` -> `Enter` - zapisanie
- `Ctrl + X` - wyjście

### Pierwszy program w C
Skompilowany za pomocą `gcc` (pakiet `build-essential`):
1. Tworzenie: `nano hello.c`
2. Kompilacja: `gcc hello.c -o program`
3. Uruchomienie: `./program`

## 💡 Ważne skróty i triki
- **Klawisz TAB:** Autouzupełnianie nazw plików i komend (oszczędza czas!).
- **Strzałki (Góra/Dół):** Przeglądanie historii wpisanych komend.
- **`ip a`:** Sprawdzanie adresu IP maszyny wirtualnej.
- **`sudo poweroff`:** Bezpieczne wyłączenie systemu.

---
*Notatki stworzone podczas nauki podstaw Linuxa dla Embedded.*
