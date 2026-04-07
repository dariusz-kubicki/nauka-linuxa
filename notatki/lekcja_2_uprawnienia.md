# Lekcja 2: Uprawnienia plików i magia SUDO

W linuxie wszystko opiera się na dostępie. Każdy plik ma przypisane zasady, które określają, kto może go czytać, edytować lub uruchamiać

## 1. Rozszyfrowanie hieroglifów (ls -l)
Kiedy wpiszesz `ls -l`, zobaczysz na początku coś takiego: `-rwxrwxr-x`.
Dzielimy to na trzy grupy:
1. **Właściciel** (Ty)
2. **Grupa** (Twoi kumple w systemie)
3. **Reszta świata** (Wszyscy inni)

| Symbol | Nazwa | Co oznacza? |
| :--- | :--- | :--- |
| **r** | Read | Czytanie pliku |
| **w** | Write | Edycja / Zapisywanie |
| **x** | Execute | Uruchamianie (np. programu |
| **-** | Brak | Brak danego uprawnienia |

---

## 2. Metoda liczbowa (Dla hakerów)
Zamiast pisać litery, administratorzy używają liczb. Każdemu uprawnieniu przypisana jest wartość:

- **4** = Czytanie (r)
- **2** = Zapis (w)
- **1** = Uruchamianie (x)

### Jak to liczyć?
Sumujemy wartości dla każdej z trzech grup osób.
- **7 (4+2+1)** = Pełne prawa (`rwx`)
- **6 (4+2+0)** = Czytanie i zapis, bez uruchamiania (`rw-`)
- **5 (4+0+1)** = Czytanie i uruchamianie, bez edycji (`r-x`)
- **4 (4+0+0)** = Tylko do odczytu (`r--`)
 
**Przykład:** `chmod 755 plik`
- **7** (Właściciel): Może wszystko.
- **5** (Grupa): Może czytać i uruchamiać.
- **5** (Inni): Może czytaći uruchamiać.

---

## 3. Komenda CHMOD w praktyce
- `chmod +x skrypt.sh` - sprawia, że plik staje się programem (można go odpalić).
- `chmod -w plik.txt` - blokuje możliwość edycji pliku (tylko do odczytu).
- `chmod 600 tajne.txt` - tylko Ty możesz czytać i pisać, reszta świata nie widzi nic.
 
---

## 4. SUDO (SuperUser DO)
`sudo` to komenda, która pozwala na chwilę stać się **Rootem** (Bogiem systemu).
  
- Używaj `sudo` tylko, gdy edytujesz pliki systemowe (poza `/home/użytkowink`).
- Praca na samym koncie Roota jest niebezpieczna - jeden błąd i możesz skasować cały system. `sudo` to taki "bezpiecznik".

---
*Notatka stworzona dla "siebie z przeszłości", żeby nigdy nie zapomnieć, dlaczego Linux mówi "Permission Denied"*
