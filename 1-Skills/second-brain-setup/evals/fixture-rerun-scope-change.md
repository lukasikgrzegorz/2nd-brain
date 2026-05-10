# Fixture: Re-run - Scope Change

## Scenariusz

Użytkownik ma istniejący about.md (wypełniony 3 miesiące temu). Zmienił rolę - z solo foundera przeszedł do korporacji jako PM. Chce zaktualizować profil.

## Pre-condition

Przed uruchomieniem skilla, `8-System/about.md` zawiera:

```markdown
# O mnie

> Ten plik mówi Twojemu AI kim jesteś, jak pracujesz i czego od niego oczekujesz.
> Wypełnij go uruchamiając skill `second-brain-setup` albo edytuj ręcznie.

---

## Context

Solo founder budujący SaaS do zarządzania umowami dla małych kancelarii prawnych w Polsce. 12 użytkowników na beta, zero revenue. Kancelarie potrzebują czegoś prostszego niż Legito, bardziej pro niż Excel. Konkurencja = Excel i Word. Kluczowa metryka: weekly retention.

## How to work with me

- Komunikuj się bez ogródek, twardo. Nie łagodź krytyki.
- Odpowiedzi strukturalnie - bullety, ramki, krok po kroku.
- Zwięźle. Najpierw sedno, szczegóły tylko jeśli zapytam.
- Suchy, bezpośredni ton, bez ceregieli.
- Wypychaj mnie poza strefę komfortu. Nie pozwalaj ślizgać się na łatwiznę.
- Popychaj w obszarach: Wykonanie i Dostarczanie, Analityka i Dane.
- Mam tendencję do budowania featurów zamiast mierzenia co działa - przypominaj mi o danych.

## Current goal

Dojść do 50 płacących użytkowników i zwalidować biznes w 4 miesiące.

---

## Historia

- 2026-01-15: profil utworzony (wywiad)
```

## Inputs

### Reakcja na streszczenie AI

> Zmieniłem robotę. Zamknąłem SaaS - nie zwalidował się. Teraz jestem PM-em w ING, zespół 8 osób, pracujemy nad aplikacją mobilną dla klientów detalicznych. Styl komunikacji i reszta bez zmian.

### Potwierdzenie

> Zapisz

## Expected output

### Asercje strukturalne

- [ ] Plik zapisany do `8-System/about.md`
- [ ] Zawiera wszystkie cztery sekcje (Context, How to work with me, Current goal, Historia)
- [ ] Historia zawiera ZARÓWNO stary wpis (2026-01-15) JAK I nowy wpis z dzisiejszą datą

### Asercje treściowe - Context

- [ ] Zaktualizowany: zawiera "PM" i "ING" i "aplikacja mobilna" i "klienci detaliczni"
- [ ] NIE zawiera starej informacji o SaaS/kancelariach (zastąpiona, nie dodana obok)
- [ ] Zawiera "zespół 8 osób" lub podobny

### Asercje treściowe - How to work with me

- [ ] BEZ ZMIAN lub minimalne zmiany. Użytkownik powiedział "bez zmian" - AI nie powinno przepisywać
- [ ] Zachowane bullet pointy o stylu komunikacji (twardy, strukturalny, zwięzły, suchy, wymagający)
- [ ] Zachowane obszary rozwoju (Wykonanie, Analityka)

### Asercje treściowe - Current goal

- [ ] Zaktualizowany - stary cel (50 użytkowników, walidacja) nie ma sensu w nowym kontekście
- [ ] AI powinno było zapytać o nowy cel LUB zaproponować placeholder
- [ ] Jeśli AI zaproponowało cel - musi być spójny z nową rolą (PM w ING)

### Asercje treściowe - Historia

- [ ] Zawiera: `- 2026-01-15: profil utworzony (wywiad)`
- [ ] Zawiera nowy wpis z dzisiejszą datą i informacją "zaktualizowano Context" (lub podobny)
- [ ] Stary wpis NIE został usunięty ani zmodyfikowany

### Asercje przepływu

- [ ] AI zaczęło od streszczenia istniejącego profilu ("Znam Cię już trochę...")
- [ ] AI NIE zadało pełnego zestawu pytań Q1-Q4
- [ ] AI zapytało tylko o deltę
- [ ] AI zapytało o nowy cel (stary nie pasuje do nowego kontekstu)
- [ ] Propozycja pokazana przed zapisem

### Czerwone flagi

- [ ] AI zadało wszystkie pytania od nowa (Q1, Q2, Q3, Q4)
- [ ] AI usunęło stare wpisy z Historii
- [ ] AI przepisało sekcję "How to work with me" mimo że użytkownik powiedział "bez zmian"
- [ ] AI zapisało bez propozycji i potwierdzenia
- [ ] AI zmodyfikowało brain.md
