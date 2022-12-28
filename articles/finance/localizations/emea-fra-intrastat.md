---
title: Intrastat — Francja
description: Ten artykuł zawiera informacje dotyczące deklaracji Intrastat we Francji.
author: anasyash
ms.date: 11/30/2022
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: ''
ms.openlocfilehash: 2076649c7fff9f47b9c1fda62a103168b19bb973
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831813"
---
# <a name="french-intrastat"></a>Intrastat — Francja

[!include[banner](../includes/banner.md)]

Firmy we Francji zarejestrowane jako podatnik VAT (VAT) i prowadzące handel z innymi krajami Unii Europejskiej (UE) muszą zadeklarować wymianę towarów i usług do i z Francji. Deklaracja d'exchange de biens (Deklaracja handlu towarami lub DEB) to kombinacja listy sprzedaży do UE i raportu Intrastat. Raport ten należy składać co miesiąc dla wszystkich wewnątrzwspólnotowych sprzedaży towarów.

Raport DEB można wygenerować w jednym z dwóch elektronicznych formatów plików tekstowych: SAISUNIC 330 lub INTRACOM.

W poniższej tabeli przedstawiono pola zawarte we francuskiej deklaracji Intrastat w formacie SAISUNIC 330. W tabeli są również wskazywane poziomy raportu tego pola. Pole może mieć następujące poziomy raportów:

- **4** – Deklaracja podatkowa.
- **1** – Statystyczna odpowiedź.
- **5** – Statystyczna odpowiedź na wysyłkę i deklarację podatkową i wypełnianie wspólne.

| Pole                       | Poziomy raportu |
|-----------------------------|---------------|
| Okres odwołania         | 4, 1, 5       |
| Numer deklaracji       | 4, 1, 5       |
| Numer wiersza                 | 4, 1, 5       |
| Kod ISO kraju (FR)       | 4, 1, 5       |
| Kod uzupełniający          | 4, 1, 5       |
| Numer siren                | 4, 1, 5       |
| Kod VAT odbiorcy        | 4, 1, 5       |
| Kod kierunku              | 4, 1, 5       |
| Typ transakcji            | 4, 1, 5       |
| Poziom zobowiązania            | 4, 1, 5       |
| Kod asortymentu              | 1, 5          |
| Krajowy NGP                | 1, 5          |
| Powiat (Dział)         | 1, 5          |
| Charakter transakcji       | 1, 5          |
| Kraj pochodzenia      | 1, 5          |
| Kraj pochodzenia – import | 1, 5          |
| Ostateczne miejsce przeznaczenia - eksport | 1, 5          |
| Wartość faktury               | 4, 1, 5       |
| Wartość statystyczna           | 1, 5          |
| Waga netto                  | 1, 5          |
| Jednostki dodatkowe            | 1, 5          |
| Kod transportu              | 1, 5          |

W poniższej tabeli przedstawiono pola zawarte we francuskiej deklaracji Intrastat w formacie INTRACOM. W tabeli są również wskazywane poziomy raportu tego pola. Pole może mieć następujące poziomy raportów:

- **4** – Deklaracja podatkowa.
- **1** – Statystyczna odpowiedź.
- **5** – Statystyczna odpowiedź na wysyłkę i deklarację podatkową i wypełnianie wspólne.

| Pole                       | Poziomy raportu |
|-----------------------------|---------------|
| Kod kierunku              | 4, 1, 5       |
| Numer deklaracji       | 4, 1, 5       |
| Liczba wierszy              | 4, 1, 5       |
| Syreny                       | 4, 1, 5       |
| Powiat (Dział)         | 1, 5          |
| Kod transportu              | 1, 5          |
| Kraj pochodzenia           | 1, 5          |
| Charakter transakcji       | 1, 5          |
| Wartość faktury               | 4, 1, 5       |
| Metody dostawy           | 1, 5          |
| Typ transakcji            | 4, 1, 5       |
| Poziom zobowiązania            | 4, 1, 5       |
| Kod asortymentu              | 1, 5          |
| Krajowy NGP                | 1, 5          |
| Waga netto                  | 1, 5          |
| Wartość statystyczna           | 1, 5          |
| Jednostki dodatkowe            | 1, 5          |
| Kraj pochodzenia – import | 1, 5          |
| Ostateczne miejsce przeznaczenia - eksport | 1, 5          |
| Kod VAT odbiorcy        | 4, 1, 5       |
| Kod uzupełniający          | 4, 1, 5       |
| Okres odwołania         | 4, 1, 5       |

