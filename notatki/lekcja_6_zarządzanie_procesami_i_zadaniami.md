# Lekcja 6: Zarządzanie procesami i zadaniami

Linux pozwala na pełną kontrolę nad tym, co i jak długo działa w systemie. Każdy uruchomiony program to proces z unikalnym numerem PID.

## 1. Monitorowanie systemu
- `top` – podstawowy podgląd procesów.
- `htop` – (wymaga instalacji) interaktywny i kolorowy menedżer zadań.
- `ps aux` – pełna lista wszystkich działających procesów w systemie.

## 2. Zarządzanie zadaniami (Background vs Foreground)
- `Ctrl+C` – brutalne przerwanie programu działającego w terminalu.
- `Ctrl+Z` – wstrzymanie programu i przejście do terminala.
- `bg` – wznowienie wstrzymanego programu w tle.
- `&` – dodane na końcu komendy uruchamia ją od razu w tle.
- `jobs` – lista zadań uruchomionych w bieżącej sesji terminala.

## 3. Kończenie procesów (Kill)
Jeśli program nie odpowiada, możemy go zamknąć siłowo:
- `kill <PID>` – grzeczna prośba o zamknięcie.
- `kill -9 <PID>` – natychmiastowe ubicie procesu przez system.
- `pkill <nazwa>` – zabicie wszystkich procesów o danej nazwie.

## 4. Praca długodystansowa
- `nohup <komenda> &` – uruchamia proces, który będzie działał nawet po wylogowaniu użytkownika (kluczowe przy skryptach monitorujących np. giełdę).
