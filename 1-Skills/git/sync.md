---
name: git-sync
description: Sprawdza stan repo i pobiera zmiany z remote przed startem operacji
---

# Git Sync

## Workflow

### Krok 1: Sprawdź niezacommitowane zmiany

```bash
git status --short
```

Jeśli są niezacommitowane zmiany — zatrzymaj się i pokaż je użytkownikowi:

> Widzę niezacommitowane zmiany: [lista plików]. Co z nimi robimy zanim zaczniemy?

Opcje: commituj teraz (→ wywołaj `commit.md`), porzuć, kontynuuj mimo to.

### Krok 2: Pobierz zmiany z remote

```bash
git pull --rebase
```

- **Sukces** — kontynuuj, powiedz "Repo aktualne."
- **Konflikt** — zatrzymaj się, pokaż konfliktujące pliki, nie kontynuuj.
- **Brak remote / brak połączenia** — kontynuuj offline, zanotuj: "Repo nie zsynchronizowane z remote."
- **Brak repo git** — poinformuj użytkownika, kontynuuj bez git.
