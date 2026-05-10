---
name: prototype-builder
description: Meta-skill do budowania prototypów produktowych — router do sub-skilli (PRD, inicjalizacja projektu, backend, frontend, testy)
---

# Prototype Builder

## Przeznaczenie

Meta-skill: wykrywa co chcesz zbudować i deleguje do odpowiedniego sub-skilla. Nie wykonuje pracy samodzielnie — orkiestruje.

## Sub-skille

| Sub-skill | Plik | Kiedy |
|---|---|---|
| Napisz PRD | `write-prd.md` | Chcesz opisać produkt, feature, user stories |
| Zainicjuj projekt | `init-project.md` | Zakładasz nowy projekt w `zewnętrzne repozytoria git` |
| Zaplanuj bazę danych | `design-database.md` | Projektujesz schemat / model danych |
| Zbuduj backend | `build-backend.md` | Piszesz API, logikę serwerową |
| Zbuduj frontend | `build-frontend.md` | Piszesz UI, komponenty, integracje |
| Odpal testy | `run-tests.md` | Weryfikujesz działanie, piszesz testy |

## Routing

Gdy człowiek mówi cokolwiek związanego z budowaniem — przeczytaj intent i powiedz wprost co uruchamiasz:

> Rozumiem, że chcesz [X]. Uruchamiam sub-skill `[nazwa]`.

Następnie przeczytaj odpowiedni plik sub-skilla i wykonaj jego workflow.

### Sygnały routingu

| Sygnał | Sub-skill |
|---|---|
| "napisz PRD", "opisz produkt", "user stories", "wymagania" | `write-prd.md` |
| "nowy projekt", "zainicjuj", "stwórz projekt", "zacznijmy" | `init-project.md` |
| "baza danych", "schemat", "model", "tabele", "relacje" | `design-database.md` |
| "backend", "API", "endpoint", "serwer", "logika" | `build-backend.md` |
| "frontend", "UI", "interfejs", "komponenty", "widok" | `build-frontend.md` |
| "testy", "testuj", "sprawdź", "weryfikuj", "QA" | `run-tests.md` |

### Niejasny intent

Jeśli nie możesz jednoznacznie przypisać — zapytaj:

> Pracujemy nad [projektem]. Co teraz robimy?
> A) Piszemy PRD / wymagania
> B) Zakładamy projekt
> C) Projektujemy bazę danych
> D) Budujemy backend
> E) Budujemy frontend
> F) Testujemy

## Git sync przed startem

Przed każdym sub-skillem sprawdź stan repo:

```bash
git status --short
git pull --rebase
```

Jeśli są niezacommitowane zmiany — poinformuj użytkownika zanim zaczniesz.

## Po zakończeniu sub-skilla

Wywołaj skill `commit` z odpowiednim typem (`update` lub `ingest`).
