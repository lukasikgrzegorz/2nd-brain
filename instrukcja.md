# Jak uruchomić Super Brain

## Zanim zaczniesz

### 1. Zainstaluj Obsidian (zalecane)

Obsidian to darmowy edytor markdown - Twoje okno na Super Brain. AI pisze pliki, Obsidian je pokazuje w czasie rzeczywistym z backlinkami i grafem.

1. Wejdź na https://obsidian.md
2. Pobierz (macOS / Windows / Linux - darmowe)
3. Zainstaluj, uruchom
4. Wybierz **"Open folder as vault"** i wskaż rozpakowany folder

### 2. Zainstaluj Obsidian Web Clipper (opcjonalne)

Rozszerzenie przeglądarki, które zapisuje strony jako markdown prosto do Twojego Super Brain.

1. https://obsidian.md/clipper (albo Chrome/Firefox store - "Obsidian Web Clipper")
2. Zainstaluj
3. W ustawieniach Web Clippera ustaw domyślny folder zapisu na `5-Inbox`

---

## Wybierz swoją ścieżkę

| Ścieżka | Dla kogo | Koszt |
|---|---|---|
| **A. Claude Code / Cowork** | Masz subskrypcję Claude Pro lub Max | ~20$/msc |
| **B. OpenCode + ChatGPT** | Masz subskrypcję ChatGPT Plus/Pro, nie używasz Claude | ~20$/msc |
| **C. OpenCode + darmowy model** | Nie chcesz płacić za żadne AI | Darmowe |
| **D. Cursor / Windsurf / Antigravity** | Masz już IDE z wbudowanym AI | Zależy od IDE |

Wszystkie ścieżki pracują na TYM samym folderze. Jeśli zmienisz zdanie w trakcie programu - po prostu przełączasz narzędzie, nie migrujesz plików.

---

## Ścieżka A: Claude Code / Cowork

Najlepsza opcja jeśli masz Claude Pro. Dwie wersje:

### Opcja A1: Claude Cowork (dla nie-deweloperów)

Cowork to zakładka w Claude Desktop z pełnym dostępem do plików.

