# Fixture: Assessment Path - Gallup CliftonStrengths

## Scenariusz

Użytkownik wybiera Ścieżkę A i wkleja wyniki Gallup Top 5.

## Inputs

### Krok 0: Wybór ścieżki

> A

### Wklejone wyniki

> Moje Top 5 CliftonStrengths:
> 1. Strategic - widzę wzorce i alternatywne ścieżki, szybko oceniam scenariusze
> 2. Achiever - muszę codziennie osiągnąć coś wymiernego, wewnętrzny napęd do działania
> 3. Ideation - fascynują mnie połączenia między pozornie niepowiązanymi konceptami
> 4. Command - naturalna skłonność do przejmowania kontroli, konfrontacji, jasnego mówienia
> 5. Activator - niecierpliwość wobec planowania bez działania, chcę zaczynać natychmiast
>
> Moje Bottom 5:
> 34. Discipline - chaos w organizacji, trudność z rutynami i systematycznością
> 33. Consistency - nie lubię traktować wszystkich tak samo, szukam wyjątków
> 32. Deliberative - podejmuję decyzje szybko, czasem za szybko
> 31. Harmony - nie unikam konfliktu, wręcz go szukam gdy widzę problem
> 30. Analytical - wolę intuicję i wzorce niż szczegółową analizę danych

### Follow-up: Kontekst (skrócony)

> PM w startupie fintech, 30 osób, budujemy neobank dla freelancerów w Polsce. Rynek rośnie, ale regulacje nas spowalniają.

### Follow-up: Cel

> Zshipować MVP do końca Q3 i zamknąć seed round.

### Potwierdzenie

> Zapisz

## Expected output

### Asercje strukturalne

- [ ] Plik zapisany do `8-System/about.md`
- [ ] Zawiera nagłówek `# O mnie`
- [ ] Zawiera sekcje: `## Context`, `## How to work with me`, `## Current goal`, `## Historia`
- [ ] Sekcja Historia zawiera datowany wpis z informacją "na podstawie CliftonStrengths"

### Asercje treściowe - Context

- [ ] Zawiera "PM" i "fintech" i "neobank" i "freelancerów"
- [ ] Zawiera informację o wielkości firmy (~30 osób) i etapie (startup)
- [ ] NIE zawiera pełnej listy 34 strengths - to jest wyciąg, nie raport

### Asercje treściowe - How to work with me

- [ ] Zawiera 5-8 bullet pointów (nie mniej niż 5, nie więcej niż 8)
- [ ] Co najmniej jeden bullet odnosi się do mocnych stron (Strategic/Ideation/Command)
- [ ] Co najmniej jeden bullet odnosi się do blind spots (Discipline/Deliberative)
- [ ] Co najmniej jeden bullet jest instrukcją operacyjną dla AI (np. "przypominaj o systematyczności", "wymagaj danych zanim podejmiesz decyzję")
- [ ] NIE jest przepisanym raportem Gallup - jest wyciągiem operacyjnym
- [ ] Bullet pointy są konkretne i actionable, nie ogólnikowe

### Asercje treściowe - Current goal

- [ ] Zawiera "MVP" i "Q3" i "seed round" (lub synonimy)

### Czerwone flagi (test fails jeśli którakolwiek jest prawdą)

- [ ] AI zapisało plik bez pokazania propozycji i uzyskania potwierdzenia
- [ ] AI przepisało pełny raport Gallup (wszystkie 34 pozycje) do about.md
- [ ] AI zmodyfikowało brain.md
- [ ] AI zadało pełny zestaw pytań Q1-Q4 mimo że użytkownik wybrał ścieżkę A
- [ ] Sekcja "How to work with me" zawiera mniej niż 5 bullet pointów
