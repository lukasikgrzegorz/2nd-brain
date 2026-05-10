---
name: git-commit
description: Commituje zmiany i pushuje po operacji modyfikującej pliki brain — ingest, update, daily, lint
---

# Git Commit & Push

## Wymaganie: gh CLI

Wszystkie operacje git używają `gh` CLI. Sprawdź raz przed pierwszym użyciem:

```bash
gh auth status
```

Jeśli brak — zainstaluj i zaloguj:

```bash
sudo apt install gh
gh auth login
```

## Kiedy wywoływać

Po operacji która zmodyfikowała pliki brain:
- plik przeszedł z `5-Inbox/`, `6-News/` lub `7-Courses/` do `3-Knowledge/`
- powstała lub zaktualizowała się strona w `3-Knowledge/`
- zapisano nową notatkę w `4-Daily/`
- uruchomiono Lint i zapisano raport
- zmieniono konfigurację brain (`0-System/`)

Nie commituj po samym Query (brak zmian w plikach).

## Workflow

### Krok 1: Sprawdź czy są zmiany

```bash
git status --short
```

Jeśli brak zmian (`nothing to commit`) — zakończ bez commita.

### Krok 2: Zbuduj komunikat

Format: `<typ>: <co się zmieniło>`

Typy:
- `ingest` — nowe źródło przetworzone do Knowledge
- `daily` — notatka dzienna
- `lint` — raport health check wiki
- `system` — zmiana konfiguracji brain

Przykłady:
```
ingest: dodano stronę "Metody Discovery" ze źródła art-jtbd.md
daily: notatka 2026-05-10
lint: raport health check wiki 2026-05-10
system: rename 9-Raw → 9-Archive
```

### Krok 3: Commituj i pushuj

```bash
git add -A
git commit -m "<komunikat>"
gh repo sync --source
```

> **Nie używaj `git push`** — do pushowania używamy `gh repo sync --source`.

### Krok 4: Potwierdź

Powiedz użytkownikowi co zostało commitowane i spushowane, w jednym zdaniu.

## Zasady

- Commituj tylko po zakończeniu pełnej operacji, nie w trakcie
- Zawsze pushuj po commicie — commit bez pusha to praca która nie istnieje
- Jeśli komenda zwróci błąd — pokaż go użytkownikowi, nie próbuj naprawić samodzielnie
