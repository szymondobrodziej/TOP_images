# 🛋️ Katalog Produktów TOP Meble

Nowoczesna aplikacja do przeglądania i pobierania zdjęć produktów z katalogu TOP Meble.

## ✨ Funkcje

- 🔍 **Wyszukiwanie** - przeszukuj produkty po nazwie, opisie, kategorii i wszystkich atrybutach
- 🏷️ **Filtry kategorii** - filtruj produkty według kategorii
- 📊 **Sortowanie** - sortuj po cenie, nazwie lub dostępności
- ✅ **Zaznaczanie produktów** - wybierz produkty do pobrania zdjęć
- 📥 **Pobieranie zdjęć** - pobierz główne zdjęcia lub wszystkie zdjęcia zaznaczonych produktów
- 📁 **Archiwum ZIP** - zdjęcia organizowane w foldery według numeru katalogowego
- 🖼️ **Modal szczegółów** - pełna galeria, opis i specyfikacja produktu
- 📱 **Responsywny design** - działa na desktop, tablet i mobile
- 🎨 **Nowoczesny UI** - elegancki design dopasowany do branży meblowej

## 🚀 Uruchomienie lokalne

Wystarczy otworzyć plik `index.html` w przeglądarce:

```bash
open index.html
```

Lub uruchom lokalny serwer:

```bash
# Python 3
python3 -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000

# Node.js (jeśli masz zainstalowany npx)
npx serve
```

Następnie otwórz: http://localhost:8000

## 📦 Deployment na GitHub Pages

### Krok 1: Utwórz repozytorium na GitHub

1. Przejdź na https://github.com/new
2. Nazwij repozytorium np. `top-katalog`
3. Ustaw jako publiczne
4. Kliknij "Create repository"

### Krok 2: Wypchnij kod

```bash
# Zainicjuj git (jeśli jeszcze nie jest)
git init

# Dodaj pliki
git add .

# Commit
git commit -m "Initial commit - Katalog produktów TOP Meble"

# Dodaj remote (zamień na swój URL)
git remote add origin https://github.com/TWOJA_NAZWA/top-katalog.git

# Wypchnij
git branch -M main
git push -u origin main
```

### Krok 3: Aktywuj GitHub Pages

1. Przejdź do ustawień repozytorium: `Settings` → `Pages`
2. W sekcji "Source" wybierz `main` branch
3. Kliknij `Save`
4. Po chwili strona będzie dostępna pod adresem:
   ```
   https://TWOJA_NAZWA.github.io/top-katalog/
   ```

## 🛠️ Technologie

- **HTML5** - struktura
- **CSS3** - nowoczesny design z gradientami i animacjami
- **Vanilla JavaScript** - logika aplikacji (zero dependencies)
- **JSZip** - generowanie archiwów ZIP
- **GitHub Pages** - hosting statyczny

## 📋 Struktura XML

Aplikacja pobiera dane z:
```
https://b2b.topeshop.pl/pl/purchases/articles/exportxmlview
```

### Format oczekiwanego XML:

```xml
<offers>
  <group name="category">
    <o id="uuid" price="259.05" stock="144">
      <cat><![CDATA[ Kategoria ]]></cat>
      <name><![CDATA[ Nazwa produktu ]]></name>
      <imgs>
        <main url="url_do_głównego_zdjęcia"/>
        <i url="url_do_zdjęcia_1"/>
        <i url="url_do_zdjęcia_2"/>
      </imgs>
      <desc><![CDATA[ Opis HTML ]]></desc>
      <techdesc><![CDATA[ Specyfikacja HTML ]]></techdesc>
      <attrs>
        <a name="Numer_katalogowy"><![CDATA[ KOD123 ]]></a>
        <a name="EAN"><![CDATA[ 1234567890 ]]></a>
      </attrs>
    </o>
  </group>
</offers>
```

## 🎨 Customizacja

### Zmiana kolorów

Edytuj zmienne CSS w `index.html`:

```css
:root {
    --primary: #8B7355;    /* Główny brąz */
    --secondary: #D4C5B9;  /* Beż */
    --accent: #B8956A;     /* Złoty akcent */
    --bg: #FAFAF8;         /* Tło */
    --text: #2C2C2C;       /* Tekst */
}
```

### Zmiana URL XML

W pliku `index.html`, znajdź funkcję `fetchXML()` i zmień URL:

```javascript
const url = 'TWÓJ_URL_DO_XML';
```

## 🐛 Rozwiązywanie problemów

### Problem z CORS

Jeśli pojawia się błąd CORS, aplikacja automatycznie użyje proxy. Alternatywnie:

1. Zainstaluj rozszerzenie CORS do przeglądarki
2. Użyj lokalnego serwera proxy
3. Skonfiguruj CORS na serwerze z XML

### Zdjęcia się nie ładują

Sprawdź czy URLe w XML są poprawne i dostępne publicznie.

## 📄 Licencja

MIT License - użyj swobodnie w swoich projektach!

## 🤝 Wkład

Pull requesty są mile widziane! Dla większych zmian, otwórz najpierw issue.

---

Made with ❤️ for TOP Meble
