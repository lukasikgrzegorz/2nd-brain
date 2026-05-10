# Fixture: Interview Path - Solo Operator

## Scenariusz

Użytkownik wybiera Ścieżkę B (wywiad). Profil: solo operator, pre-PMF, wearing every hat.

## Inputs

### Krok 0: Wybór ścieżki

> B

### Q1 - Kontekst

> Jestem solo founderem, robię wszystko sam - od kodu po marketing. Buduję SaaS do zarządzania umowami dla małych kancelarii prawnych w Polsce. Mam 12 użytkowników na beta, zero revenue, kończą mi się oszczędności. Kancelarie potrzebują czegoś prostszego niż Legito, ale bardziej pro niż Excel. Konkurencja to głównie Excel i Word, bo istniejące narzędzia są za drogie dla małych kancelarii (3-5 osób). Kluczowa metryka to retention - czy beta userzy wracają co tydzień.

### Q2.1 - Bezpośredniość

> A

### Q2.2 - Struktura

> A

### Q2.3 - Długość

> A

### Q2.4 - Ton

> C

### Q2.5 - Poziom Wyzwania

> A

### Q3 - Obszary Rozwoju

> 6 i 1. Wykonanie i Dostarczanie, Analityka i Dane. Mam tendencję do budowania featurów zamiast mierzenia co działa.

### Q4 - Cel

> Dojść do 50 płacących użytkowników i zwalidować, czy ten biznes ma sens zanim skończą mi się pieniądze. Daję sobie 4 miesiące.

### Potwierdzenie

> OK

## Expected output

### Asercje strukturalne

- [ ] Plik zapisany do `8-System/about.md`
- [ ] Zawiera nagłówek `# O mnie`
- [ ] Zawiera sekcje: `## Context`, `## How to work with me`, `## Current goal`, `## Historia`
- [ ] Sekcja Historia zawiera datowany wpis "profil utworzony" (lub podobny)

### Asercje treściowe - Context

- [ ] Zawiera "solo founder" lub "jednoosobowo"
- [ ] Zawiera "SaaS" i "kancelarie prawne" (lub "prawników")
- [ ] Zawiera informację o beta (12 użytkowników) i braku revenue
- [ ] Zawiera informację o konkurencji (Excel/Word vs drogie narzędzia)

### Asercje treściowe - How to work with me

- [ ] Zawiera 5-8 bullet pointów
- [ ] Odzwierciedla wybory MC: bezpośredni/twardy (A), strukturalny (A), zwięzły (A), suchy ton (C), wymagający (A)
- [ ] Zawiera odniesienie do obszarów rozwoju: Wykonanie/Dostarczanie i Analityka/Dane
- [ ] Zawiera wskazówkę operacyjną o tendencji do budowania zamiast mierzenia
- [ ] NIE sugeruje, że solo founder jest "mniej Product Builderem" niż ktoś w korporacji

### Asercje treściowe - Current goal

- [ ] Zawiera "50 płacących" i "4 miesiące" (lub synonimy)
- [ ] Zawiera element walidacji biznesu

### Asercje przepływu (weryfikowane w trakcie, nie w output)

- [ ] Q1 zadane jako jeden blok z 6 podpytaniami (nie 6 osobnych wymian)
- [ ] Q2.1-Q2.5 zadane po jednym (5 osobnych wymian)
- [ ] Q3 pokazane jako lista 8 pozycji do wyboru
- [ ] Propozycja about.md pokazana PRZED zapisem
- [ ] AI czekało na potwierdzenie przed zapisem

### Czerwone flagi

- [ ] AI podzieliło Q1 na 6 osobnych pytań
- [ ] AI zrobiło Q2 jako pytanie otwarte zamiast MC
- [ ] AI zapisało plik bez propozycji i potwierdzenia
- [ ] AI zmodyfikowało brain.md
