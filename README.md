## Parę słów o
Na tej stronie można szlifować słówka z j. angielskiego z **repetytorium Express Publishing (podstawa i rozszerzenie)** w dwóch formach - lista słówek i quizy. W pierwszym przypadku dostajemy po prostu alfabetyczną listę słówek. W drugim przypadku strona wybiera **15** losowych słówek po polsku i należy napisać ich angielskie odpowiedniki. Po zakończeniu testu ukazuje się podsumowanie i z jego poziomu można powtórzyć test, tym razem tylko z rzeczy, których nie udało się odgadnąć.

## Technikalia
Model SI **Claude Sonnet** generuje plik JSON na podstawie zdjęcia repetytorium ze słówkami. Po wrzuceniu go do tego repozytorium GitHub Actions automatycznie aktualizuje plik `index.json` z listą wszystkich rozdziałów, a następnie generuje spis treści widoczny na stronie głównej. Po wybraniu rozdziału stronka pobiera potrzebny JSON i wyświetla listę słówek, jak i quiz.

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
    └── index.json                    ← generowany automatycznie
```