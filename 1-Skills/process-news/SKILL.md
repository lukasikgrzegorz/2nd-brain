---
name: process-news
description: Przetwarza artykuły i materiały medialne z 6-News/ przez pętlę wiedzy Karpathy'ego — kompiluje do wiki 3-Knowledge/, archiwizuje do 9-Raw/. Dla blogerów: przetwarza artykuły, eventy i trendy na pomysły blogowe i bazę wiedzy.
---

# Process News

Przetwarza materiały newsowe z `6-News/` przez pętlę wiedzy Karpathy'ego. Zaprojektowany dla bloggerów: wyciąga insighty z artykułów, eventów i trendów, kompiluje do wiki i identyfikuje potencjalne tematy blogowe.

## Kiedy używać

- Dodałeś artykuły, newsy lub trendy do `6-News/`
- Chcesz przetworzyć materiał newsowy na wiedzę i potencjalne tematy blogowe
- `/process-news`
- "Przetwórz newsy"

## Jak to działa

Dla każdego pliku w `6-News/`:

### 1. Przeczytaj i sklasyfikuj

Przeczytaj pełną zawartość pliku. Określ:
- **Typ**: artykuł prasowy / event branżowy / raport / opinia / trend
- **Temat**: jaki obszar wiedzy dotyczy?
- **Aktualność**: data i kontekst czasowy

### 2. Sprawdź duplikaty i powiązania

Przeszukaj `3-Knowledge/`:
- Czy istnieje strona na ten temat? → AKTUALIZUJ (dodaj nowe dane, datę, źródło)
- Czy to nowe podejście do istniejącego konceptu? → dodaj jako `> UPDATE [data]: ...` do istniejącej strony
- Czy to zupełnie nowy temat? → UTWÓRZ nową stronę

### 3. Kompiluj do Knowledge

Utwórz lub zaktualizuj stronę wiki w `3-Knowledge/`:

```markdown
---
title: [Czytelny Tytuł]
created: [RRRR-MM-DD]
sources:
  - nazwa-artykulu.md
---

# [Czytelny Tytuł]

[Skompilowana treść - synteza, nie kopiuj-wklej. Przy newsach: co to znaczy, nie tylko co się stało.]

[Każde twierdzenie cytuje źródło: [source: nazwa-pliku.md]]

## Blog Ideas
- [Potencjalny temat blogowy wynikający z tego materiału]

## Related
- [[Inna Strona Wiki]]
```

### 4. Sekcja Blog Ideas

Dla każdego materiału dodaj sekcję `## Blog Ideas` z 1-3 konkretnymi tematami blogowymi które można napisać na podstawie tego materiału. Bądź konkretny: "Dlaczego [X] zmienia [Y] dla [grupy docelowej]" — nie "artykuł o trendach AI".

### 5. Archiwizuj źródło

Przenieś przetworzony plik z `6-News/` do `9-Raw/`.

### 6. Raportuj

```
✓ Przetworzono: "nazwa-pliku.md"
  → Wiki: 3-Knowledge/[Podfolder]/[Tytuł].md (utworzono/zaktualizowano)
  → Blog Ideas: [liczba] pomysłów
  → Archiwum: 9-Raw/
```

## Czerwone flagi - STOP

- Kopiujesz treść artykułu 1:1 zamiast syntetyzować
- Tworzysz stronę wiki bez sekcji Blog Ideas
- Modyfikujesz plik w `9-Raw/` (archiwum jest niezmienne)
