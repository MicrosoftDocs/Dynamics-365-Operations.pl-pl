---
title: Intrastat — Polska
description: Ten temat zawiera informacje o raportowaniu Intrastat w Polsce.
author: andosip
ms.date: 11/09/2021
ms.topic: article
audience: Application User
ms.reviewer: kfender
ms.search.region: Global
ms.author: v-aosipov
ms.search.validFrom: ''
ms.openlocfilehash: 9564892f768adb8f48208fe10b31c7c6392a4567
ms.sourcegitcommit: f4823a97c856e9a9b4ae14116a43c87f9482dd90
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/09/2021
ms.locfileid: "7779914"
---
# <a name="polish-intrastat"></a>Intrastat — Polska

[!include[banner](../includes/banner.md)]

Strona **Intrastat** służy do generowania i raportowania informacji o handlu między krajami Unii Europejskiej (UE). Polska deklaracja Intrastat zawiera informacje o handlu towarami do zgłoszenia.

W polskiej deklaracji Intrastat znajdują się następujące pola. Wszystkie pola są uwzględniane w dostawach i wysyłkach, z wyjątkiem **RodzajTransportu** (trybu transportu) i **KrajPochodzenia** (kraju lub regionu pochodzenia), które nie są uwzględnione w wysyłkach, oraz **IdKontrahenta** (obcy numer VAT odbiorcy), które nie są uwzględniane w wysyłkach.

| Nazwa pola | Opis |
|-------------------------|-------------------------|
| Deklaracja Data | Data utworzenia dokumentu. |
| Miesiac | Miesiąc odwołania deklaracji. |
| Rok | Rok odwołania deklaracji. |
| Numer | Numer deklaracji w okresie odniesienia. |
| Wersja | Numer wersji deklaracji. |
| NrWlasny | Identyfikator deklaracji. Wartość jest generowana automatycznie. |
| Typ | Kierunek raportu.</br><li>W przypadku przyjścia jest drukowana etykieta „P”.</li><li>W wysyłkach jest drukowany „W”.</li> |
| Rodzaj | Rodzaj deklaracji. Wartość wskazuje, czy raport jest deklaracją oryginalną, czy deklaracją korygującą. |
| UC | Kod jednostki, do której adresowana jest deklaracja Intrastat. Ta wartość jest określana w polu **Numer identyfikacji podatkowej** w sekcji **Podatek** na karcie **Agent** na stronie **Parametry handlu zagranicznego**. |
| Nazwa | Nazwa firmy. |
| Miejscowosc, UlicaNumer, KodPocztowy | Pełny adres firmy. |
| Nip | Polski numer identyfikacji podatkowej (VAT). |
| Regon | Polski numer statystyczny (numer przedsiębiorstwa). |
| LacznaWartoscFaktur | Suma wartości faktury. |
| LacznaWartoscStatystyczna | Suma wartości statystycznych. |
| LacznaLiczbaPozycji | Całkowita liczba pozycji towarowych. |
| PozId | Numer kolejny danego towaru. |
| OpisTowaru | Nazwa handlowa towaru. |
| KrajPochodzeniaWysylki | Kod Międzynarodowej Organizacji Normalizacyjnej (ISO) dla kraju lub regionu kontrahenta. |
| WarunkiDostawy | Kod Intrastat warunków dostawy. |
| RodzajTransakcji | Kod wskazujący charakter transakcji. Polskie firmy stosują dwucyfrowe kody transakcji. |
| KodTowarowy | Ośmiu cyfrowy kod asortymentu zgodnie z Nazewnictwami Łączony. |
| RodzajTransportu | Kod Intrastat dla rodzaju transportu. |
| KrajPochodzenia | Kod ISO kraju lub regionu, w którym wytworzono lub wytworzono towary. |
| MasaNetto | Masa netto w pełnych kilogramach. |
| IloscUzupelniajacaJm | Ilość w dodatkowej jednostka miary w liczbach całych. |
| WartoscFaktury | Wartość faktury wszystkich transakcji, które są pokryte przez jedną pozycję. |
| WartoscStatystyczna | Wartość statystyczna. |
| Wypelniajacy: NazwiskoImie, Telefon, Faks, Email | Imię i nazwisko, numer telefonu, numer faksu i adres e-mail osoby, która przesyła deklarację. |
| IdKontrahenta | Obcy numer VAT odbiorcy w kraju członkowskim UE. |


## <a name="set-up-intrastat"></a>Konfiguracja Intrastat

Z repozytorium globalnego zaimportuj najnowszą wersję następujących konfiguracji raportowania elektronicznego (ER):

   - Model Intrastat
   - Raport Intrastat
   - Intrastat (PL)

