---
name: process-inbox
description: Przetwarza nowe pliki z 5-Inbox/ i Clippings/ przez pętlę wiedzy Karpathy'ego — wzbogaca, kompiluje do wiki 3-Knowledge/, archiwizuje do 9-Archive/
---

# Process Inbox

Przetwarza nowe pliki z `5-Inbox/` i `Clippings/` przez pętlę wiedzy Karpathy'ego.

## Kiedy używać

- Dodałeś nowe pliki do Inbox lub Clippings (artykuły, transkrypty, notatki, klipy z webu)
- Chcesz przetworzyć wszystko co nowe jednym poleceniem

## Jak wywołać

- "Przetwórz Inbox"
- "Zrób ingest"
- "Co nowego w Inbox?"
- `/process-inbox`
- `/process-inbox nazwa-pliku.md`
- `/process-inbox --all`

## Jak to działa

Dla każdego pliku w `5-Inbox/` lub `Clippings/`:

### 1. Przeczytaj i przeanalizuj

Przeczytaj pełną zawartość pliku. Wyciągnij:
- Temat i kluczowe koncepty
- Autora/źródło
- Czy to jest artykuł, thread, tutorial, video, notatka?

### 2. Sprawdź duplikaty

Przeszukaj `3-Knowledge/` i `9-Archive/` - czy ten temat już jest przetworzony?
- Jeśli tak → AKTUALIZUJ istniejącą stronę wiki (dodaj nowe insighty, dodaj źródło do YAML)
- Jeśli nie → UTWÓRZ nową stronę wiki

### 3. Kompiluj do Knowledge

Utwórz lub zaktualizuj stronę wiki w `3-Knowledge/`:

```markdown
---
title: [Czytelny Tytuł]
created: [RRRR-MM-DD]
sources:
  - nazwa-pliku-1.md
  - nazwa-pliku-2.md
---

# [Czytelny Tytuł]

[Skompilowana treść - synteza, nie kopiuj-wklej]

[Każde twierdzenie cytuje źródło: [source: nazwa-pliku.md]]

## Related
- [[Inna Strona Wiki]]
```

**Zasady:**
- Nazwa pliku czytelna: `Metody Discovery.md`, nie `metody-discovery.md`
- Jedna strona na koncept, nie jedno źródło
- Umieść w odpowiednim podfolderze `3-Knowledge/` (utwórz nowy jeśli żaden nie pasuje, minimum 2-3 strony na podfolder)
- Dodaj `[[backlinki]]` do powiązanych stron
- Cytuj źródło: `[source: nazwa-pliku.md]`

### 4. Archiwizuj źródło

Przenieś przetworzony plik z `5-Inbox/` lub `Clippings/` do `9-Archive/`.

### 5. Raportuj

```
✓ Przetworzono: "nazwa-pliku.md"
  → Wiki: 3-Knowledge/[Podfolder]/[Tytuł Strony].md (utworzono/zaktualizowano)
  → Archiwum: 9-Archive/
```

## Tryb batch (--all)

1. Wylistuj pliki w `5-Inbox/` i `Clippings/`
2. Dla każdego: przeanalizuj, skompiluj, archiwizuj
3. Pokaż podsumowanie:

| Plik | Wiki | Status |
|------|------|--------|
| artykuł.md | 3-Knowledge/AI/Tytuł.md | utworzono |
| thread.md | 3-Knowledge/Product/Tytuł.md | zaktualizowano |

4. Raport: X przetworzonych, Y pominiętych, Z zflagowanych

## Czerwone flagi - STOP

- Modyfikujesz plik w `9-Archive/` (archiwum jest niezmienne)
- Tworzysz stronę wiki z nazwą-slug zamiast czytelnego tytułu
- Kopiujesz treść 1:1 zamiast kompilować
- Przenosisz plik bez tworzenia/aktualizacji strony wiki