1. Otwórz **Claude Desktop** (pobierz z https://claude.ai/download jeśli nie masz)
2. Kliknij zakładkę **Cowork** (obok Chat)
3. Wskaż folder Super Brain jako working directory
4. **Test:** napisz w chacie:

```
Przeczytaj CLAUDE.md i powiedz mi co widzisz.
```

5. **Uruchom skilla:** napisz `/second-brain-setup` (jeśli skill jest zainstalowany) albo:

```
Przeczytaj 1-Skills/second-brain-setup/SKILL.md i wykonaj workflow opisany w tym pliku.
```

### Opcja A2: Claude Code (dla deweloperów)

Claude Code to CLI z pełnym dostępem do systemu plików.

1. Zainstaluj Claude Code:

```bash
npm install -g @anthropic-ai/claude-code
```

2. Przejdź do folderu Super Brain i uruchom:

```bash
cd /ścieżka/do/twojego/super-brain
claude
```

3. **Test:** napisz:

```
Przeczytaj CLAUDE.md i powiedz mi co widzisz.
```

4. **Uruchom skilla:**

```
Uruchom skill second-brain-setup
```

---

## Ścieżka B: OpenCode + ChatGPT

### Czym jest OpenCode?

OpenCode to darmowe, open-source narzędzie do pracy z AI na plikach - podobne do Claude Code, ale obsługuje wielu dostawców AI (OpenAI, Google, open-source modele i inne). Jeśli nie masz Claude Pro, ale masz subskrypcję ChatGPT Plus/Pro - OpenCode pozwala Ci używać modeli OpenAI do pracy z Super Brain w ramach istniejącej subskrypcji. Nie potrzebujesz klucza API.

### Instalacja OpenCode

Wejdź na https://opencode.ai/download i pobierz aplikację dla swojego systemu (macOS / Windows / Linux).

Dla deweloperów - alternatywnie przez terminal:

```bash
npm i -g opencode-ai
```

### Połączenie z ChatGPT

1. Przejdź do folderu Super Brain i uruchom:

```bash
cd /ścieżka/do/twojego/super-brain
opencode
```

2. Wpisz `/connect`
3. Wybierz **OpenAI** z listy dostawców
4. Wybierz **"ChatGPT Plus/Pro"** jako metodę autoryzacji
5. Otworzy się przeglądarka - zaloguj się kontem ChatGPT
6. Po zalogowaniu token wraca do CLI automatycznie
7. Wpisz `/models` i wybierz model (np. GPT-4.1 albo o3)

### Test

```
Przeczytaj CLAUDE.md i powiedz mi co widzisz.
```

### Uruchom skilla

```
Przeczytaj 1-Skills/second-brain-setup/SKILL.md i wykonaj workflow opisany w tym pliku.
```

---

## Ścieżka C: OpenCode + darmowy model

Jeśli nie chcesz płacić za żadne AI - możesz użyć OpenCode z darmowym modelem przez OpenRouter.

### Czym jest OpenRouter?

Bramka do setek modeli AI - w tym darmowych. Zakładasz konto, dostajesz klucz API, wybierasz model. Dla Super Brain wystarczy darmowy model MiniMax M2.5.

### Instalacja OpenCode

Wejdź na https://opencode.ai/download i pobierz aplikację.

Dla deweloperów:

```bash
npm i -g opencode-ai
```

### Konfiguracja darmowego modelu

1. Wejdź na https://openrouter.ai i załóż konto (darmowe)
2. Wygeneruj klucz API (Settings -> Keys -> Create Key)
3. Przejdź do folderu Super Brain i uruchom:

```bash
cd /ścieżka/do/twojego/super-brain
opencode
```

4. Wpisz `/connect`
5. Wybierz **OpenRouter** z listy, wklej klucz API
6. Wpisz `/models` i wybierz **MiniMax M2.5** (darmowy, 0$ za milion tokenów)

### Test

```
Przeczytaj CLAUDE.md i powiedz mi co widzisz.
```

### Uruchom skilla

```
Przeczytaj 1-Skills/second-brain-setup/SKILL.md i wykonaj workflow opisany w tym pliku.
```

---

## Ścieżka D: Cursor / Windsurf / Antigravity

Jeśli masz już IDE z wbudowanym AI (Cursor, Windsurf, Antigravity, inne) - po prostu otwórz folder Super Brain jako projekt. IDE czytają i piszą pliki bezpośrednio - Super Brain działa tak samo jak w pozostałych ścieżkach.

### Instrukcja

1. Otwórz swoje IDE
2. **File -> Open Folder** (albo odpowiednik) -> wskaż folder Super Brain
3. Otwórz chat/agent AI wbudowany w IDE
4. **Test:** napisz:

```
Przeczytaj CLAUDE.md i powiedz mi co widzisz.
```

5. **Uruchom skilla:**

```
Przeczytaj 1-Skills/second-brain-setup/SKILL.md i wykonaj workflow opisany w tym pliku.
```

---

## Po konfiguracji - pierwsze zadania

Niezależnie od ścieżki, po uruchomieniu skilla `second-brain-setup` i wypełnieniu profilu, masz dwa zadania:

### 1. Migracja kontekstu z Cyfrowego Bliźniaka

Twój Cyfrowy Bliźniak z pierwszej lekcji miał kontekst - kim jesteś, jak pracujesz. Skill `second-brain-setup` pozwala Ci przenieść ten kontekst do Super Brain. Jeśli masz wyniki Gallup CliftonStrengths, DISC, MBTI lub innego testu - wklej je podczas konfiguracji. AI wyciągnie z nich to, co zmienia sposób współpracy.

### 2. Aktualizacja projektu FashionHero

Masz już za sobą tydzień pracy - wybrałeś feature, zbudowałeś prototyp w Lovable. Czas przenieść to do Super Brain. Napisz do AI:

```
Przeczytaj zewnętrznym repozytorium projektu. Mam update z pierwszego tygodnia
pracy. Chcę opisać jaki feature wybrałem, co zbudowałem w Lovable i co
z tego wynikło. Pomóż mi to ustrukturyzować.
```

AI zapyta Cię o szczegóły i zapisze ustrukturyzowane notatki do odpowiednich podfolderów projektu (decisions/, prototypes/, analyses/).

---

## Coś nie działa?

| Problem | Rozwiązanie |
|---|---|
| AI nie widzi plików | Sprawdź czy otworzyłeś FOLDER Super Brain, nie pojedynczy plik |
| OpenCode: `/connect` nie działa | Upewnij się, że masz najnowszą wersję z https://opencode.ai/download |
| Obsidian nie pokazuje folderów | Wybierz "Open folder as vault" (nie "Create new vault") |
| Skill nie działa jako slash command | Użyj metody ad-hoc: "Przeczytaj SKILL.md i wykonaj workflow" |
| about.md jest pusty po uruchomieniu skilla | AI powinno było zapisać plik. Sprawdź w Obsidian. Jeśli pusty - uruchom ponownie. |

Nic nie pomaga? Circle, kanał `#vault-onboarding`.
