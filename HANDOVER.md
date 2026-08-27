# Handover — Weitblick am Rammenfeld

Ten plik jest punktem startowym dla kolejnej sesji. Przeczytaj go przed zmianami w projekcie.

## Projekt i publikacja

- Strona: https://radoslawdeboszcloud-alt.github.io/greenrest/
- Repozytorium: `https://github.com/radoslawdeboszcloud-alt/greenrest.git`
- Gałąź publikowana: `main`.
- GitHub Actions publikuje GitHub Pages po pushu na `main` (workflow: `.github/workflows/deploy-pages.yml`).
- Projekt jest statyczny: `index.html`, `styles.css`, `news.txt`, `availability-demo.ics` i `assets/`.

## Marka i dane obiektu

- Nazwa: **Weitblick am Rammenfeld**.
- Adres widoczny na stronie / Google Maps: `Rammenfeld 8A, 54614 Schönecken`.
- Telefon / WhatsApp: `015901624869` (`+49 159 01624869`).
- E-mail: `activeurlaub@gmail.com`.
- Rezerwacja: https://www.booking.com/Share-9QRbYH
- Strona działa w językach PL i DE; domyślnie ładuje PL.

## Materiały źródłowe

- Wypełniony formularz i zdjęcia klienta: `F:\RADO_IT_STRONY\Dane\Ferienwohnung Jurek Materiały`.
- Zrzuty ekranowe do oceny: `F:\RADO_IT_STRONY\Dane\Ferienwohnung Jurek Materiały\CODEX`.
- Nie dodawaj do Git pliku `FORMULARZ.docx` w głównym katalogu projektu — jest to lokalny materiał roboczy użytkownika.

## Aktualny wygląd hero

- Zdjęcie hero: `assets/hero-weitblick.png`; zawiera wbudowany napis „Weitblick am Rammenfeld” po lewej oraz pasek udogodnień u dołu.
- Desktop: hero jest wysokie (`min-height: max(94vh, 66.667vw)`), aby pokazywać dolny pasek; zdjęcie jest pozycjonowane od lewego górnego rogu.
- Desktop: nagłówek strony znajduje się po prawej, bez tła/karty, z cieniem dla czytelności.
- Mobile: zdjęcie jest pozycjonowane od prawego górnego rogu, aby ukryć wbudowany napis ze zdjęcia i uniknąć kolizji z wyśrodkowanym nagłówkiem HTML. Przyciski hero układają się pionowo.
- Jeżeli zmieniasz hero, koniecznie sprawdź desktop i mobile — jest to najbardziej wrażliwy fragment układu.

## Funkcje strony

- Przełącznik PL/DE jest w JavaScript na końcu `index.html`; wywołanie `setLanguage(activeLanguage())` przy starcie jest ważne dla poprawnego PL na pierwszym załadowaniu.
- Galeria ma 14 zdjęć klienta, zdefiniowanych w tablicy `galleryItems` w `index.html`.
- Aktualności są ładowane z `news.txt`. Edycja ma format `Klucz=Wartość`; obraz wskazuje pole `Image`.
- „Rent a Quad” zastąpił wcześniejsze „Rent a Bike”.
- Rezerwacja prowadzi bezpośrednio do Booking.com; testowy Smoobu został usunięty.
- `availability-demo.ics` wraz z kodem w `index.html` prezentuje przykładowy kalendarz dostępności na trzy miesiące. Jest oznaczony jako dane demonstracyjne.
  - To nie jest integracja z Booking.com.
  - Gdy klient poda publiczny adres `.ics`, zmień `data-ical-url="availability-demo.ics"` w sekcji rezerwacji i sprawdź w przeglądarce CORS / odczyt pliku.
  - iCal synchronizuje dostępność, ale nie umożliwia złożenia rezerwacji; prawdziwy link Booking pozostaje przyciskiem CTA.
- Modal Impressum celowo zawiera pola „do uzupełnienia” — klient nie podał kompletnych danych formalnych.

## Nawigacja i responsywność

- Nawigacja desktopowa jest sticky.
- Wszystkie sekcje z `id` mają `scroll-margin-top: 96px`, żeby kliknięcie w menu nie chowało nagłówka za paskiem.
- Menu mobilne (`max-width: 760px`) zaczyna się na `top: 118px` i ma wyższy `z-index`; wcześniej „O nas” było częściowo zasłonięte przez górny pasek.

## Obrazy dodane do `assets/`

Najważniejsze: `hero-weitblick.png`, `gallery-salon-view.png`, `gallery-kitchen.png`, `gallery-bathroom.png`, `gallery-bedroom-1.png`, `gallery-bedroom-2.png`, `gallery-equipment.png`, `gallery-sunset-quad.jpg`, `gallery-cave.png`, `gallery-bench.jpg`, `gallery-misty-panorama.png`, `gallery-panorama.jpg`, `gallery-ruins.jpg`, `gallery-trails.png`.

## Praca i publikacja

1. Sprawdź `git status --short` — zachowaj cudze / lokalne zmiany.
2. Wprowadzaj edycje przez `apply_patch`.
3. Sprawdź `git diff --check`.
4. Jeżeli użytkownik prosi o publikację: dodaj tylko pliki związane z zadaniem, commit i `git push origin main`.
5. Po pushu publikacja GitHub Pages trwa zwykle kilka minut.

## Otwarte tematy

- Uzupełnić kompletne Impressum przed formalną publikacją.
- W razie potrzeby podmienić demonstracyjny iCal na rzeczywisty adres eksportu kalendarza obiektu.
- Przy zmianach hero zawsze ocenić zrzuty desktop/mobile; użytkownik aktywnie dopracowuje ten obszar.
