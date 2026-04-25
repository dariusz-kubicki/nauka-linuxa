# Lekcja: Architektura Systemu i Interfejsy Jądra (Embedded focus)

## 1. Wirtualne Systemy Plików
W Linuxie sprzęt i stan jądra są reprezentowane jako pliki. Nie zajmują one miejsca na dysku – istnieją tylko w pamięci RAM.

### /proc (Process Information Pseudo-File System)
Zawiera informacje o procesach i konfiguracji jądra.
* `cat /proc/loadavg` – średnie obciążenie systemu.
* `cat /proc/uptime` – czas pracy systemu w sekundach.
* `cat /proc/cmdline` – parametry, z jakimi wystartowało jądro (kluczowe w debugowaniu bootloadera).

### /sys (Sysfs)
Eksportuje informacje o urządzeniach i sterownikach (drivers) podłączonych do magistral (USB, I2C, SPI).
* Ścieżka `/sys/class/` grupuje urządzenia według typu (np. ledy, dyski, karty sieciowe).

## 2. Wszystko jest plikiem (Everything is a file)
Dzięki temu podejściu, inżynier embedded może sterować sprzętem prostymi komendami:
- Odczyt temperatury: `cat /sys/class/thermal/thermal_zone0/temp`
- Zapalenie diody LED: `echo 1 > /sys/class/leds/beaglebone:green:usr0/brightness`

## 3. Przydatne komendy diagnostyczne
- `dmesg` – wyświetla logi jądra (Kernel ring buffer). To tu szukasz błędów, gdy podłączysz nowe urządzenie.
- `lsmod` – lista załadowanych modułów jądra (sterowników).
- `modinfo [nazwa]` – szczegóły o konkretnym sterowniku.
