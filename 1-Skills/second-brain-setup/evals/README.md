# Evals - second-brain-setup

Trzy test fixtures. Każdy zawiera kanoniczne odpowiedzi (Inputs) i oczekiwane asercje (Expected output).

## Jak uruchomić

1. Otwórz nową sesję AI z dostępem do vaulta
2. Wyczyść (lub schowaj) istniejący `8-System/about.md`
3. Uruchom skill `second-brain-setup`
4. Podaj odpowiedzi z sekcji `## Inputs` danego fixture'a
5. Sprawdź output przeciwko asercjom z `## Expected output`

## Fixtures

| Fixture | Ścieżka | Scenariusz |
|---|---|---|
| `fixture-assessment-gallup.md` | A (assessment) | Wklejone wyniki Gallup Top 5 + krótki follow-up |
| `fixture-interview-solo.md` | B (interview) | Pełny wywiad, solo operator pre-PMF |
| `fixture-rerun-scope-change.md` | Re-run | Istniejący about.md + zmiana roli, oczekiwana delta |
