---
name: youtube
description: Tworzy ustrukturyzowaną notatkę z filmu YouTube, a następnie kompiluje ją do strony wiki 3-Knowledge/ metodą Karpathy'ego
---

# YouTube Video Summary

Tworzy ustrukturyzowaną notatkę z filmu na YouTube, a następnie kompiluje ją do strony wiki w Knowledge.

## Kiedy używać

- Chcesz podsumować film do czystej notatki z metadanymi i kluczowymi ideami
- Dla tutoriali - output to step-by-step guide, nie streszczenie

## Jak wywołać

- `/youtube https://youtube.com/watch?v=...`
- "Zrób notatkę z tego filmu: [URL]"

## Jak to działa

### 1. Wyciągnij metadane

```bash
yt-dlp --skip-download --print "%(title)s|||%(channel)s|||%(upload_date)s|||%(description).500s" "$ARGUMENTS"
```

Jeśli yt-dlp nie działa: wyciągnij video ID z URL, użyj WebSearch.

### 2. Pobierz transkrypt

```bash
yt-dlp --skip-download --write-auto-subs --sub-langs "en,pl" --sub-format "vtt" -o "/tmp/yt_transcript" "$ARGUMENTS"
```

Jeśli nie działa: poproś użytkownika o wklejenie transkryptu z YouTube.

### 3. Sklasyfikuj typ filmu

- **Tutorial/Explainer**: walkthrough, demo, how-to → output to step-by-step guide
- **Idea/Opinia**: teza, wywiad, perspektywa → output to key ideas + cytaty

### 4. Wygeneruj notatkę

**YAML Frontmatter:**
```yaml
---
date: RRRR-MM-DD
title: "Tytuł Filmu"
author: Nazwa Kanału
source: [URL YouTube]
topics:
  - topic-1
  - topic-2
type: video
---
```

**Dla tutoriali:**
```markdown
# Tytuł

## Co to obejmuje
[1-2 zdania]

## Step-by-Step Tutorial
### Krok 1: [Akcja]
[Co kliknąć, wpisać, skonfigurować. Imperatywnie.]

## Tips & Gotchas
- Praktyczne wskazówki i ograniczenia

## Source
[URL]
```

**Dla idei/opinii:**
```markdown
# Tytuł

## Key Ideas
- (5-10 kluczowych idei - bądź konkretny)

## Summary
[3-5 akapitów]

## Notable Quotes
> "Cytat z filmu"

## Source
[URL]
```

**Co wyciągać:**
- Konkretne przykłady i anegdoty (nie abstrahuj)
- Liczby i metryki
- Cytaty "my faktycznie robimy X" - gdy mówcy zdradzają praktykę vs teorię
- Kontrariańskie twierdzenia
- Narzędzia i produkty po nazwie
- Metafory i modele mentalne
- Sekcje Q&A - tam są najcenniejsze nuggets

### 5. Zapisz i przetwórz (Karpathy)

**Krok A:** Zapisz notatkę do `5-Inbox/`

**Krok B:** Kompiluj do Knowledge
1. Sprawdź czy strona wiki na ten temat istnieje w `3-Knowledge/`
2. Jeśli tak → AKTUALIZUJ (dodaj insighty, dodaj źródło do YAML)
3. Jeśli nie → UTWÓRZ nową stronę w odpowiednim podfolderze `3-Knowledge/`
4. Czytelna nazwa pliku, `[[backlinki]]`, `[source: ...]` cytaty

**Krok C:** Przenieś notatkę z `5-Inbox/` do `9-Archive/`

## Self-check

- Czy ktoś może dyskutować o tym temacie czytając tylko moje notatki?
- Dla tutoriali: czy ktoś może WYKONAĆ workflow bez oglądania filmu?
- Czy wyciągnąłem konkretne liczby/metryki?
- Czy złapałem sekcję Q&A?
- Czy nie użyłem AI markerów (delve, tapestry, pivotal, foster)?

## Cleanup

```bash
rm -f /tmp/yt_transcript*
```
