# Słówka – Setup na GitHub Pages

## Struktura plików
```
slowka/
├── index.html                        ← strona główna (wybór rozdziału)
├── quiz.html                         ← quiz
├── lista.html                        ← lista słówek A–Z
├── .github/
│   └── workflows/
│       └── build-index.yml           ← automatyczny skrypt
└── rozdzialy/
    ├── rozdzial-4-2-praca.json       ← rozdział 4 cz. 2
    └── index.json                    ← generowany automatycznie (nie edytuj!)
```

---

## Jednorazowy setup

### 1. Załóż konto na GitHub
Wejdź na https://github.com i zarejestruj się.

### 2. Utwórz nowe repozytorium
- Kliknij "+" → "New repository"
- Nazwa: `slowka` (lub dowolna)
- Ustaw jako **Public**
- Kliknij "Create repository"

### 3. Wgraj pliki
- W nowym repo kliknij "uploading an existing file"
- Wgraj wszystkie pliki zachowując strukturę folderów:
  - `index.html`, `quiz.html`, `lista.html` → główny folder
  - `build-index.yml` → do `.github/workflows/`
  - `rozdzial-4-2-praca.json` → do `rozdzialy/`
- Kliknij "Commit changes"

### 4. Włącz GitHub Pages
- Wejdź w **Settings** → **Pages**
- Source: **Deploy from a branch**
- Branch: **main** / folder: **/ (root)**
- Kliknij "Save"

### 5. Gotowe!
Po chwili strona będzie dostępna pod adresem:
`https://TWOJA_NAZWA.github.io/slowka`

---

## Dodawanie nowego rozdziału

1. Dostań plik JSON od Claude (np. `rozdzial-5-1-technologia.json`)
2. Wejdź na GitHub → folder `rozdzialy/`
3. Kliknij **"Add file"** → **"Upload files"**
4. Wgraj plik i kliknij **"Commit changes"**
5. GitHub Actions automatycznie zaktualizuje `index.json` (~30 sekund)
6. Nowy rozdział pojawia się na stronie!

---

## Nazewnictwo plików JSON
```
rozdzial-{numer}-{czesc}-{temat}.json

Przykłady:
rozdzial-4-1-praca.json
rozdzial-4-2-praca.json
rozdzial-5-1-szkola.json
```

## Format pliku JSON
```json
{
  "name": "Rozdział 4, cz. 2 – Praca",
  "date": "2026-03-11",
  "words": [
    {"pl": "szef", "en": "boss"},
    {"pl": "pracownik", "en": "employee"}
  ]
}
```
