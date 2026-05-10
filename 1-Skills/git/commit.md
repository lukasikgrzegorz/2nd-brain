---
name: git-commit
description: Commituje zmiany po operacji modyfikującej pliki brain — ingest, update, daily, lint
---

# Git Commit

## Kiedy wywoływać

Po operacji która zmodyfikowała pliki brain:
- plik przeszedł z `2-Inbox/` lub `5-Raw/` do `4-Knowledge/`
- powstała lub zaktualizowała się strona w `4-Knowledge/`
- zapisano nową notatkę w `1-Daily/`
- zaktualizowano plik w `3-Projects/`
- uruchomiono Lint i zapisano raport

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
- `update` — aktualizacja projektu
- `daily` — notatka dzienna
- `lint` — raport health check wiki
- `system` — zmiana konfiguracji brain

Przykłady:
```
ingest: dodano stronę "Metody Discovery" ze źródła art-jtbd.md
update: projekt FashionHero — decyzja o wyborze feature MVP
daily: notatka 2026-05-10
lint: raport health check wiki 2026-05-10
```

### Krok 3: Commituj

```bash
git add -A
git commit -m "<komunikat>"
```

### Krok 4: Potwierdź

Powiedz użytkownikowi co zostało commitowane, w jednym zdaniu.

## Zasady

- Commituj tylko po zakończeniu pełnej operacji, nie w trakcie
- Nigdy nie używaj `git push` — push jest decyzją człowieka
- Jeśli `git commit` zwróci błąd — pokaż go użytkownikowi, nie próbuj naprawić samodzielnie
