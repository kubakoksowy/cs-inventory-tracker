# Instrukcja wrzucenia zmian na GitHub

Ten projekt jest obecnie hostowany na platformie Kilo Apps. Aby przenieść go na GitHub, wykonaj poniższe kroki:

## Opcja 1: Użycie GitHub CLI (zalecane)

1. Zainstaluj i zaloguj się do GitHub:
   ```bash
   gh auth login
   ```
   Wybierz GitHub.com, protokół HTTPS, zaloguj się przez przeglądarkę.

2. Utwórz nowe prywatne repozytorienie na GitHubie:
   ```bash
   gh repo create cs2-inventory-tracker --private --source=. --remote=github --push
   ```

3. Wrzuć zmiany na GitHub:
   ```bash
   git push github main
   ```

## Opcja 2: Manualnie przez GitHub Web

1. Wejdź na https://github.com/new
2. Utwórz nowe puste repozytorium (np. `cs2-inventory-tracker`)
3. Skopiuj URL nowego repozytorium (np. `https://github.com/TWOJ_USERNAME/cs2-inventory-tracker.git`)
4. W terminalu:
   ```bash
   git remote add github https://github.com/TWOJ_USERNAME/cs2-inventory-tracker.git
   git push github main
   ```

## Opcja 3: Użycie Personal Access Token (PAT)

1. Utwórz token na GitHub: Settings → Developer settings → Personal access tokens
2. Dodaj zdalne repozytorium:
   ```bash
   git remote add github https://TWOJ_TOKEN@github.com/TWOJ_USERNAME/cs2-inventory-tracker.git
   ```
3. Wrzuć zmiany:
   ```bash
   git push github main
   ```

## Aktualny status repozytorium

- Branch: `main`
- Ostatni commit: `dc5c8e8` - "Fix: Profit calculation only after 'ready to remove'"
- Zmiany: Poprawka w obliczaniu zysku - zysk jest teraz liczony tylko po kliknięciu "ready to remove"
- Repozytorium zdalne (origin): https://builder.kiloapps.io/apps/91c14ba1-bf4b-425e-900d-98aee6578812.git

## Jak sprawdzić zmiany przed wgraniem

```bash
git log --oneline -3
git diff HEAD~1 HEAD --stat
```
