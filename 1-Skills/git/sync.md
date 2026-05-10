---
name: git-sync
description: Sprawdza stan repo i pobiera zmiany z remote przed startem operacji
---

# Git Sync

## Wymaganie: gh CLI

Wszystkie operacje git używają `gh` CLI do autoryzacji i synchronizacji. Sprawdź raz przed pierwszym użyciem:

```bash
gh auth status
```

Jeśli brak — zainstaluj i zaloguj:

```bash
sudo apt install gh
gh auth login
```

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
gh repo sync
```

- **Sukces** — kontynuuj, powiedz "Repo aktualne."
- **Konflikt** — zatrzymaj się, pokaż konfliktujące pliki, nie kontynuuj.
- **Brak połączenia** — kontynuuj offline, zanotuj: "Repo nie zsynchronizowane z remote."
- **Brak repo git** — poinformuj użytkownika, kontynuuj bez git.
