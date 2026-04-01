# Platforma Egzaminacyjna Doradcy Inwestycyjnego

Kompletna, modułowa platforma quizów dla egzaminu Doradcy Inwestycyjnego (EDIP) zbudowana z czystym HTML, CSS i JavaScript.

## 📁 Struktura Projektu

```
VIbe coding/
├── index.html                 # Strona główna - wybór testów
├── css/
│   └── style.css             # Wszystkie style CSS
├── data/
│   ├── questions.json        # Wszystkie pytania (110)
│   └── answer_key.json       # Klucz odpowiedzi
├── quizzes/
│   ├── quiz1.html            # Test 1 (pytania 1-30)
│   ├── quiz2.html            # Test 2 (pytania 31-60)
│   ├── quiz3.html            # Test 3 (pytania 61-90)
│   └── quiz4.html            # Test 4 (pytania 91-110)
├── Questions/                # Oryginalne pliki PDF (referencja)
├── js/                       # Folder na dodatkowe skrypty (opcjonalnie)
└── README.md                 # Ten plik
```

## 🚀 Jak Używać

### Lokalnie
```bash
cd "/Users/ivan01/Desktop/VIbe coding"
# Na Mac:
open index.html
# Na Windows:
start index.html
```

### Na Serwerze WWW
1. Skopiuj całą strukturę folderów na serwer
2. Otwórz `index.html` w przeglądarce
3. Wszystko będzie działać!

## 📋 Struktura Testów

| Test | Pytania | Zakres |
|------|---------|--------|
| Test 1 | 30 | 1-30 |
| Test 2 | 30 | 31-60 |
| Test 3 | 30 | 61-90 |
| Test 4 | 20 | 91-110 |

**Razem: 110 pytań**

## ✨ Funkcje

✅ **Strona główna (index.html)**
- Wybór testów
- Informacje o egzaminie
- Statystyki

✅ **Indywidualne quizy (quizzes/quiz1-4.html)**
- Wyświetlanie pytań jedno po drugim
- Przycisk "Wstecz" i "Dalej"
- Pasek postępu
- Przycisk "Wyjdź z Quizu" z potwierdzeniem
- Natychmiastowa informacja zwrotna (zielone/czerwone)
- Powtórka quizu

✅ **Strona wyników**
- Status zaliczenia/niezaliczenia (próg: 40 pkt)
- Łączny wynik
- Liczba poprawnych/niepoprawnych odpowiedzi
- Procentowy rozkład
- Szczegółowy rozkład punktów:
  - Poprawne: +2 pkt każda
  - Niepoprawne: -1 pkt każda
  - Puste: 0 pkt

✅ **Responsywny design**
- Działa na desktopie, tablecie i telefonie
- Wszystko w polskim interfejsie

## 🎯 System Punktacji

| Akcja | Punkty |
|-------|--------|
| Poprawna odpowiedź | +2 |
| Niepoprawna odpowiedź | -1 |
| Brak odpowiedzi | 0 |

**Próg zaliczenia:** 40 punktów (dla testu 30-pytań)

### Przykłady:
- 20 poprawnych: 20×2 = 40 pkt → ✓ ZALICZONE
- 19 poprawnych: 19×2 = 38 pkt → ✗ NIEZALICZONE
- 15 poprawnych + 10 niepoprawnych + 5 pustych: (15×2) + (10×-1) = 20 pkt → ✗ NIEZALICZONE

## 📂 Opis Plików

### index.html (2.8 KB)
Strona główna z:
- Nagłówkiem i statystykami
- Kartami testów
- Linkami do poszczególnych quizów

### css/style.css
Wszystkie style CSS:
- Layout i responsywność
- Kolory i animacje
- Styling przycisków i opcji
- Style wyników

### data/questions.json (85 KB)
Wszystkie 110 pytań w formacie JSON:
```json
[
  {
    "number": 1,
    "text": "Pytanie...",
    "options": {
      "A": "Opcja A",
      "B": "Opcja B",
      "C": "Opcja C",
      "D": "Opcja D"
    }
  },
  ...
]
```

### data/answer_key.json (1.6 KB)
Klucz odpowiedzi:
```json
{
  "answers": {
    "1": "B",
    "2": "B",
    ...
    "110": "B"
  }
}
```

### quizzes/quiz1.html - quiz4.html
Indywidualne pliki quizów, każdy zawiera:
- Embedded pytania dla danego testu
- Klucz odpowiedzi
- Kompletną logikę quizu
- Stylizację

## 🔧 Dostosowywanie

### Zmiana Progu Zaliczenia
W pliku `quizzes/quiz*.html` szukaj:
```javascript
const PASS_SCORE = 40;  // Zmień na inną wartość
```

### Zmiana Systemu Punktacji
W plikach quizów szukaj:
```javascript
const CORRECT_POINTS = 2;      // Punkty za poprawną
const INCORRECT_POINTS = -1;   // Punkty za złą
```

### Zmiana Kolorów
W pliku `css/style.css` szukaj:
- `#667eea` - niebieski główny
- `#764ba2` - fioletowy główny
- `#28a745` - zielony (poprawna)
- `#dc3545` - czerwony (niepoprawna)

## 📱 Kompatybilność

- ✅ Chrome 60+
- ✅ Firefox 55+
- ✅ Safari 12+
- ✅ Edge 79+
- ✅ Przeglądarki mobilne

## 🌐 Wdrażanie

### Lokal
Otwórz `index.html` bezpośrednio w przeglądarce

### Serwer WWW
```bash
# Skopiuj wszystko na serwer
cp -r * user@server:/var/www/quiz/
```

Następnie otwórz: `https://yoursite.com/quiz/index.html`

## 📝 Notatki Techniczne

- **Brak zależności:** Pure HTML/CSS/JavaScript
- **Bez serwera:** Wszystko działa offline
- **Responsive:** Dostosowuje się do każdego ekranu
- **Polska:** Cały interfejs w języku polskim
- **Modułowy:** Każdy quiz to niezależny plik

## 🚀 Przyszłe Usprawnienia

Możliwe rozszerzenia:
- Backend do zapisywania wyników
- Historia wyników użytkownika
- Analityka i raporty
- Tryb offline z synchronizacją
- Aplikacja mobilna

## ✅ Gotowe do Użycia!

Wszystko jest przygotowane. Otwórz `index.html` i zacznij praktykować! 🎓

---

**Stworzone:** Kwiecień 2025
**Egzamin:** Doradca Inwestycyjny (EDIP)
**Pytania:** 110
**Testy:** 4
**Język:** Polski
