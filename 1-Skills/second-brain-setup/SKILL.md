---
name: second-brain-setup
description: Użyj do tworzenia lub odświeżania profilu product buildera w 0-System/about.md — obsługuje onboarding przez testy (Gallup, DISC, MBTI) i przez wywiad
---

# Konfiguracja Cyfrowego Bliźniaka

## Przeznaczenie

Prowadzi rozmowę z Product Builderem i zapisuje wynik do pliku `0-System/about.md`. Plik mówi agentowi kim jest człowiek, jak chce być traktowany, gdzie potrzebuje wyzwania. Działa w parze z `0-System/brain.md` (który zawiera uniwersalne zasady operacyjne).

## Kiedy używać

- Konfiguracja nowego vaulta po raz pierwszy
- Odświeżenie profilu po zmianie roli, nowym projekcie, zmianie priorytetów
- Gdy AI wydaje się "nieskalibrowane"

## Jak to działa

### Krok 0: Wybierz ścieżkę

Zapytaj:

> Mam dwie drogi do poznania Cię:
>
> **A) Mam wyniki testu** - wklej wyniki CliftonStrengths (Gallup), DISC, MBTI, 16Personalities, Enneagram, Working Genius lub dowolnego innego testu osobowości/kompetencji. Wyciągnę z nich to, co zmienia sposób naszej współpracy.
>
> **B) Porozmawiajmy** - przeprowadzę krótki wywiad (5-7 minut).
>
> Możesz też zrobić oba: zacząć od testu, potem uzupełnić rozmową.

### Ścieżka A: Assessment-first

1. Przeczytaj wklejone wyniki testu
2. Wyciągnij TYLKO informacje operacyjne - takie, które zmieniają sposób pracy AI:
   - Mocne strony → jak AI ma framować rekomendacje
   - Słabe strony / blind spots → gdzie AI ma aktywnie popychać
   - Styl komunikacji → jak AI ma się odzywać
   - Styl decyzyjny → jak AI ma prezentować opcje
3. NIE przepisuj pełnego raportu do about.md. Wyciąg = 5-8 bullet pointów w sekcji "How to work with me"
4. Zapytaj krótkie follow-up pytania o to czego test nie pokrywa:
   - Obecna rola i kontekst (Q1 z `references/questions.md` - wersja skrócona, 2-3 zdania wystarczą)
   - Cel na 6 miesięcy (Q4 z `references/questions.md`)
5. Przejdź do Kroku 3 (propozycja)

### Ścieżka B: Interview

1. Zadaj pytania z `references/questions.md` w kolejności: Q1 (Kontekst), Q2 (Styl Komunikacji), Q3 (Obszary Rozwoju), Q4 (Cele)
2. Zasady:
   - Q1: sześć podpytań razem, jedna odpowiedź
   - Q2.1-Q2.5: pięć pytań MC, po jednym
   - Q3: multi-select 2-3 z listy 8
   - Q4: jedno otwarte pytanie
3. Przejdź do Kroku 3 (propozycja)

### Krok 3: Zaproponuj treść about.md

**Nie pisz pliku od razu.** Pokaż pełną propozycję:

> Oto co chcę zapisać do `0-System/about.md`:
>
> ```
> [pełna zawartość pliku]
> ```
>
> Wygląda OK? Powiedz "zapisz" albo powiedz co poprawić.

Format pliku - trzy sekcje:

```markdown
# O mnie

## Context
[Rola, firma, produkt, użytkownicy, metryki - z Q1 lub z wyników testu + follow-up]

## How to work with me
[5-8 bullet pointów: styl komunikacji, mocne strony, blind spots, jak framować rekomendacje]
[Ścieżka A: wyciąg z testu. Ścieżka B: z Q2 + Q3]

## Current goal
[Z Q4, własnymi słowami]

---
## Historia
- [RRRR-MM-DD]: profil utworzony [ścieżka A: na podstawie CliftonStrengths / ścieżka B: wywiad]
```

### Krok 4: Zapisz po potwierdzeniu

Dopiero po wyraźnym "zapisz", "OK", "dobrze" - zapisz do `0-System/about.md`. Dopisz wpis do Historii.

### Tryb re-run

Gdy about.md już istnieje:

1. Przeczytaj istniejący plik
2. Streść: "Znam Cię już trochę. Obecny profil mówi..."
3. Zapytaj: "Co się zmieniło?"
4. Zaktualizuj tylko deltę
5. Dopisz wpis historii: `- [RRRR-MM-DD]: zaktualizowano [lista sekcji]`

## Czerwone flagi - STOP

- Piszesz about.md bez pokazania propozycji i uzyskania potwierdzenia
- Modyfikujesz brain.md (nie wolno, nigdy)
- Przepisujesz pełny raport Gallup/DISC do about.md zamiast wyciągu operacyjnego
- W trybie re-run pytasz wszystko od nowa zamiast o deltę
- Pytasz użytkownika o rolę z zamkniętej listy stanowisk
- Sugerujesz, że niektóre role są "bardziej Product Builderami" niż inne

## Referencje

- `references/questions.md` - pełny zestaw pytań z opcjami MC
- `references/e1-source.md` - oryginalny prompt z Edycji 1 (zachowany jako kontekst historyczny)