## <a name="set-up-intrastat"></a>Konfiguracja Intrastat

- W [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/Logon/Index) w bibliotece zasobów udostępnionych pobierz najnowsze wersje następujących konfiguracji raportowania elektronicznego (ER) dla deklaracji Intrastat:

    - Model Intrastat
    - Raport Intrastat
    - Intrastat INTRACOM (Francja)
    - Intrastat SAISUNIC (Francja)

    Aby uzyskać więcej informacji, zobacz [Pobieranie konfiguracji modułu Raportowanie elektroniczne z usługi Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

### <a name="set-up-vat-ids"></a>Konfigurowanie identyfikatorów VAT

#### <a name="set-up-vat-codes-for-your-company"></a>Konfigurowanie kodów VAT dla swojej firmy

1. Wybierz kolejno opcje **Podatek** \> **Ustawienia** \> **Podatek** \> **Numery zwolnione z podatku**.
2. W okienku akcji wybierz opcję **Nowy**.
3. W polu **kraj/region** wybierz **FRA**.
4. W polu **Numer zwolniony z podatku** wprowadź klucz do numeru VAT swojej firmy.
5. Przejdź do **Administrowanie organizacją** \> **Organizacje** \> **Firmy** i wybierz swoją firmę.
6. Na skróconej karcie **Handel zagraniczny i logistyka**, w sekcji **Intrastat** ustaw pola **numeru identyfikacji podatkowej VAT** i **Import numerów zwolnionych z VAT** z kodem utworzonym w kroku 4.
7. Na skróconej karcie **Rejestracja podatkowa** w polu **Numer identyfikacji podatkowej** wpisz numer identyfikacji podatkowej swojej firmy.

#### <a name="set-up-the-vat-ids-for-trading-partners"></a>Ustawienie identyfikatorów VAT dla partnerów handlowych

##### <a name="create-a-registration-type-for-the-company-code"></a>Utworzenie typu rejestracji dla kodu firmy

Musisz stworzyć typy rejestracji VAT dla wszystkich krajów lub regionów, z którymi Twoja firma prowadzi interesy.

1. Wybierz kolejno pozycje **Administrowanie organizacją** \> **Globalna książka adresowa** \> **Typy rejestracji** \> **Typy rejestracji**.
2. W okienku akcji wybierz opcję **Nowy**, aby utworzyć typ rejestracji dla identyfikatora VAT.
3. W nowym oknie dialogowym **Podaj szczegóły typu rejestracji**, w polu **Nazwa** wprowadź nazwę nowego typu rejestracji. Na przykład wpisz **VAT ID**.
4. W polu **Kraj/region** wybierz kraj lub region partnera handlowego.
5. Wybierz opcję **Utwórz**.

##### <a name="match-the-registration-type-with-a-registration-category"></a>Dopasuj typ rejestracji do kategorii rejestracji

1. Wybierz kolejno pozycje **Administrowanie organizacją** \> **Globalna książka adresowa** \> **Typy rejestracji** \> **Kategorie rejestracji**.
2. W okienku akcji wybierz opcję **Nowy**, aby utworzyć łącze między każdym utworzonym typem rejestracji a kategorią rejestracji.
3. Dla typu rejestracji dla identyfikatora VAT wybierz kategorię rejestracji **identyfikatorów VAT**.
4. Powtórz kroki 2 i 3 dla pozostałych typów rejestracji, które utworzyłeś dla krajów lub regionów, z którymi Twoja firma prowadzi interesy.

##### <a name="set-up-the-vat-number-of-a-trading-partner"></a>Ustawienie numeru VAT partnera handlowego

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Odbiorcy** \> **Wszyscy odbiorcy**.
2. W siatce wybierz klienta.
3. W okienku akcji na karcie **Klient** w grupie **Rejestracja** wybierz pozycję **Identyfikatory rejestracji**.
4. Na zakładce **Identyfikator rejestracji** wybierz **Dodaj**, aby utworzyć identyfikator rejestracji.
5. W polu **Typ rejestracji** wybierz typ rejestracji, który utworzyłeś dla kodu firmy.
6. W polu **Numer rejestracji** wpisz numer podatku VAT firmy.
7. W okienku akcji wybierz **Zapisz** i zamknij stronę.

Aby uzyskać więcej informacji, zobacz [Identyfikatory rejestracji](emea-registration-ids.md).

### <a name="set-up-foreign-trade-parameters"></a>Konfigurowanie parametrów handlu zagranicznego

1. Wybierz kolejno opcje **Podatek** \> **Ustawienia** \> **Handel zagraniczny** \> **Parametry handlu zagranicznego**.
2. Na karcie **Intrastat**, w skróconej karcie **Raportowanie elektroniczne** w polu **Mapowanie formatu pliku** wybierz **Intrastat INTRACOM (FR)** lub **Intrastat SAISUNIC (FR)**.
3. W polu **Mapowanie formatu raportów** wybierz wartość **Raport Intrastat**.
4. Na skróconej karcie **hierarchii kodów asortymentu** w polu **Hierarchia kategorii** wybierz pozycję **Intrastat**.
5. Na skróconej karcie **Ogólne** w polu **Kod transakcji** wybierz kod używany do przeniesienia towarów.
6. W polu **Nota kredytowa** wybierz kod używany do zwrotów towarów.
7. W polu **Pracownik** wybierz imię osoby kontaktowej.
8. Na karcie **Kontakt** dodaj informacje o osobie kontaktowej:

    - W polu **Telefon** wprowadź numer telefonu osoby kontaktowej.
    - W polu **Faks** wprowadź numer faksu osoby kontaktowej.

9. Na karcie **Właściwości kraju/regionu**, w polu **Kraj/region**, podaj listę wszystkich krajów lub regionów, w których organizacja prowadzi interesy. Dla każdego kraju należącego do UE wybierz pozycję **Typ UE** w polu **Typ kraju/regionu**, aby kraj były wyświetlany w raporcie Intrastat. Dla Francji wybierz opcję **Krajowy** w polu **Typ kraju/regionu**.

### <a name="set-up-compression-of-intrastat"></a>Ustawianie kompresji Intrastat

- Przejdź do **Podatek** \> **Ustawienia** \> **Handel zagraniczny** \> **Kompresja Intrastat** i wybierz pola, które należy porównać, gdy informacje Intrastat podsumowano. Dla francuskiego Intrastat określ wartości w następujących obowiązkowych polach:
 
    - Procedura statystyk
    - Kraj/region pochodzenia
    - Transport
    - Korekta
    - Kraj/region
    - Powiat pochodzenia/docelowy
    - Kierunek
    - Kraj/region nadawcy
    - Kod transakcji
    - Asortyment

### <a name="set-up-product-parameters-for-the-intrastat-declaration"></a>Konfigurowanie parametrów produktu na potrzeby deklaracji Intrastat

1. Przejdź do **Zarządzanie informacjami o produktach** \> **Produkty** \> **Zwolnione produkty**.
2. Wybierz produkt w siatce.
3. Na skróconej karcie **Handel zagraniczny**, w sekcji **Intrastat**, w polu **Asortyment** wybierz odpowiedni kod asortymentu. Nazwa asortymentu zostanie wydrukowana w polu **Opis towarów** w raporcie Intrastat.
4. W sekcji **Źródło** w polu **Kraj/region** wybierz kraj lub region pochodzenia produktu.
5. Na skróconej karcie **Zarządzanie zapasami** w polu **Waga netto** wprowadź masę produktu w kilogramach.

### <a name="ngp-codes"></a>Kody NGP

W raporcie DEB kodowanie produktów składa się z następujących elementów:

- Ośmiu cyfrowy kod CN8, który reprezentuje nazewnictwo taryf i statystyk UE.
- Jeśli ma zastosowanie, jednocyfrowy kod towaru Nazewnictwo Générale des Pénérale des Pénérale (NGP).

W roku 2022, NGP dotyczy tylko trzech typów produktów:

- Niektóre produkty z krów, owiec i kóz
- Sprzęt wojskowy
- Wina francuskie

Musisz skonfigurować kody NGP i przypisać je do powiązanych produktów. Pole **NGP** zostanie automatycznie ustawione na stronie **arkusza Intrastat**.

#### <a name="set-up-an-ngp-code"></a>Konfigurowanie kodu NGP

1. Wybierz kolejno opcje **Podatek** \> **Ustawienia** \> **Handel zagraniczny** \> **Kody NGP**.
2. W okienku akcji wybierz opcję **Nowy**.
3. W **polu NGP** wprowadź kod jednocyfrowy.
4. W polu **Opis** wprowadź opis kodu.

#### <a name="assign-an-ngp-code-to-a-product"></a>Przypisz kod NGP do produktu

1. Przejdź do **Zarządzanie informacjami o produktach** \> **Produkty** \> **Zwolnione produkty**.
2. Wybierz produkt w siatce.
3. Na skróconej karcie **Handel zagraniczny**, w sekcji **Intrastat**, w polu **NGP** wybierz odpowiedni kod NGP.

### <a name="set-up-warehouse-parameters-for-the-intrastat-declaration"></a>Konfigurowanie parametrów magazynu na potrzeby deklaracji Intrastat

1. Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Magazyn** \> **Magazyny**.
2. Wybierz magazyn, a następnie na skróconej karcie **Adresy** wybierz pozycję **Dodaj** lub **Edytuj**.
3. W oknie dialogowym w polu **Miasto** wybierz miasto magazynu. Stan lub prowincja miasta będą używane jako hrabstwo w raporcie DEB.

### <a name="set-up-the-transport-method"></a>Ustaw sposób transportu

1. Wybierz kolejno opcje **Podatek** \> **Ustawienia** \> **Handel zagraniczny** \> **Metoda transportu**.
2. W okienku akcji wybierz opcję **Nowy**.
3. W polu **Transport** wpisz unikalny kod. Firmy we Francji używają jednocyfrowych kodów transportowych.

### <a name="intrastat-journal"></a>Arkusz Intrastat

Przejdź do **Podatek** \> **Deklaracje** \> **Zagraniczny handel** \> **Intrastat**, aby zarządzać swoimi transakcjami, które dotyczą zagranicznych handel z krajami UE. Aby uzyskać więcej informacji, zobacz [Omowienie Intrastat](emea-intrastat.md).

Kolumna **NGP** jest specyficzna dla Francji i zawiera kod NGP dla produktu. Jeśli NGP nie ma zastosowania do produktu, **jest wyświetlana wartość 0** (zero). Aby dostosować kod NGP, wybierz transakcję, a następnie, na karcie **Ogólne**, w sekcji **Kody**, w polu **NGP** wybierz wymagany kod NGP.

#### <a name="intrastat-transfer"></a>Przeniesienie do Intrastat

Na stronie **Intrastat** w okienku akcji możesz wybrać **Transfer**, aby automatycznie przesyłać informacje o handlu wewnątrzwspólnotowym z zamówień sprzedaży, faktur niezależnych, zamówień zakupu, faktur od dostawców, pokwitowań produktów od dostawców , faktury projektowe i zlecenia przeniesienia. Przekazywane będą tylko dokumenty, w których krajem lub regionem przeznaczenia jest kraj UE (w przypadku wysyłek) lub przesyłka (w przypadku przywozów).

Ponieważ raport DEB jest połączeniem listy sprzedaży do UE i raportu Intrastat, obejmuje on również transakcje *trójkątne*, w których dostawa bezpośrednia jest realizowana z jednego kraju UE (strona A) do innego kraju UE (strona C) oraz francuska osoba prawna (strona B) znajduje się w środku trójstronnej umowy.

#### <a name="generate-a-deb-intrastat-report"></a>Wygeneruj raport DEB (Intrastat)

1. Wybierz kolejno opcje **Podatek** \> **Deklaracje** \> **Handel zagraniczny** \> **Intrastat**.
2. W okienku akcji wybierz pozycję **Dane wyjściowe** \> **Raport**.
3. W oknie dialogowym **Raport Intrastat** można ustawić następujące pola.

    | Pole            | opis                                                                                                                         |
    |------------------|-------------------------------------------------------------------------------------------------------------------------------------|
    | Data rozpoczęcia        | Wybierz datę rozpoczęcia raportu.                                                                                               |
    | Data zakończenia          | Wybierz datę zakończenia raportu.                                                                                                 |
    | Generuj plik    | Ustaw tę opcję na wartość **Tak**, aby stworzyć plik .txt.                                                                                 |
    | Nazwa pliku        | Wprowadź nazwę pliku .txt dla raportu Intrastat.                                                                          |
    | Generuj raport  | Ustaw tę opcję na wartość **Tak**, aby stworzyć plik .xml.                                                                                |
    | Nazwa pliku raportu | Wpisz wymaganą nazwę.                                                                                                            |
    | Tylko korekty | Tę opcję należy wybrać **tak**, aby zgłaszać tylko poprawki. Ustaw dla niego wartość **Nie**, aby raportować zarówno normalne transakcje, jak i korekty.         |
    | Kierunek        | Wybierz **opcję Przyjęcia** do raportu o wewnątrzwspólnotowych przyjęć. Wybierz **opcję Wysyłki** do raportu o wysyłkach wewnątrzwspólnotowych. |

4. Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Raport Intrastat**.
5. W oknie dialogowym **Parametry raportu elektronicznego**, na skróconej karcie **Parametry** w polu **Poziom raportu** wybierz poziom raportu. Poziom raportu może wynosić **1 – odpowiedź statystyczna**, **4 – deklaracja podatkowa** lub **5 – odpowiedź statystyczna na przesyłkę i deklarację podatkową**.

## <a name="example"></a>Przykład

W poniższym przykładzie pokazano, jak skonfigurować francuski raport Intrastat i utworzyć raport DEB. Użyj firmy **DEMF**.

### <a name="preliminary-setup"></a>Konfiguracja wstępna

1. W [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/Logon/Index) w bibliotece zasobów udostępnionych pobierz najnowsze wersje następujących konfiguracji raportowania elektronicznego (ER) dla formatu deklaracji Intrastat:

    - Model Intrastat
    - Raport Intrastat
    - Intrastat INTRACOM (Francja)

2. Skonfiguruj hierarchię produktów w sieci sprzedaży:

    1. Wybierz kolejno opcje **Zarządzanie informacjami o produktacht** \> **Ustawienia** \> **Kategorie i atrybuty** \> **Hierarchie kategorii**.
    2. W siatce zaznacz element **Intrastat**.
    3. W okienku akcji na karcie **Hierarchia kategorii** w grupie **Obsługa** wybierz opcję **Edytuj**.
    4. W okienku akcji kliknij pozycję **Nowy węzeł kategorii**.
    5. W polu **Nazwa** wpisz **Autres Libournais**.
    6. W polu **Kod** wpisz **2204 21 42**.
    7. Na okienku akcji wybierz opcję **Zapisz**.

### <a name="set-up-vat-ids"></a>Konfigurowanie identyfikatorów VAT

#### <a name="set-up-vat-codes-for-your-company"></a>Konfigurowanie kodów VAT dla swojej firmy

1. Wybierz kolejno opcje **Podatek** \> **Ustawienia** \> **Podatek** \> **Numery zwolnione z podatku**.
2. W okienku akcji wybierz opcję **Nowy**.
3. W polu **kraj/region** wybierz **FRA**.
4. W polu **Numer identyfikacji podatkowej** wybierz opcję **MS123456**.
5. Wybierz kolejno opcje **Administrowanie organizacją** \> **Organizacja** \> **Firmy** i wybierz firmę **DEMF**.
6. Na skróconej karcie **Handel zagraniczny i logistyka**, w sekcji **Intrastat** ustaw pola **numeru identyfikacji podatkowej VAT** i **Import numerów zwolnionych z VAT** z kodem utworzonym w kroku 4.
7. Na skróconej karcie **Rejestracja VAT** na podatek w polu **Numer rejestracji podatkowej** wprowadź **123456789**.

#### <a name="set-up-the-vat-ids-for-trading-partners"></a>Ustawienie identyfikatorów VAT dla partnerów handlowych

##### <a name="create-a-registration-type-for-the-company-code"></a>Utworzenie typu rejestracji dla kodu firmy

1. Wybierz kolejno pozycje **Administrowanie organizacją** \> **Globalna książka adresowa** \> **Typy rejestracji** \> **Typy rejestracji**.
2. W okienku akcji wybierz opcję **Nowy**, aby utworzyć typ rejestracji dla identyfikatora VAT.
3. W oknie dialogowym **Wprowadź szczegóły typu rejestracji** w polu **Nazwa** wpisz **VAT ID**.
4. W polu **kraj/region** wybierz **DEU**.
5. Wybierz opcję **Utwórz**.

##### <a name="match-the-registration-type-with-a-registration-category"></a>Dopasuj typ rejestracji do kategorii rejestracji

1. Wybierz kolejno pozycje **Administrowanie organizacją** \> **Globalna książka adresowa** \> **Typy rejestracji** \> **Kategorie rejestracji**.
2. W okienku akcji wybierz opcję **Nowy**, aby utworzyć łącze między każdym utworzonym typem rejestracji a kategorią rejestracji.
3. Dla typu rejestracji **VAT ID** w kraju **DEU** wybierz kategorię rejestracji **VAT ID**.

##### <a name="set-up-the-customers-vat-registration-number"></a>Ustawienie numeru NIP klienta

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Odbiorcy** \> **Wszyscy odbiorcy**.
2. W siatce zaznacz element **DE-016**.
3. W okienku akcji na karcie **Klient** w grupie **Rejestracja** wybierz pozycję **Identyfikatory rejestracji**.
4. Na zakładce **Identyfikator rejestracji** wybierz **Dodaj**, aby utworzyć identyfikator rejestracji.
5. W polu **Typ rejestracji** wybierz **VAT ID**.
6. W polu **Numer rejestracyjny** wpisz **DE9012**.
7. W okienku akcji wybierz **Zapisz** i zamknij stronę.
8. Na **Faktura i dostawa** skrócona karta, w sekcji **Podatek od sprzedaży** , w polu **Numer zwolnienia z podatku** wybierz **DE9012**.

### <a name="set-up-foreign-trade-parameters"></a>Konfigurowanie parametrów handlu zagranicznego

1. Wybierz kolejno opcje **Podatek** \> **Ustawienia** \> **Handel zagraniczny** \> **Parametry handlu zagranicznego**.
2. Na karcie **Intrastat**, na skróconej karcie **Ogólne**, w polu **Kod transakcji** wybierz wartość **11**.
3. Na **skróconej karcie Raportowanie elektroniczne** w polu **Mapowanie formatu pliku** wybierz pozycję **Intrastat INTRACOM (FR)**.
4. W polu **Mapowanie formatu raportów** wybierz wartość **Raport Intrastat**.
5. Na skróconej karcie **hierarchii kodów asortymentu** w polu **Hierarchia kategorii** wybierz pozycję **Intrastat**.
6. W polu **Pracownik** wybierz rekord.
7. W zakładce **Kontakt**, w polu **Telefon** wprowadź numer telefonu kontaktu
8. W polu **Faks** wprowadź numer faksu osoby kontaktowej.

### <a name="create-ngp-code"></a>Utwórz kod NGP

1. Wybierz kolejno opcje **Podatek** \> **Ustawienia** \> **Handel zagraniczny** \> **Kody NGP**.
2. W okienku akcji wybierz opcję **Nowy**.
3. W polu **NGP** wprowadź **8**.
4. W polu **Nazwa opisu** wpisz **NGP 8**.
5. Na okienku akcji wybierz opcję **Zapisz**.

### <a name="set-up-product-information"></a>Konfigurowanie informacji o produktach

1. Przejdź do **Zarządzanie informacjami o produktach** \> **Produkty** \> **Zwolnione produkty**.
2. W siatce zaznacz element **D0001**.
3. Na skróconej karcie **Handel zagraniczny**, w sekcji **Intrastat**, w polu **NGP** wybierz **8**.
4. W polu **Asortyment** wybierz **2204 21 42**.
5. W sekcji **Pochodzenie** w polu **kraj/region** wybierz **FRA**.
6. Na skróconej karcie **Zarządzanie zapasami** w sekcji **Pomiary wagi** w polu **Waga netto** wprowadź **2**.
7. W okienku akcji wybierz **Zapisz** i zamknij stronę.
8. W siatce zaznacz element **D0003**.
9. Na skróconej karcie **Handel zagraniczny**, w sekcji **Intrastat**, w polu **Asortyment** wybierz **100 200 30**.
10. W sekcji **Pochodzenie** w polu **kraj/region** wybierz **DEU**.
11. Na skróconej karcie **Zarządzanie zapasami** w sekcji **Pomiary wagi** w polu **Waga netto** wprowadź **5**.
12. Na okienku akcji wybierz opcję **Zapisz**.

### <a name="set-up-regime-codes"></a>Ustawianie kodów zasad

1. Wybierz kolejno opcje **Podatek** \> **Ustawienia** \> **Handel zagraniczny** \> **Procedura statystyczna**.
2. W okienku akcji wybierz opcję **Nowy**.
3. W polu **Procedura statystyczna** wprowadź **21**.
4. W polu **Tekst 1** wprowadź **Kod zasad 21**.

### <a name="change-the-site-address"></a>Zmienianie adresu lokalizacji

1. Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Magazyn** \> **Lokalizacja**.
2. W siatce zaznacz element **1**.
3. Na skróconej karcie **Adresy** wybierz pozycję **Edytuj**.
4. W oknie dialogowym **Edycja adresu** w polu **Kraj/region** wybierz pozycję **FRA**.
5. Kliknij przycisk **OK**.
6. Przejdź do **Warehouse management** \> **Ustawienia** \> **Magazyn** \> **Magazyny**, wybierz magazyn.
7. Na skróconej karcie **Adresy** wybierz pozycję **Dodaj**.
8. W oknie dialogowym **Nowyu adres** w polu **Kraj/region** wybierz pozycję **FRA**.
9. W polu **Miasto** wybierz **Bordeaux**.
10. Kliknij przycisk **OK**, aby zamknąć okno dialogowe.

### <a name="set-up-a-transport-method"></a>Ustaw sposób transportu

1. Wybierz kolejno opcje **Podatek** \> **Ustawienia** \> **Handel zagraniczny** \> **Metoda transportu**.
2. W okienku akcji wybierz opcję **Nowy**.
3. W polu **Transport** wprowadź nazwę **3**.
4. W polu **Opis** wprowadź **Transport drogowy**.

### <a name="assign-a-transport-mode-to-a-mode-of-delivery"></a>Przypisz transport do środka dostawy

1. Przejdź do **Zaopatrzenie i sourcing** \> **Ustawienia** \> **Dystrybucja** \> **Metody dostawy**.
2. W siatce zaznacz element **50**.
3. Na skróconej karcie **Handel zagraniczny** w polu **Transport** wybierz wartość **3**.

### <a name="create-a-sales-order-with-an-eu-customer-that-includes-the-new-product"></a>Utwórz zlecenie sprzedaży z klientem z Unii Europejskiej, które obejmuje nowy produkt

1. Przejdź do pozycji **Rozrachunki z odbiorcami** \> **Zamówienia** \> **Wszystkie zamówienia sprzedaży**.
2. W okienku akcji wybierz opcję **Nowy**.
3. W oknie dialogowym **Utwórz zamówienie sprzedaży** w sekcji **Klient** w polu **Konto klienta** wybierz **DE-016**.
4. W sekcji **Adres**, w polu **Adres dostawy** wybierz znak plus (**+**), aby utworzyć adres.
5. W oknie dialogowym **Nowy adres** w polu **Nazwa opisu** wprowadź **Niemcy**.
6. W polu **kraj/region** wybierz **DEU**.
7. Kliknij przycisk **OK**.
8. W **Tworzenie zamówienia sprzedaży** wybierz **OK**.
9. W skróconej karcie **Wiersze zamówienia** sprzedaży w polu **Numer towaru** wybierz wartość **0001**.
10. Na skróconej karcie **Szczegóły wierszy**, na karcie **Handel zagraniczny**, w polu **Procedura statystyczna** wybierz wartość **21**.
11. W polu **Kraj pochodzenia/docelowy** wybierz pozycję **AL**.
12. Na okienku akcji wybierz opcję **Zapisz**.
13. W zakładce **Nagłówek**, na skróconej karcie **Dostawa**, w polu **Tryb dostarczania** upewnij się, że wybrano **50**.
14. W okienku akcji na karcie **Faktura** w grupie **Generuj** wybierz **Faktura**.
15. W **oknie dialogowym Księgowanie faktury**, na skróconej karcie **Parametry** w sekcji **Parametr** w polu **Ilość** zaznacz opcję **Wszystko**. Następnie wybierz **OK**, aby zaksięgować fakturę.

### <a name="transfer-the-transaction-to-the-intrastat-journal-and-review-the-result"></a>Przenieś transakcję do arkusza Intrastat i przejrzyj wynik.

1. Wybierz kolejno opcje **Podatek** \> **Deklaracje** \> **Handel zagraniczny** \> **Intrastat**.
2. W okienku akcji wybierz pozycję **Transfer**.
3. W oknie dialogowym **Intrastat (Przeniesienie)** w sekcji **Parametry** ustaw opcję **Faktura dla odbiorcy** na **wartość Tak**. Następnie wybierz opcję **OK**.
4. Sortuj transakcje według **pola Data**. Najwyższa transakcja to transakcja wynikowa.

    ![W wierszu pokazane jest utworzone wcześniej na stronie Intrastat zamówienie sprzedaży.](media/intrastat_fr_1.png)

5. Wybierz wiersz transakcji, a następnie wybierz kartę **Ogólne**, aby wyświetlić więcej szczegółów.

    ![Szczegóły zamówienia sprzedaży na karcie Ogólne na stronie Intrastat.](media/intrastat_fr_2.png)

6. W okienku akcji wybierz pozycję **Dane wyjściowe** \> **Raport**.
7. W oknie dialogowym **Raport Intrastat**, na skróconej karcie **Parametry**, w sekcji **Data** wybierz miesiąc utworzonego zamówienia sprzedaży.
8. W sekcji **Opcje eksportu** ustaw wartość **Tak** dla opcji **Generuj plik**.
9. W polu **Nazwa pliku** wprowadź wymaganą nazwę.
10. Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Raport Intrastat**.
11. W oknie dialogowym **Parametry raportu elektronicznego**, na skróconej karcie **Parametry**, w polu **Poziom raportu** wybierz **5 – odpowiedź statystyczna na przesyłkę i deklarację podatkową** i przejrzyj raport.

    ![Raport Intracom dotyczący wysyłek.](media/intrastat_fr_3.png)

12. Przejrzyj wygenerowany raport Excel.

    ![Raport Intrastat dotyczący wysyłek.](media/intrastat_fr_4.png)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
