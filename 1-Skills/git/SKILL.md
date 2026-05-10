---
name: git
description: Meta-skill do operacji git — router do sub-skilli sync, commit i push
---

# Git

## Przeznaczenie

Meta-skill orkiestrujący operacje git na repozytorium brain. Nie wykonuje operacji samodzielnie — deleguje do sub-skilli.

## Sub-skille

| Sub-skill | Plik | Kiedy |
|---|---|---|
| Sync | `sync.md` | Przed każdą operacją — pobierz zmiany z remote, sprawdź konflikty |
| Commit | `commit.md` | Po każdej operacji modyfikującej pliki brain |

## Routing

| Sygnał | Sub-skill |
|---|---|
| przed operacją, "aktualizuj repo", "pobierz zmiany", "pull" | `sync.md` |
| po operacji, "zapisz zmiany", "commituj", "zrób commit" | `commit.md` |

## Kolejność w każdej sesji

```
1. git sync    ← przed startem
   ...praca...
2. git commit + push  ← po zakończeniu
```

Zawsze sync przed, zawsze commit+push po. Wyjątek: operacja Query (samo czytanie) — bez git.
