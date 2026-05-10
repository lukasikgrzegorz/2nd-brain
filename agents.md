# Super Brain

Przeczytaj te dwa pliki zanim zrobisz cokolwiek:

1. **`0-System/brain.md`** - jak operujesz tym Super Brain (foldery, workflowy, konwencje, architektura skilli)
2. **`0-System/about.md`** - kim jest człowiek, z którym pracujesz

Jeśli `about.md` jest pusty - zaproponuj uruchomienie skilla `second-brain-setup` z folderu `1-Skills/`.

`3-Knowledge/index.md` to spis treści wiki - czytaj go jako pierwsze przy Query i Ingest. `3-Knowledge/log.md` to historia operacji - dopisuj po każdym Ingest.

---

## Architektura skilli

Skille w `1-Skills/` dzielą się na dwa typy:

**Meta-skill** — router delegujący do sub-skilli. `SKILL.md` zawiera logikę routingu i listę sub-skilli. Sam nie wykonuje pracy — czyta intent i deleguje.

**Leaf-skill** — samodzielnie wykonuje jedną operację. Punkt wejścia: `SKILL.md`.

> **Zasada oszczędności kontekstu:** Czytaj `SKILL.md` leaf-skilla dopiero gdy do niego delegujesz — nie ładuj wszystkich skilli na starcie.

### Meta-skille

| Skill | Opis | Sub-skille |
|---|---|---|
| `git/` | Operacje git na brainie | `sync.md` (pull --rebase), `commit.md` (commit po operacji) |

### Leaf-skille

| Skill | Opis |
|---|---|
| `second-brain-setup/` | Konfiguracja profilu `0-System/about.md` |
| `process-inbox/` | Przetwarzanie plików z `5-Inbox/` do Knowledge |
| `youtube/` | Ingest transkryptów z YouTube |
| `process-news/` | Przetwarzanie materiałów z `6-News/` do Knowledge |
| `process-course/` | Przetwarzanie notatek z kursów z `7-Courses/` do Knowledge |

### Konwencja wywołania

Każda operacja modyfikująca pliki brain:
1. Zaczyna się od `git sync` (`1-Skills/git/sync.md`)
2. Kończy się `git commit + push` (`1-Skills/git/commit.md`) — tylko jeśli są realne zmiany w plikach

Wyjątek: Query (samo czytanie) — bez git.
