---
name: process-course
description: Przetwarza notatki i materiały z kursów z 7-Courses/ przez pętlę wiedzy Karpathy'ego — kompiluje do wiki 3-Knowledge/, archiwizuje do 9-Archive/. Do organizowania wiedzy z kursów online, warsztatów i bootcampów.
---

# Process Course

Przetwarza notatki i materiały z kursów z `7-Courses/` przez pętlę wiedzy Karpathy'ego. Kompiluje wiedzę z lekcji, modułów i ćwiczeń do trwałej wiki.

## Kiedy używać

- Dodałeś notatki z kursu, transkrypt lekcji lub materiały do `7-Courses/`
- Chcesz skompilować wiedzę z kursu do Knowledge
- `/process-course`
- "Przetwórz kurs"
- "Zrób ingest z lekcji"

## Jak to działa

Dla każdego pliku w `7-Courses/`:

### 1. Przeczytaj i zidentyfikuj

Przeczytaj pełną zawartość. Określ:
- **Kurs**: nazwa kursu / platformy (Udemy, Coursera, Circle, własny)
- **Typ**: lekcja / moduł / ćwiczenie / podsumowanie
- **Temat**: jaki koncept lub skill jest omawiany?

### 2. Wyciągnij wiedzę operacyjną

Skup się na tym co MOŻNA ZASTOSOWAĆ, nie na tym co POWIEDZIANO:
- Frameworki i modele mentalne
- Konkretne techniki i metody (z krokami)
- Przykłady i case studies
- "Gotchas" - co NIE działa i dlaczego
- Narzędzia i zasoby wspomniane po nazwie

Pomiń: organizacyjne informacje o kursie, autopromocję autora, ogólne motywacje bez treści.

### 3. Sprawdź duplikaty i powiązania

Przeszukaj `3-Knowledge/`:
- Czy istnieje strona na ten temat? → AKTUALIZUJ (dodaj nową perspektywę z kursu, dodaj źródło)
- Czy to inny kąt na istniejący koncept? → wzbogać istniejącą stronę
- Czy to zupełnie nowy temat? → UTWÓRZ nową stronę

### 4. Kompiluj do Knowledge

```markdown
---
title: [Czytelny Tytuł Konceptu]
created: [RRRR-MM-DD]
sources:
  - nazwa-lekcji.md
---

# [Czytelny Tytuł]

[Skompilowana wiedza - zwięzła synteza gotowa do zastosowania]

[Cytuj źródło: [source: nazwa-pliku.md]]

## Jak to stosować
[Konkretne kroki lub checklist - jeśli dotyczy]

## Related
- [[Inna Strona Wiki]]
```

### 5. Archiwizuj źródło

Przenieś przetworzony plik z `7-Courses/` do `9-Archive/`.

### 6. Raportuj

```
✓ Przetworzono: "nazwa-pliku.md" [Kurs: nazwa kursu]
  → Wiki: 3-Knowledge/[Podfolder]/[Tytuł].md (utworzono/zaktualizowano)
  → Archiwum: 9-Archive/
```

## Czerwone flagi - STOP

- Przepisujesz notatki 1:1 bez syntezy
- Tworzysz osobną stronę wiki dla każdej lekcji zamiast grupować po konceptach
- Modyfikujesz plik w `9-Archive/` (archiwum jest niezmienne)