Więcej informacji można znaleźć w temacie [Pobieranie konfiguracji ER z globalnego repozytorium usługi Configuration service](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

## <a name="set-up-a-vat-id-and-an-enterprise-number-for-your-company"></a>Skonfiguruj identyfikator VAT i numer przedsiębiorstwa w firmie

### <a name="create-registration-types-for-company-codes"></a>Tworzenie typów rejestracji dla kodów firmy

Dla kodów firmy należy utworzyć dwa typy rejestracji: jeden dla identyfikatora VAT (kod NIP) i jeden dla numeru przedsiębiorstwa (kod Regon).

1. Wybierz kolejno opcje **Administrowanie organizacją** > **Globalna książka adresowa** > **Typy rejestracji** > **Typy rejestracji**.
2. W okienku akcji wybierz opcję **Nowy**, aby utworzyć typ rejestracji dla identyfikatora VAT.
3. W nowym oknie dialogowym **Podaj szczegóły typu rejestracji**, w polu **Nazwa** wprowadź nazwę nowego typu rejestracji. Na przykład wpisz **NIP**.
4. W polu **kraj/region** wybierz **POL**.
5. Wybierz opcję **Utwórz**.
6. W okienku akcji wybierz opcję **Nowy**, aby utworzyć typ rejestracji dla identyfikatora firmy.
7. W nowym oknie dialogowym **Podaj szczegóły typu rejestracji**, w polu **Nazwa** wprowadź nazwę nowego typu rejestracji. Na przykład wpisz **Regon**.
8. W polu **kraj/region** wybierz **POL**.
9. Wybierz opcję **Utwórz**.

### <a name="match-the-registration-types-with-registration-categories"></a>Dopasuj typy rejestracji do kategorii rejestracji

1. Wybierz kolejno opcje **Administrowanie organizacją** > **Globalna książka adresowa** > **Typy rejestracji** > **Kategorie rejestracji**.
2. W okienku akcji wybierz opcję **Nowy**, aby utworzyć łącze między każdym utworzonym typem rejestracji a kategorią rejestracji.

    - Dla typu rejestracji dla identyfikatora VAT (kod NIP) wybierz kategorię rejestracji **identyfikatorów VAT**.
    - Jako typ rejestracji dla numeru przedsiębiorstwa (kod regionu) wybierz kategorię rejestracji **Identyfikator przedsiębiorstwa (KOD)**.

### <a name="set-up-a-vat-id-and-an-enterprise-number-for-your-company"></a>Skonfiguruj identyfikator VAT i numer przedsiębiorstwa w firmie

1. Wybierz kolejno opcje **Administrowanie organizacją** > **Organizacje** > **Firmy**.
2. W siatce wybierz swoją firmę.
3. W okienku akcji wybierz pozycję **Identyfikatory rejestracyjne**.
4. Na skróconej karcie **Identyfikatory rejestracyjne** wybierz pozycję **Dodaj**.
5. W polu **Typ rejestracji** wybierz jeden z utworzonych wcześniej typów rejestracji.
6. Wprowadź identyfikator VAT firmy (kod NIP) lub numer przedsiębiorstwa (kod Regon), w zależności od typu rejestracji wybranego w poprzednim kroku.
7. Powtórz kroki od 4 do 6 dla innych utworzonych wcześniej typów rejestracji.

## <a name="set-up-a-company-address"></a>Ustaw adres firmy

1. Wybierz kolejno opcje **Administrowanie organizacją** > **Organizacje** > **Firmy**.
2. W siatce wybierz swoją firmę.
3. Na karcie **Adresy** wybierz pozycję **Edytuj**.
4. W oknie dialogowym **Edycja adresu** w polu **Kod pocztowy** wybierz kod pocztowy firmy.
5. W **polu Ulica** wprowadź adres.
6. W polu **Miasto** wybierz swoje miasto.

## <a name="set-up-foreign-trade-parameters"></a>Konfigurowanie parametrów handlu zagranicznego

1. Wybierz kolejno opcje **Podatek** > **Ustawienia** > **Parametry handlu zagranicznego**.
2. Na karcie **Intrastat**, na skróconej karcie **Intrastat** w polu **Mapowanie formatu pliku** wybierz pozycję **Intrastat (PL)**.
3. W polu **Mapowanie formatu raportów** wybierz wartość **Raport Intrastat**.
4. Na skróconej karcie **hierarchii kodów asortymentu** w polu **Hierarchia kategorii** wybierz pozycję **Intrastat**.
5. W polu **Kod transakcji** wybierz kod transakcji dla przeniesień właściwości. Kod ten będzie wykorzystywany do tworzenia transakcji powodujących faktyczne lub planowane przeniesienie własności za odszkodowaniem (finansowej lub innej). Można go również użyć do poprawek. Firmy w Polsce stosują dwucyfrowe kody transakcji.
6. W polu **Nota kredytowa** wybierz kod transakcji zwrotu towarów.
7. Na karcie **Właściwości kraju/regionu**, w polu **Kraj/region**, podaj listę wszystkich krajów lub regionów, w których organizacja prowadzi interesy. Dla każdego kraju należącego do UE wybierz pozycję **Typ UE** w polu **Typ kraju/regionu**, aby kraj były wyświetlany w raporcie Intrastat. Wybierz opcję **Krajowy** w polu **Typ kraju/regionu**.
8. Na karcie **Agent**, na skróconej karcie **agenta**, w sekcji **Numer podatku**, w polu **Numer identyfikacji podatkowej** wprowadź wartość **420000**, aby wskazać kod jednostki, do których jest adresowana deklaracja Intrastat.
9. W zakładce **Kontakt** wpisz imię i nazwisko, numer telefonu, numer faksu oraz adres e-mail osoby składającej oświadczenie.
10. Na karcie **Sekwencje numerów**, w polu **Kod sekwencji numerów** dla odwołania do **pliku XML** określ nieuchamiętną sekwencję numerów o maksymalnej liczbie 9 znaków. To pole służy do automatycznego generowania wartości pola **Identyfikator deklaracji** w raporcie Intrastat.

## <a name="set-up-product-parameters-for-the-intrastat-declaration"></a>Konfigurowanie parametrów produktu na potrzeby deklaracji Intrastat

1. Przejdź do **Zarządzanie informacjami o produktach** > **Produkty** > **Zwolnione produkty**.
2. Wybierz produkt w siatce.
3. Na skróconej karcie **Handel zagraniczny**, w sekcji **Intrastat**, w polu **Asortyment** wybierz odpowiedni kod asortymentu. Nazwa asortymentu zostanie wydrukowana w polu **Opis towarów** w raporcie Intrastat.
4. W sekcji **Źródło** w polu **Kraj/region** wybierz kraj lub region pochodzenia produktu.
5. Na skróconej karcie **Zarządzanie zapasami** w polu **Waga netto** wprowadź masę produktu w kilogramach.

## <a name="set-up-compression-of-intrastat"></a>Ustawianie kompresji Intrastat

-   Przejdź do **Podatek** > **Ustawienia** > **Handel zagraniczny** > **Kompresja Intrastat** i wybierz pola, które należy porównać, gdy informacje Intrastat podsumowano. Dla polskiego Intrastat określ wartości w następujących obowiązkowych polach:

    - Asortyment
    - Kod transakcji
    - Kraj/region pochodzenia
    - Transport
    - Warunki dostawy
    - Kraj/region nadawcy
    - Kraj/region
    - Korekta
    - Numer identyfikacji podatkowej
    - Kierunek
    - Faktura

## <a name="set-up-the-transport-method-and-delivery-terms"></a>Ustaw metodę transportu i warunki dostawy

1.  Skonfiguruj kody transportu.

    1. Wybierz kolejno opcje **Podatek** > **Ustawienia** > **Handel zagraniczny** > **Metoda transportu**.
    2. W okienku akcji wybierz opcję **Nowy**.
    3. W polu **Transport** wpisz unikalny kod. Polskie firmy stosują jednocyfrowe kody transportowe.

2.  Ustawianie kodów Intrastat trybu dostawy.

    1. Przejdź do **Zaopatrzenie i sourcing** > **Ustawienia** > **Dystrybucja** > **Warunki dostarczenia**.
    2. W siatce wybierz zestaw warunków dostawy.
    3. Na skróconej karcie **Ogólne** w polu **Kod Intrastat** wpisz unikalny kod.

## <a name="intrastat-transfer"></a>Przeniesienie do Intrastat

Na stronie **Intrastat** w okienku akcji możesz wybrać **Transfer**, aby automatycznie przesyłać informacje o handlu wewnątrzwspólnotowym z zamówień sprzedaży, faktur niezależnych, zamówień zakupu, faktur od dostawców, pokwitowań produktów od dostawców , faktury projektowe i zlecenia przeniesienia. Przekazywane będą tylko dokumenty, w których krajem lub regionem przeznaczenia lub przesyłki jest kraj UE.

Transakcje można również wprowadzać ręcznie, wybierając opcję **Nowe** w okienku akcji.

### <a name="generate-an-intrastat-report"></a>Wygeneruj raport Intrastat

1. Wybierz kolejno opcje **Podatek** > **Deklaracje** > **Handel zagraniczny** > **Intrastat**.
2. W okienku akcji wybierz pozycję **Dane wyjściowe** &gt; **Raport**.
3. W oknie dialogowym **Raport Intrastat** można ustawić następujące pola.

    | Pole | Opis |
    |-------------------------|-------------------------|
    | Data rozpoczęcia | Wybierz datę rozpoczęcia raportu. |
    | Generuj plik | Ustaw tę opcję na wartość **Tak**, aby był generowany plik .xml raportu Intrastat. |
    | Nazwa pliku | Umożliwia wprowadzanie nazwy pliku .xml. |
    | Generuj raport | Ustaw tę opcję na wartość **Tak**, aby był generowany plik .xlsx raportu Intrastat. |
    | Nazwa pliku raportu | Umożliwia wprowadzanie nazwy pliku .xlsx. |
    | Kierunek | Wybierz **opcję Przyjęcia** do raportu o wewnątrzwspólnotowych przyjęć.</br>Wybierz **opcję Wysyłki** do raportu o wysyłkach wewnątrzwspólnotowych. |
    | Identyfikator deklaracji | Identyfikator dokumentu jest generowany automatycznie i może zostać zaktualizowany. |
    | Typ deklaracji | Wybierz **deklarację** dla oryginalnej deklaracji.</br>Wybierz opcję **Korekta deklaracji — zastąpienie** deklaracji korekty, która ma w pełni zastąpić istniejącą, poprzednio przesłaną deklarację oryginalną lub deklarację korekty. |
    | Miasto utworzenia dokumentu | W polu **Miejscowosc** deklaracji Intrastat należy wprowadzić wartość, która powinna być drukowana. |
    | Data utworzenia dokumentu | W polu **Deklaracja Data** deklaracji Intrastat należy wprowadzić wartość, która powinna być drukowana. |
    | Numer dokumentu | W polu **Numer** deklaracji Intrastat należy wprowadzić wartość, która powinna być drukowana. |
    | Wersja dokumentu | W polu **Wersja** deklaracji Intrastat należy wprowadzić wartość, która powinna być drukowana. |

4. Wybierz przycisk **OK** i przejrzyj wygenerowane raporty.

## <a name="example"></a>Przykład

Ten przykład pokazuje, jak księgować przyjęcia i wysyłki dla Intrastat przy użyciu firmy **DEMF**.

### <a name="preliminary-setup"></a>Konfiguracja wstępna

Zaimportuj najnowszą wersję następujących konfiguracji ER:

   - Model Intrastat
   - Raport Intrastat
   - Intrastat (PL)

### <a name="set-up-a-company-address"></a>Ustaw adres firmy

1. Wybierz kolejno opcje **Administrowanie organizacją** > **Globalna książka adresowa** > **Adresy** > **Utworzenie adresu**.
2. Na karcie **Miasto** wybierz opcję **nowa**.
3. W polu **kraj/region** wybierz **POL**.
4. W polu **Miasto** wpisz wartość **Warszawa**.
5. Na karcie **Kod pocztowy** wybierz opcję **Nowe**.
6. W polu **kraj/region** wybierz **POL**.
7. W polu **Miasto** wybierz **Warszawa**.
8. W polu **Kod pocztowy** wpisz **00-844**.
9. Wybierz kolejno opcje **Administrowanie organizacją** > **Organizacja** > **Firmy** i wybierz firmę **DEMF**.
10. Na skróconej karcie **Adresy** wybierz pozycję **Edytuj**.
11. W polu **kraj/region** wybierz **POL**.
12. W polu **Kod pocztowy** wybierz **31-111**.
13. W polu **Ulica** wprowadź adres **Statystyczna 22/1**.
14. W polu **Miasto** wybierz **Warszawa**.
15. Kliknij przycisk **OK**.

## <a name="set-up-a-vat-id-and-an-enterprise-number-code-for-your-company"></a>Skonfiguruj identyfikator VAT i numer przedsiębiorstwa dla swojej firmy

### <a name="create-registration-types-for-company-codes"></a>Tworzenie typów rejestracji dla kodów firmy

1. Wybierz kolejno opcje **Administrowanie organizacją** > **Globalna książka adresowa** > **Typy rejestracji** > **Typy rejestracji**.
2. W okienku akcji wybierz opcję **Nowy**, aby utworzyć typ rejestracji dla identyfikatora VAT (NIP).
3. W oknie dialogowym **Wprowadź szczegóły typu rejestracji** w polu **Nazwa** wpisz **NIP**.
4. W polu **kraj/region** wybierz **POL**.
5. Wybierz opcję **Utwórz**.
6. W okienku akcji wybierz opcję **Nowy**, aby utworzyć typ rejestracji dla identyfikatora firmy (Regon).
7. W oknie dialogowym **Wprowadź szczegóły typu rejestracji** w polu **Nazwa** wpisz **Regon**.
8. W polu **kraj/region** wybierz **POL**.
9. Wybierz opcję **Utwórz**.

### <a name="match-the-registration-types-with-registration-categories"></a>Dopasuj typy rejestracji do kategorii rejestracji

1. Wybierz kolejno opcje **Administrowanie organizacją** > **Globalna książka adresowa** > **Typy rejestracji** > **Kategorie rejestracji**.
2. W okienku akcji wybierz opcję **Nowy**, aby utworzyć łącze między każdym utworzonym typem rejestracji a kategorią rejestracji.

    - Dla typu rejestracji dla **NIP** wybierz kategorię rejestracji **identyfikatorów VAT**.
    - Dla typu rejestracji dla **Regon** wybierz kategorię rejestracji **Identyfikator przedsiębiorstwa (COID)**.

### <a name="set-up-a-vat-id-and-an-enterprise-number-for-your-company"></a>Skonfiguruj identyfikator VAT i numer przedsiębiorstwa w firmie

1. Wybierz kolejno opcje **Administrowanie organizacją** > **Organizacje** > **Firmy**.
2. W siatce zaznacz element **DEMF**.
3. W okienku akcji wybierz pozycję **Identyfikatory rejestracyjne**.
4. Na skróconej karcie **Identyfikatory rejestracyjne** wybierz pozycję **Dodaj**.
5. W polu **Typ rejestracji** wybierz **NIP**.
6. W polu **Numer rejestracyjny** wpisz **1234567890**.
7. Wybierz opcję **Dodaj**.
8. W polu **Typ rejestracji** wybierz **Regon**.
9. W polu **Numer rejestracyjny** wpisz **12345678901234**.

### <a name="set-up-a-number-sequence-code"></a>Skonfiguruj kod sekwencji liczb

1. Wybierz kolejno opcje **Administrowanie organizacją** > **Sekwencje numerów** > **Sekwencje numerów**.
2. W okienku akcji, na karcie **Sekwencja liczb**, w grupie **Nowe** wybierz **Sekwencja liczb**.
3. Na **skróconej karcie identyfikatorów** w polu **Kod sekwencji numerów** wprowadź **XML\_file**.
4. Na skróconej karcie **Parametry Scope** w polu **Scope** wybierz pozycję **Firma**.
5. W polu **Firma** wybierz wartość **DEMF**.
6. Na **skróconej karcie Segmenty** w polu **Długość** segmentu **alfanumerycznego** wprowadź wartość **4**.
7. Na skróconej karcie **Ogólne**, w sekcji **Konfiguracja** ustaw opcję **Ciągłe** na **Nie**.
8. W sekcji **Alokacja numeru** w polu **Największy** wprowadź wartość **9999**.

### <a name="set-up-foreign-trade-parameters"></a>Konfigurowanie parametrów handlu zagranicznego

1. Wybierz kolejno opcje **Podatek** > **Ustawienia** > **Handel zagraniczny** > **Parametry handlu zagranicznego**.
2. Na karcie **Intrastat**, na skróconej karcie **Ogólne**, w polu **Kod** **transakcji** wybierz wartość **11**.
3. Na skróconej karcie **Raportowanie elektroniczne** w polu **Mapowanie formatu pliku** wybierz pozycję **Intrastat (PL)**.
4. W polu **Mapowanie formatu raportów** wybierz wartość **Raport Intrastat**.
5. Na skróconej karcie **hierarchii kodów asortymentu** w polu **Hierarchia kategorii** upewnij się, że wybrano pozycję **Intrastat**.
6. Kliknij kartę **Właściwości kraju/regionu** i wybierz **Nowe**.
7. W polu **Kraj/region partii** wybierz **POL**. W polu **Typ kraju/regionu** wybierz opcję **Krajowy**.
8. W polu **Kraj/region partii** wybierz **DEU**. W polu **Typ kraju/regionu** wybierz opcję **UE**.
9. Na karcie **Agent**, na skróconej karcie **Agent**, w sekcji **Podatek od sprzedaży**, w polu **Numer zwolnienia podatkowego** wpisz **420000**.
10. Na karcie **Kontakt** w polu **Nazwa** wprowadź **Manish Chopra**.
11. W polu **Telefon** wprowadź datę faktury **425-555-5068**.
12. W polu **Numer faks** wprowadź wartość **425-555-5049**.
13. W polu **Adres e-mail** wprowadź **manishc@contoso.com**.
14. Na karcie **Sekwencje numerów** w polu **Kod sekwencji numerów** dla odwołania **numer pliku XML** wybierz **XML\_file**.

### <a name="set-up-product-information"></a>Konfigurowanie informacji o produktach

1. Przejdź do **Zarządzanie informacjami o produktach** > **Produkty** > **Zwolnione** **produkty**.
2. W siatce zaznacz element **D0001**.
3. Na skróconej karcie **Handel zagraniczny**, w sekcji **Intrastat**, w polu **Asortyment** wybierz **100 200 30**.
4. Na skróconej karcie **Zarządzanie zapasami** w sekcji **Pomiary wagi** w polu **Waga netto** wprowadź **2**.
5. Na okienku akcji wybierz opcję **Zapisz**.
6. W siatce zaznacz element **D0003**.
7. Na skróconej karcie **Handel zagraniczny**, w sekcji **Intrastat**, w polu **Asortyment** wybierz **100 200 30**.
8. W sekcji **Pochodzenie** w polu **kraj/region** wybierz **DEU**.
9. Na skróconej karcie **Zarządzanie zapasami** w sekcji **Pomiary wagi** w polu **Waga netto** wprowadź **5**.
10. Na okienku akcji wybierz opcję **Zapisz**.

### <a name="change-the-site-address"></a>Zmienianie adresu lokalizacji

1. Wybierz kolejno opcje **Zarządzanie magazynem** > **Ustawienia** > **Magazyn** > **Lokalizacje**.
2. W siatce zaznacz element **1**.
3. Na skróconej karcie **Adresy** wybierz pozycję **Edytuj**.
4. W oknie dialogowym **Edycja adresu** w polu **Kraj/region** wybierz pozycję **POL**.
5. Kliknij przycisk **OK**.

### <a name="set-up-a-transport-method"></a>Ustaw sposób transportu

1. Utwórz metodę transportu.

    1. Wybierz kolejno opcje **Podatek** > **Ustawienia** > **Handel zagraniczny** > **Metoda transportu**.
    2. W okienku akcji wybierz opcję **Nowy**.
    3. W polu **Transport** wprowadź nazwę **3**.
    4. W polu **Opis** wprowadź **Transport drogowy**.

2. Przypisz nową metodę transportu do sposobu dostawy. W ten sposób można ustawić wartości domyślne, które są używane dla metody transportu po wybraniu odpowiedniej metody dostawy.

    1. Przejdź do **Zaopatrzenie i sourcing** > **Ustawienia** > **Dystrybucja** > **Metody dostawy**.
    2. W siatce zaznacz element **10**.
    3. Na skróconej karcie **Handel zagraniczny** w polu **Transport** wybierz wartość **3**.

3. Umożliwia wybór domyślnej trybu dostawy dla odbiorcy

    1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** > **Odbiorcy** > **Wszyscy odbiorcy**.
    2. W siatce zaznacz element **DE-016**.
    3. Na skróconej karcie **Faktura i dostawa** w polu **Tryb dostawy** wybierz pozycję **10**.

4. Umożliwia wybór domyślnej trybu dostawy dla dostawcy.

    1. Wybierz kolejno opcje **Rozrachunki z dostawcami** > **Dostawcy** > **Wszyscy dostawy**.
    2. W siatce zaznacz element **DE-001**.
    3. Na skróconej karcie **Faktura i dostawa** w polu **Tryb dostawy** wybierz pozycję **10**.

### <a name="set-up-codes-for-terms-of-delivery"></a>Skonfiguruj kody dla warunków dostawy

1. Skonfiguruj kod Intrastat dla warunków dostawy.

    1. Przejdź do **Zaopatrzenie i sourcing** > **Ustawienia** > **Dystrybucja** > **Warunki dostarczenia**.
    2. W siatce zaznacz element **CIF**.
    3. Na skróconej karcie **Ogólne** w polu **Kod Intrastat** wpisz wartość **CIF**.

2. Wybierz domyślne warunki dostawy dla klienta.

    1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** > **Odbiorcy** > **Wszyscy odbiorcy**.
    2. W siatce zaznacz element **DE-016**.
    3. Na skróconej karcie **Faktura i dostawa** w polu **Warunki dostawy** wybierz pozycję **CIF**.

3. Wybierz domyślne warunki dostawy dla dostawcy.

    1. Wybierz kolejno opcje **Rozrachunki z dostawcami** > **Dostawcy** > **Wszyscy dostawy**.
    2. W siatce zaznacz element **DE-001**.
    3. Na skróconej karcie **Faktura i dostawa** w polu **Warunki dostawy** wybierz pozycję **CIF**.

### <a name="verify-an-eu-customers-tax-exempt-number-code"></a>Zweryfikuj kod numeru zwolnienia podatkowego klienta z UE

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** > **Odbiorcy** > **Wszyscy odbiorcy**.
2. W siatce zaznacz element **DE-016**.
3. Na **Faktura i dostawa** skrócona karta, w sekcji **Podatek od sprzedaży** , w polu **Numer zwolnienia z podatku** jest ustawiona wartość **DE9012**.

### <a name="create-a-sales-order-with-an-eu-customer"></a>Tworzenie zamówienia sprzedaży z odbiorcą z UE

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** > **Zamówienia** > **Wszystkie zamówienia sprzedaży**.
2. W okienku akcji wybierz opcję **Nowy**.
3. W oknie dialogowym **Utwórz zamówienie sprzedaży**, na skróconej karcie **Klient**, w sekcji **Klient**, w polu **Konto klienta** wybierz **DE-016**.
4. Na **skróconej karcie Ogólne** w sekcji **Wymiary magazynu** w polu **Lokacja** wybierz pozycję **1**.
5. W polu **Magazyn** wybierz wartość **11**.
6. Na karcie **Adres** sprawdź, czy w polu **Adres** jest ustawiona wartość **Teichgasse 12, Kiel, 24103, DEU**, ponieważ odbiorca pochodzi z Niemiec.
7. Kliknij przycisk **OK**.
8. Na karcie **Nagłówek**, na skróconej karcie **Dostawa** sprawdź, czy w polu **Warunki dostawy** jest ustawiona wartość **CIF**, a w polu **Tryb dostawy** jest ustawiona wartość **10**.
9. Na karcie **Wiersze**, na skróconej karcie **Wiersze zamówienia sprzedaży** w polu **Numer pozycji** wybierz wartość **D0001**. W polu **Ilość** wpisz wartość **8**.
10. Na skróconej karcie **Szczegóły wiersza**, na karcie **Handel zagraniczny** sprawdź, czy pole **Kod transakcji** ma wartość **11**, w polu **Asortyment** jest ustawiona wartość **100 200 30**, a w polu **Kraj/region pochodzenia** jest ustawiona wartość **POL**.
11. Na okienku akcji wybierz opcję **Zapisz**.
12. W okienku akcji na karcie **Faktura** w grupie **Generuj** wybierz **Faktura**.
13. W **oknie dialogowym Księgowanie faktury**, na skróconej karcie **Parametry** w sekcji **Parametr** w polu **Ilość** zaznacz opcję **Wszystko**.
14. Na skróconej karcie **Konfiguracja** w polu **Data sprzedaży** wybierz datę **18/10/2021** (18 października 2021).
15. Wybierz **OK**, aby zaksięgować fakturę.

### <a name="transfer-the-transaction-to-the-intrastat-journal-and-review-the-result"></a>Przenieś transakcję do arkusza Intrastat i przejrzyj wynik.

1. Wybierz kolejno opcje **Podatek** > **Deklaracje** > **Handel zagraniczny** > **Intrastat**.
2. W okienku akcji wybierz pozycję **Transfer**.
3. W oknie dialogowym **Intrastat (Przeniesienie)** w sekcji **Parametry** ustaw opcję **Faktura dla odbiorcy** na **wartość Tak**.
4. Wybierz **Filtry**.
5. W oknie dialogowym **Filtr Intrastat** na karcie **Zakres** wybierz pierwszy wiersz i upewnij się, że pole **Pole** jest ustawione na **Data**.
6. W polu **Kryteria** wybierz bieżącą datę.
7. Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Filtr Intrastat**.
8. Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Filtr Intrastat** i sprawdzić wynik. W wierszu pokazane jest pierwsze utworzone wcześniej zamówienie sprzedaży.

    ![W wierszu pokazane jest utworzone wcześniej na stronie Intrastat zamówienie sprzedaży](media/intrastat_pl_1.png)

9. Wybierz wiersz transakcji, a następnie wybierz kartę **Ogólne**, aby wyświetlić więcej szczegółów.

    ![Szczegóły zamówienia sprzedaży na karcie Ogólne na stronie Intrastat](media/intrastat_pl_2.png)

10. W okienku akcji wybierz pozycję **Dane wyjściowe** > **Raport**.
11. W oknie dialogowym **Raport Intrastat**, na skróconej karcie **Parametry**, w sekcji **Data** w polu **Od daty** wybierz pierwszy dzień bieżącego miesiąc.
12. W sekcji **Opcje** **eksportu** ustaw wartość **Tak** dla opcji **Generuj plik**. Następnie w polu **Nazwa pliku** wprowadź wymaganą nazwę.
13. W polu **Generuj raport** wybierz opcję **Tak**. Następnie w polu **Nazwa pliku raportu** wprowadź wymaganą nazwę.
14. W polu **Kierunek** wybierz opcję **Wysyłki**.
15. W sekcji **Mapowanie formatu** pliku sprawdź, czy w polu **Typ deklaracji** jest ustawiona wartość **Deklaracja**.
16. W **polu Miasto utworzenia dokumentu** wprowadź wartość **Kraków**.
17. W polu **Data utworzenia dokumentu** wybierz **19/10/2021** (19 października 2021).
18. W polu **Numer dokumentu** wpisz **11**.
19. W polu **Wersja dokumentu** wpisz **22**.
20. Naciśnij przycisk **OK** i przejrzyj wygenerowany raport w formacie XML. W poniższej tabeli przedstawiono wartości w przykładowym raporcie.

    <table>
    <tbody>
    <tr>
    <td>
    <p><strong>Nazwa pola</strong></p>
    </td>
    <td>
    <p><strong>Opis pola</strong></p>
    </td>
    <td>
    <p><strong>Wartość</strong></p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>Informacje o dokumencie</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Deklaracja Data</p>
    </td>
    <td>
    <p>Data utworzenia dokumentu.</p>
    </td>
    <td>
    <p>2021-19-10</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Miejscowosc</p>
    </td>
    <td>
    <p>Miasto, w którym powstał dokument.</p>
    </td>
    <td>
    <p>Kraków</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaLiczbaPozycji</p>
    </td>
    <td>
    <p>Całkowita liczba przedmiotów.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscStatystyczna</p>
    </td>
    <td>
    <p>Całkowita wartość statystyczna.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscFaktur</p>
    </td>
    <td>
    <p>Całkowita wartość faktury.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UC</p>
    </td>
    <td>
    <p>Kod jednostki.</p>
    </td>
    <td>
    <p>420000</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Rodzaj</p>
    </td>
    <td>
    <p>Rodzaj deklaracji.</p>
    </td>
    <td>
    <p>D</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Wersja</p>
    </td>
    <td>
    <p>Wersja dokumentu.</p>
    </td>
    <td>
    <p>22</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Numer</p>
    </td>
    <td>
    <p>Numer dokumentu.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miesiac</p>
    </td>
    <td width="330">
    <p>Miesiąc referencyjny.</p>
    </td>
    <td>
    <p>10</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Rok</p>
    </td>
    <td width="330">
    <p>Rok odwołania.</p>
    </td>
    <td>
    <p>2021</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Typ</p>
    </td>
    <td width="330">
    <p>Kierunek raportu.</p>
    </td>
    <td>
    <p>Ś</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>NrWlasny</p>
    </td>
    <td width="330">
    <p>Identyfikator deklaracji.</p>
    </td>
    <td>
    <p>21ISTDEMF-0001</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>Informacje o firmie</strong></p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miejscowosc</p>
    </td>
    <td width="330">
    <p>Miasto, w którym znajduje się siedziba firmy.</p>
    </td>
    <td>
    <p>Warszawa</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Regon</p>
    </td>
    <td width="330">
    <p>Kod firmy Regon.</p>
    </td>
    <td>
    <p>12345678901234</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nip</p>
    </td>
    <td>
    <p>Kod firmy NIP.</p>
    </td>
    <td>
    <p>1234567890</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodPocztowy</p>
    </td>
    <td>
    <p>Kod pocztowy firmy.</p>
    </td>
    <td>
    <p>31-111</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UlicaNumer</p>
    </td>
    <td>
    <p>Ulica, na której znajduje się firma.</p>
    </td>
    <td>
    <p>Statystyczna 22/1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nazwa</p>
    </td>
    <td>
    <p>Nazwa firmy.</p>
    </td>
    <td>
    <p>Contoso Entertainment System Niemcy</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>Informacje o towarze</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscStatystyczna</p>
    </td>
    <td>
    <p>Wartość statystyczna.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscFaktury</p>
    </td>
    <td>
    <p>Wartość faktury.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>MasaNetto</p>
    </td>
    <td>
    <p>Masa netto.</p>
    </td>
    <td>
    <p>16</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>IdKontrahenta</p>
    </td>
    <td>
    <p>Numer VAT klienta.</p>
    </td>
    <td>
    <p>DE9012</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodTowarowy</p>
    </td>
    <td>
    <p>Kod asortymentu.</p>
    </td>
    <td>
    <p>10020030</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>RodzajTransakcji</p>
    </td>
    <td>
    <p>Kod transakcji.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WarunkiDostawy</p>
    </td>
    <td>
    <p>Warunki dostawy.</p>
    </td>
    <td>
    <p>CIF</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KrajPochodzeniaWysylki</p>
    </td>
    <td>
    <p>Kod kraju lub regionu wysyłki/przeznaczenia.</p>
    </td>
    <td>
    <p>DE</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>OpisTowaru</p>
    </td>
    <td>
    <p>Opis towarów.</p>
    </td>
    <td>
    <p>Sprzęt</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>PozId</p>
    </td>
    <td>
    <p>Kod towaru.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>Informacje o kontakcie</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Wiadomość e-mail</p>
    </td>
    <td>
    <p>Adres e-mail zgłaszającego.</p>
    </td>
    <td>
    <p>manishc@contoso.com</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Faks</p>
    </td>
    <td>
    <p>Numer faksu zgłaszającego.</p>
    </td>
    <td>
    <p>425-555-5049</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Telefon</p>
    </td>
    <td>
    <p>Numer telefonu zgłaszającego.</p>
    </td>
    <td>
    <p>425-555-5068</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>NazwiskoImie</p>
    </td>
    <td>
    <p>Imię i nazwisko zgłaszającego.</p>
    </td>
    <td>
    <p>Manish Chopra</p>
    </td>
    </tr>
    </tbody>
    </table>

21. Przejrzyj wygenerowany raport w formacie Excel.

    ![Raport Intrastat dotyczący wysyłek](media/intrastat_pl_3.png)

### <a name="create-a-purchase-order"></a>Tworzenie zamówienia zakupu

1. Wybierz kolejno opcje **Rozrachunki z dostawcami** > **Zamówienia zakupu** > **Wszystkie zamówienia zakupu**.
2. W okienku akcji wybierz opcję **Nowy**.
3. W oknie dialogowym **Tworzenie zamówienia zakupu** w polu **Konto dostawcy** wybierz pozycję **DE-001**.
4. W polu **Oddział** wybierz wartość **1**.
5. W polu **Magazyn** wybierz wartość **11**.
6. Kliknij przycisk **OK**.
7. Na karcie **Nagłówek**, na skróconej karcie **Dostawa** sprawdź, czy w polu **Tryb dostawy** jest ustawiona wartość **10**, a w polu **Warunki dostawy** jest ustawiona wartość **10**.
8. Na karcie **Wiersze**, na skróconej karcie **Wiersze zamówienia zakupu** w polu **Numer pozycji** wybierz wartość **D0003**. W polu **Ilość** wpisz wartość **6**.
9. Na skróconej karcie **Szczegóły wiersza**, na karcie **Handel zagraniczny** sprawdź, czy pole **Kod transakcji** ma wartość **11**, w polu **Transport** jest ustawiona wartość **3**, a w polu **Asortyment** jest wartość **100 200 30**, a w polu **Kraj/region pochodzenia** jest ustawiona wartość **DEU**.
10. W okienku akcji na karcie **Zakup** w grupie **Akcje** wybierz opcję **Potwierdź**.
11. W okienku akcji na karcie **Faktura** w grupie **Generuj** wybierz **Faktura**.
12. W okienku akcji wybierz **Domyślna z**, a następnie w polu **Domyślna ilość dla wierszy** wybierz **Zamówiona ilość**. Następnie wybierz opcję **OK**.
13. Na skróconej karcie **Nagłówek faktury od dostawcy**, w sekcji **Identyfikacja faktury**, w polu **Numer** wprowadź wartość **00010**.
14. W sekcji **Daty faktury**, w polu **Data faktury** wprowadź obecną datę. Ta data będzie używana na przeniesienia Intrastat.
15. W polu **Data otrzymania dokumentu** wybierz **18/10/2021** (18 października 2021).
16. W okienku akcji naciśnij przycisk **Zaksięguj**, aby zaksięgować fakturę

### <a name="create-an-intrastat-declaration-for-arrivals"></a>Tworzenie deklaracji Intrastat dla przyjęć

1. Wybierz kolejno opcje **Podatek** > **Deklaracje** > **Handel zagraniczny** > **Intrastat**.
2. W okienku akcji wybierz pozycję **Transfer**.
3. W oknie dialogowym **Intrastat (Przeniesienie)** ustaw opcję **Faktura od dostawcy** na wartość **Tak**.
4. Kliknij **OK**, aby przenieść transakcje, a następnie przejrzyj arkusz Intrastat.

    ![W wierszu pokazane jest utworzone wcześniej na stronie Intrastat zamówienie zakupu](media/intrastat_pl_4.png)

5. Przejrzyj informacje na karcie **Ogólne** dotyczące zamówienia zakupu.

    ![Szczegóły zamówienia zakupu na karcie Ogólne na stronie Intrastat](media/intrastat_pl_5.png)

6. W okienku akcji wybierz pozycję **Dane wyjściowe** > **Raport**.
7. W oknie dialogowym **Raport Intrastat**, na skróconej karcie **Parametry**, w sekcji **Data** w polu **Od daty** wybierz pierwszy dzień bieżącego miesiąc.
8. W sekcji **Opcje** **eksportu** ustaw wartość **Tak** dla opcji **Generuj plik**. Następnie w polu **Nazwa pliku** wprowadź wymaganą nazwę.
9. W polu **Generuj raport** wybierz opcję **Tak**. Następnie w polu **Nazwa pliku raportu** wprowadź wymaganą nazwę.
10. W polu **Kierunek** wybierz opcję **Przyjęcia**.
11. W sekcji **Mapowanie formatu** pliku sprawdź, czy w polu **Typ deklaracji** jest ustawiona wartość **Deklaracja**.
12. W **polu Miasto utworzenia dokumentu** wprowadź wartość **Kraków**.
13. W polu **Data utworzenia dokumentu** wybierz **19/10/2021** (19 października 2021).
14. W polu **Numer dokumentu** wpisz **11**.
15. W polu **Wersja dokumentu** wpisz **22**.
16. Naciśnij przycisk **OK** i przejrzyj wygenerowany raport w formacie XML. W poniższej tabeli przedstawiono wartości w przykładowym raporcie.

    <table>
    <tbody>
    <tr>
    <td>
    <p><strong>Nazwa pola</strong></p>
    </td>
    <td>
    <p><strong>Opis pola</strong></p>
    </td>
    <td>
    <p><strong>Wartość</strong></p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p style="text-align: center;"><strong>Informacje o dokumencie</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Deklaracja Data</p>
    </td>
    <td>
    <p>Data utworzenia dokumentu.</p>
    </td>
    <td>
    <p>2021-19-10</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Miejscowosc</p>
    </td>
    <td>
    <p>Miasto, w którym powstał dokument.</p>
    </td>
    <td>
    <p>Kraków</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaLiczbaPozycji</p>
    </td>
    <td>
    <p>Całkowita liczba przedmiotów.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscStatystyczna</p>
    </td>
    <td>
    <p>Całkowita wartość statystyczna.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscFaktur</p>
    </td>
    <td>
    <p>Całkowita wartość faktury.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UC</p>
    </td>
    <td>
    <p>Kod jednostki.</p>
    </td>
    <td>
    <p>420000</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Rodzaj</p>
    </td>
    <td>
    <p>Rodzaj deklaracji.</p>
    </td>
    <td>
    <p>D</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Wersja</p>
    </td>
    <td>
    <p>Wersja dokumentu.</p>
    </td>
    <td>
    <p>22</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Numer</p>
    </td>
    <td>
    <p>Numer dokumentu.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miesiac</p>
    </td>
    <td width="332">
    <p>Miesiąc referencyjny.</p>
    </td>
    <td>
    <p>10</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Rok</p>
    </td>
    <td width="332">
    <p>Rok odwołania.</p>
    </td>
    <td>
    <p>2021</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Typ</p>
    </td>
    <td width="332">
    <p>Kierunek raportu.</p>
    </td>
    <td>
    <p>P</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>NrWlasny</p>
    </td>
    <td width="332">
    <p>Identyfikator deklaracji.</p>
    </td>
    <td>
    <p>21ISTDEMF-0002</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p style="text-align: center;"><strong>Informacje o firmie</strong></p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miejscowosc</p>
    </td>
    <td width="332">
    <p>Miasto, w którym znajduje się siedziba firmy.</p>
    </td>
    <td>
    <p>Warszawa</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Regon</p>
    </td>
    <td width="332">
    <p>Kod firmy Regon.</p>
    </td>
    <td>
    <p>12345678901234</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nip</p>
    </td>
    <td>
    <p>Kod firmy NIP.</p>
    </td>
    <td>
    <p>1234567890</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodPocztowy</p>
    </td>
    <td>
    <p>Kod pocztowy firmy.</p>
    </td>
    <td>
    <p>31-111</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UlicaNumer</p>
    </td>
    <td>
    <p>Ulica, na której znajduje się firma.</p>
    </td>
    <td>
    <p>Statystyczna 22/1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nazwa</p>
    </td>
    <td>
    <p>Nazwa firmy.</p>
    </td>
    <td>
    <p>Contoso Entertainment System Niemcy</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p style="text-align: center;"><strong>Informacje o towarze</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscStatystyczna</p>
    </td>
    <td>
    <p>Wartość statystyczna.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscFaktury</p>
    </td>
    <td>
    <p>Wartość faktury.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>MasaNetto</p>
    </td>
    <td>
    <p>Masa netto.</p>
    </td>
    <td>
    <p>30</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KrajPochodzenia</p>
    </td>
    <td>
    <p>Kod kraju lub regionu pochodzenia.</p>
    </td>
    <td>
    <p>DE</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>RodzajTransportu</p>
    </td>
    <td>
    <p>Kod środka transportu.</p>
    </td>
    <td>
    <p>3</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodTowarowy</p>
    </td>
    <td>
    <p>Kod asortymentu.</p>
    </td>
    <td>
    <p>10020030</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>RodzajTransakcji</p>
    </td>
    <td>
    <p>Kod transakcji.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WarunkiDostawy</p>
    </td>
    <td>
    <p>Warunki dostawy.</p>
    </td>
    <td>
    <p>CIF</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KrajPochodzeniaWysylki</p>
    </td>
    <td>
    <p>Kod kraju lub regionu wysyłki/przeznaczenia.</p>
    </td>
    <td>
    <p>DE</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>OpisTowaru</p>
    </td>
    <td>
    <p>Opis towarów.</p>
    </td>
    <td>
    <p>Sprzęt</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>PozId</p>
    </td>
    <td>
    <p>Kod towaru.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p style="text-align: center;"><strong>Informacje o kontakcie</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Wiadomość e-mail</p>
    </td>
    <td>
    <p>Adres e-mail zgłaszającego.</p>
    </td>
    <td>
    <p>manishc@contoso.com</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Faks</p>
    </td>
    <td>
    <p>Numer faksu zgłaszającego.</p>
    </td>
    <td>
    <p>425-555-5049</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Telefon</p>
    </td>
    <td>
    <p>Numer telefonu zgłaszającego.</p>
    </td>
    <td>
    <p>425-555-5068</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>NazwiskoImie</p>
    </td>
    <td>
    <p>Imię i nazwisko zgłaszającego.</p>
    </td>
    <td>
    <p>Manish Chopra</p>
    </td>
    </tr>
    </tbody>
    </table>

17. Przejrzyj wygenerowany raport w formacie Excel.

    ![Raport przyjęć Intrastat](media/intrastat_pl_6.png)
