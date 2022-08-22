---
title: Intrastat — Niemcy
description: Ten artykuł zawiera informacje dotyczące deklaracji Intrastat w Niemczech.
author: AdamTrukawka
ms.date: 09/09/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: ''
ms.openlocfilehash: ae978b28098d92d84415c29bbe76157144f862d8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269443"
---
# <a name="german-intrastat"></a>Intrastat — Niemcy

[!include [banner](../includes/banner.md)]

Strona **Intrastat** służy do generowania i raportowania informacji o handlu między krajami Unii Europejskiej (UE). Niemiecka deklaracja Intrastat zawiera informacje o handlu towarami do zgłoszenia. Raport jest sformatowany zgodnie z wytycznymi władz niemieckich przedstawionymi na stronie [6.2 Składanie deklaracji dotyczące formatu INSTAT/XML](https://www-idev.destatis.de/idev/doc/intra_en/hilfe6_2.html).

W poniższej tabeli przedstawiono pola, które pojawiają się w niemieckiej deklaracji Intrastat.

| Pola | Wysyłki | Przyjęcia |
|-------------------------|-------------------------|-------------------------|
| Okres odwołania | X | X |
| Kod kierunku | X | X |
| Waluta deklaracji Intrastat</br>**Uwaga:** Ta waluta nie jest <em>walutą rozliczeniową</em>. | X | X |
| Kod asortymentu | X | X |
| Nazwa towaru | X | X |
| Kod jednostki dodatkowej | X | X |
| Państwo członkowskie wysyłki/przeznaczenia | X | X |
| Masa netto | X | X |
| Ilość w jednostkach dodatkowych | X | X |
| Kraj pochodzenia |  | X |
| Kwota faktury | X |  |
| Wartość statystyczna | X | X |
| Charakter transakcji | X | X |
| Rodzaj transportu | X | X |
| Kod regionu</br>**Uwaga:**</br><ul></br><li>Jeśli kraj lub region pochodzenia to Niemcy, a faktura jest wysyłana, wyświetlany jest kod Intrastat państwa pochodzenia.</li></br><li>Jeśli krajem lub regionem pochodzenia nie są Niemcy, a faktura jest wysyłana, wyświetlany jest kod **99**.</li></br><li>Jeśli faktura jest dla przyjścia, wyświetlany jest kod Intrastat dla państwa.</li></br></ul> | X | X |
| Kod portu/portu lotniczego/portu śródlądowego | X | X |
| Warunki dostawy | X | X |


## <a name="set-up-intrastat"></a>Konfiguracja Intrastat

1. Konfigurowanie kodów firmy.

    1. Wybierz kolejno opcje **Administrowanie organizacją** > **Organizacje** > **Firmy**.
    2. Na skróconej karcie **Umowy handlu zagranicznego i logistyki** w sekcji **Identyfikacja** w polu **DVR** wprowadź identyfikator umowy dot. wymiany danych. Ten identyfikator będzie zawarty w raporcie.
    3. W polu **Numer identyfikacji VAT na eksport** wprowadź numer podatku od wartości dodanej (VAT) firmy na potrzeby eksportu.
    4. W polu **Numer identyfikacji VAT na import** wprowadź numer podatku od wartości dodanej (VAT) firmy na potrzeby importu.
    5. W polu **Kod Intrastat** wprowadź kod Intrastat przypisany do firmy.
    6. Na skróconej karcie **Rejestracja podatkowa** w polu **Numer identyfikacji podatkowej** wpisz numer identyfikacji podatkowej swojej firmy.

    > [!NOTE]
    > Jeśli generujesz raport Intrastat dla podmiotów stowarzyszonych, w polu **Numer rejestracji podatkowej** wprowadź numer identyfikacji podatkowej firmy nadrzędnej.

2. W [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) w bibliotece zasobów udostępnionych pobierz najnowsze wersje następujących konfiguracji raportowania elektronicznego (ER) dla deklaracji Intrastat.

    - Model Intrastat
    - Raport Intrastat
    - INSTAT XML
    - INSTAT XML (DE)

3. Konfigurowanie parametrów handlu zagranicznego:

    1. W Dynamics 365 Finance wybierz kolejno opcje **Podatek** > **Ustawienia** > **Parametry handlu zagranicznego**.
    2. Na karcie **Intrastat**, na skróconej karcie **Intrastat** w polu **Mapowanie formatu pliku** wybierz pozycję **Intrastat XML (DE)**.
    3. W polu **Mapowanie formatu raportów** wybierz wartość **Raport Intrastat**.
    4. Na skróconej karcie **hierarchii kodów asortymentu** w polu **Hierarchia kategorii** wybierz pozycję **Intrastat**.
    5. W polu **Kod transakcji** wybierz kod transakcji dla przeniesień właściwości. Kod ten będzie wykorzystywany do tworzenia transakcji powodujących faktyczne lub planowane przeniesienie własności za odszkodowaniem (finansowej lub innej). Można go również użyć do poprawek.
    6. W polu **Nota kredytowa** wybierz kod transakcji zwrotu towarów.
    7. W polu **Pracownik** wybierz osobę kontaktową dla raportu Intrastat. Ewentualnie na karcie **Osoba kontaktowa** wprowadź lub wybierz wartości w polach **Nazwisko**, **Telefon**, **Faks**, **Adres e-mail** i **Adres internetowy**. Te pola są uwzględniane w raporcie.
    8. W polu **Urząd** wybierz urząd Intrastat.
    9. Przejdź do **Podatki** > **Podatki pośrednie** > **Podatek od sprzedaży** > **Urząd skarbowy** i wprowadź następujące informacje dla urzędu Intrastat wybranego w poprzednim kroku:

       - Identyfikacja urzędu
       - Adres 
       - Informacje o kontakcie

    10. Na karcie **Właściwości kraju/regionu**, w polu **Kraj/region**, podaj listę wszystkich krajów lub regionów, w których organizacja prowadzi interesy. Dla każdego kraju lub regionu w polu **Typ kraju/regionu** wybierz pozycję **UE**, aby kraj lub region były wyświetlane w raporcie Intrastat.

4. Ustawianie kodów regionów.

    1. Wybierz kolejno opcje **Administrowanie organizacją** > **Globalna książka adresowa** > **Adresy** > **Utworzenie adresu**.
    2. Na karcie **Kraj/prowincja** w polu **Kraj/region** wybierz pozycję **DEU**, a następnie wybierz pozycję **Zastosuj filtr**.
    3. W siatce zaznacz element stan. Następnie w polu **Kod Intrastat** wprowadź kod Instrastat kraju.

5. Skonfiguruj adres pochodzenia produktu.

    1. Przejdź do **Zarządzanie informacjami o produktach** > **Produkty** > **Zwolnione produkty**.
    2. Wybierz produkt w siatce.
    3. Na skróconej karcie **Handel zagraniczny**, w sekcji **Intrastat**, w polu **Kraj pochodzenia** wybierz **DEU**.

6. Przejdź do **Podatek** > **Ustawienia** > **Handel zagraniczny** > **Kompresja Intrastat** i wybierz pola, które należy porównać, gdy informacje Intrastat podsumowano. Dla niemieckiego Intrastat określ wartości w następujących obowiązkowych polach:

    - Asortyment
    - Kraj/region
    - Korekta
    - Kierunek
    - Warunki dostawy
    - Faktura VAT
    - Kraj/region pochodzenia
    - Port
    - Kraj/region nadawcy
    - Województwo nadawcy
    - Procedura statystyczna
    - Kod transakcji
    - Transport
    - Numer identyfikacji podatkowej

### <a name="intrastat-transfer"></a>Przeniesienie do Intrastat

Na stronie **Intrastat** w okienku akcji możesz wybrać **Transfer**, aby automatycznie przesyłać informacje o handlu wewnątrzwspólnotowym z zamówień sprzedaży, faktur niezależnych, zamówień zakupu, faktur od dostawców **,** pokwitowań produktów od dostawców , faktury projektowe i zlecenia przeniesienia. Przekazywane będą tylko dokumenty, w których krajem lub regionem przeznaczenia jest kraj UE (w przypadku wysyłek) lub przesyłka (w przypadku przywozów).

Transakcje można również wprowadzać ręcznie, wybierając opcję **Nowe** w okienku akcji.

### <a name="generate-an-intrastat-report"></a>Wygeneruj raport Intrastat

1. Wybierz kolejno opcje **Podatek** > **Deklaracje** > **Handel zagraniczny** > **Intrastat**.
2. W okienku akcji wybierz pozycję **Dane wyjściowe** > **Raport**.
3. W oknie dialogowym **Raport Intrastat** można ustawić następujące pola.

    | Pole | opis |
    |-------------------------|-------------------------|
    | Data rozpoczęcia | Wybierz datę rozpoczęcia raportu. |
    | Data zakończenia | Wybierz datę zakończenia raportu. |
    | Generuj plik | Ustaw tę opcję na wartość **Tak**, aby stworzyć plik .xml. |
    | Nazwa pliku | To pole należy pozostawić puste. Nazwa pliku jest generowana automatycznie i składa się ze znacznika XML **&lt;envelopedID&gt;** oraz rozszerzenia nazwy pliku **.xml**.</br>Wartość **&lt;envelopeId&gt;** jest połączeniem następujących elementów, w następującej kolejności:</br><ol type="1"></br><li>Wartość znacznika **&lt;interchangeAgreementId&gt;**</li></br><li>Myślnik (-)</li></br><li>Wartość taga **&lt;referencePeriod w RRRRMM&gt;**</li></br><li>Myślnik (-)</li></br><li>Wartość taga **&lt;Koperta/DataCzas/Data w formacie RRRRMMDD&gt;**</li></br><li>Myślnik (-)</li></br><li>Wartość taga **&lt;Koperta/DataCzas/czas w formacie HHMM&gt;**</li></br></ol> |
    | Kierunek | <ul></br><li>Wybierz opcję **Przyjęcia** do raportu o wewnątrzwspólnotowych przyjęciach.</li></br><li>Wybierz opcję **Wysyłki** do raportu o wysyłkach wewnątrzwspólnotowych.</li></br><li>Wybierz opcję **Obydwa** do raportu o wysyłkach i przyjęciach.</li></br></ul> |
    | Numer rejestracji podatkowej | Wprowadź numer rejestracyjny używany do generowania kodu identyfikacyjnego nadawcy, jeśli numer różni się od numeru identyfikacji podatkowej firmy. |


## <a name="example"></a>Przykład

W tym przykładzie pokazano, jak księgować przyjęcia i wysyłki dla Intrastat. Użyj firmy **DEMF**.

1. W [LCS](https://lcs.dynamics.com/Logon/Index) w bibliotece zasobów udostępnionych pobierz najnowsze wersje następujących konfiguracji raportowania elektronicznego (ER) dla formatu deklaracji Intrastat:

    - Model Intrastat
    - Raport Intrastat
    - Intrastat XML
    - Intrastat XML (DE)

2. Tworzenie kodów transakcji.

    1. Wybierz kolejno opcje **Podatek** > **Ustawienia** > **Handel zagraniczny** > **Kody transakcji**.
    2. W okienku akcji wybierz opcję **Nowy**.
    3. W polu **Kod** **transakcji** wpisz **21**.
    4. W polu **Nazwa** wpisz **Zwrot towarów**.
    5. Na okienku akcji wybierz opcję **Zapisz**.

3. Konfigurowanie numeru identyfikacyjnego urzędu.

    1. Wybierz kolejno opcje **Podatek** > **Podatki pośrednie** > **Podatek** > **Urzędy skarbowe**.
    2. Z listy wybierz opcję **TA**.
    3. W polu **Identyfikacja urzędu** wprowadź **123**.

4. Ustawianie kodów regionów.

    1. Wybierz kolejno opcje **Administrowanie organizacją** > **Globalna książka adresowa** > **Adresy** > **Utworzenie adresu**.
    2. Na karcie **Kraj/prowincja** w polu **Kraj/region** wybierz pozycję **DEU**, a następnie wybierz pozycję **Zastosuj filtr**.
    3. W siatce wybierz **BE**, a następnie w polu **Kod Intrastat** wprowadź **11**.
    4. Na okienku akcji wybierz opcję **Zapisz**.

5. Konfigurowanie parametrów handlu zagranicznego.

    1. Wybierz kolejno opcje **Podatek** > **Ustawienia** > **Handel zagraniczny** > **Parametry handlu zagranicznego**.
    2. Na karcie **Intrastat**, na skróconej karcie **Ogólne**, w polu **Kod** **transakcji** wybierz wartość **11**.
    3. W polu **Faktura kredytowa** wybierz **21**.
    4. W polu **Urząd** wybierz **TA**.
    5. Na skróconej karcie **Raportowanie elektroniczne** w polu **Mapowanie formatu pliku** wybierz pozycję **INSTAT XML (DE)**.
    6. W polu **Mapowanie formatu raportów** wybierz wartość **Raport Intrastat**.
    7. Na skróconej karcie **hierarchii kodów asortymentu** w polu **Hierarchia kategorii** upewnij się, że wybrano pozycję **Intrastat**.
    8. Kliknij kartę **Właściwości kraju/regionu** i wybierz **Nowe**.
    9. W polu **Kraj/region partii** wybierz **FRA**.
    10. W polu **Typ kraju/regionu** wybierz opcję **UE**.

6. Przypisz kod towaru do produktu i ustaw pochodzenie produktu. Pola **Kod towaru**, **Kraj/region pochodzenia** i **Kraj** pochodzenia zostaną automatycznie ustawione na zamówieniach sprzedaży i zamówieniach zakupu po wybraniu produktu.

    1. Przejdź do **Zarządzanie informacjami o produktach** > **Produkty** > **Zwolnione produkty**.
    2. W siatce zaznacz element **D0001**.
    3. Na skróconej karcie **Handel zagraniczny**, w sekcji **Intrastat**, w polu **Asortyment** wybierz **920 20 34**.
    4. W sekcji **Pochodzenie** w polu **kraj/region** wybierz **DEU**.
    5. Na skróconej karcie **Zarządzanie zapasami** w sekcji **Pomiary wagi** w polu **Waga netto** wprowadź **12**.
    6. Na okienku akcji wybierz opcję **Zapisz**.

7. Przypisz transport do środka dostawy. Kod transportu zostanie automatycznie ustawiony na zamówieniach po wybraniu sposobu dostawy.

    1. Przejdź do **Zaopatrzenie i sourcing** > **Ustawienia** > **Dystrybucja** > **Metody dostawy**.
    2. Z listy wybierz opcję **10**.
    3. Na skróconej karcie **Handel zagraniczny** w polu **Transport** wybierz wartość **01**.

8. Utwórz zamówienie sprzedaży z odbiorcą z UE.

    1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** > **Zamówienia** > **Wszystkie zamówienia sprzedaży**.
    2. W okienku akcji wybierz opcję **Nowy**.
    3. W oknie dialogowym **Utwórz zamówienie sprzedaży**, na skróconej karcie **Klient**, w sekcji **Klient**, w polu **Konto klienta** wybierz **DE-012**.
    4. Na **skróconej karcie Ogólne** w sekcji **Wymiary magazynu** w polu **Lokacja** wybierz pozycję **1**.
    5. W polu **Magazyn** wybierz wartość **11**.
    6. Kliknij przycisk **OK**.
    7. Na karcie **Nagłówek**, na skróconej karcie **Handel zagraniczny**, w polu **Port** wybierz wartość **53**.
    8. W polu **Procedura statystyczna** wybierz **31710**.
    9.  Na karcie **Wiersze**, na skróconej karcie **Wiersze** **zamówienia sprzedaży** w polu **Numer towaru** wybierz wartość **D0001**. W polu **Ilość** wpisz wartość **10**.
    10. Na skróconej karcie **Szczegóły wiersza**, na karcie **Handel zagraniczny** upewnij się, że pola **Kod transakcji**, **Transport**, **Asortyment** i **Kraj/region pochodzenia** są ustawiane automatycznie.
    11. Na okienku akcji wybierz opcję **Zapisz**.
    12. W okienku akcji na karcie **Faktura** w sekcji **Generuj** wybierz **Faktura**.
    13. W **oknie dialogowym Księgowanie faktury**, na skróconej karcie **Parametry** w sekcji **Parametr** w polu **Ilość** zaznacz opcję **Wszystko**.
    14. Wybierz **OK**, aby zaksięgować fakturę.

9.  Przenieś transakcję do arkusza Intrastat i przejrzyj wynik.

    1. Wybierz kolejno opcje **Podatek** > **Deklaracje** > **Handel zagraniczny** > **Intrastat**.
    2. W okienku akcji wybierz pozycję **Transfer**.
    3. W oknie dialogowym **Intrastat (Przeniesienie)** w sekcji **Parametry** ustaw opcję **Faktura dla odbiorcy** na **wartość Tak**.
    4. Wybierz **Filtry**.
    5. W oknie dialogowym **Filtr Intrastat** na karcie **Zakres** wybierz pierwszy wiersz i upewnij się, że pole **Pole** jest ustawione na **Data**.
    6. W polu **Kryteria** wybierz bieżącą datę.
    7. Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Filtr Intrastat**.
    8. Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Filtr Intrastat** i sprawdzić wynik. W wierszu pokazane jest pierwsze utworzone wcześniej zamówienie sprzedaży.

        ![W wierszu pokazane jest utworzone wcześniej na stronie Intrastat zamówienie sprzedaży](media/intrastat_deu_1.png)

10. Wybierz wiersz transakcji, a następnie wybierz kartę **Ogólne**, aby wyświetlić więcej szczegółów.

    ![Szczegóły zamówienia sprzedaży na karcie Ogólne na stronie Intrastat](media/intrastat_deu_2.png)

11. Tworzenie noty kredytowej używając faktury sprzedaży.

    1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** > **Zamówienia** > **Wszystkie zamówienia sprzedaży**.
    2. W okienku akcji wybierz opcję **Nowy**.
    3. W oknie dialogowym **Utwórz zamówienie sprzedaży**, na skróconej karcie **Klient**, w sekcji **Klient**, w polu **Konto klienta** wybierz **DE-012**.
    4. Na **skróconej karcie Ogólne** w sekcji **Wymiary magazynu** w polu **Lokacja** wybierz pozycję **1**.
    5. W polu **Magazyn** wybierz wartość **11**.
    6. Na karcie **Nagłówek**, na skróconej karcie **Handel zagraniczny**, w polu **Port** wybierz wartość **53**.
    7. W polu **Procedura statystyczna** wybierz **31710**.
    8. Na karcie **Wiersze**, na skróconej karcie **Wiersze** **zamówienia sprzedaży** w polu **Numer towaru** wybierz wartość **D0001**. W polu **Ilość** wpisz wartość **-2**.
    9. Na skróconej karcie **Szczegóły wiersza**, na karcie **Handel zagraniczny**, w polu **Kod transakcji** wybierz wartość **21**.
    10. Upewnij się, że pola **Transport**, **Asortyment** i **Kraj/region pochodzenia** są ustawiane automatycznie.
    11. Na okienku akcji wybierz opcję **Zapisz**.
    12. W okienku akcji na karcie **Faktura** w sekcji **Generuj** wybierz **Faktura**.
    13. W **oknie dialogowym Księgowanie faktury**, na skróconej karcie **Parametry** w sekcji **Parametr** w polu **Ilość** zaznacz opcję **Wszystko**.
    14. Wybierz **OK**, aby zaksięgować fakturę.

12. Przenieś transakcję do arkusza Intrastat i przejrzyj wynik.

    1. Wybierz kolejno opcje **Podatek** > **Deklaracje** > **Handel zagraniczny** > **Intrastat**.
    2. W okienku akcji wybierz pozycję **Transfer**.
    3. W oknie dialogowym **Intrastat (Przeniesienie)** w sekcji **Parametry** ustaw opcję **Faktura dla odbiorcy** na **wartość Tak**.
    4. Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Filtr Intrastat** i sprawdzić wynik. Dodano nowy wiersz, w którym zostało ustawione pole **Kierunek** na **Przyjęcia**.            
        Ten wiersz reprezentuje fizyczny zwrot towarów.

        ![Wiersz fizycznego zwrotu towarów na stronie Intrastat](media/intrastat_deu_3.png)

13. Wybierz wiersz transakcji, a następnie wybierz kartę **Ogólne**, aby wyświetlić więcej szczegółów.

    ![Szczegóły fizycznego zwrotu towarów na karcie Ogólne na stronie Intrastat](media/intrastat_deu_4.png)

14. Tworzenie faktury korygującej używając zamówienia sprzedaży:

    1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** > **Zamówienia** > **Wszystkie zamówienia sprzedaży**.
    2. W okienku akcji wybierz opcję **Nowy**.
    3. W oknie dialogowym **Utwórz zamówienie sprzedaży**, na skróconej karcie **Klient**, w sekcji **Klient**, w polu **Konto klienta** wybierz **DE-012**.
    4. Na **skróconej karcie Ogólne** w sekcji **Wymiary magazynu** w polu **Lokacja** wybierz pozycję **1**.
    5. W polu **Magazyn** wybierz wartość **11**.
    6. Na karcie **Nagłówek**, na skróconej karcie **Handel zagraniczny**, w polu **Port** wybierz wartość **53**.
    7. W polu **Procedura statystyczna** wybierz **31710**.
    8. Na karcie **Wiersze**, na skróconej karcie **Wiersze** **zamówienia sprzedaży** w polu **Numer towaru** wybierz wartość **D0001**. W polu **Ilość** wpisz wartość **-3**.
    9. Na skróconej karcie **Szczegóły wiersza**, na karcie **Handel zagraniczny**, w polu **Kod transakcji** wybierz wartość **11**.
    10. Upewnij się, że pola **Transport**, **Asortyment** i **Kraj/region pochodzenia** są ustawiane automatycznie.
    11. Na okienku akcji wybierz opcję **Zapisz**.
    12. Upewnij się, że pole **Kod transakcji** zawiera wartość 11.
    13. W okienku akcji na karcie **Faktura** w sekcji **Generuj** wybierz **Faktura**.
    14. W **oknie dialogowym Księgowanie faktury**, na skróconej karcie **Parametry** w sekcji **Parametr** w polu **Ilość** zaznacz opcję **Wszystko**.
    15. Wybierz **OK**, aby zaksięgować fakturę.

15. Przenieś transakcję do arkusza Intrastat i przejrzyj wynik:

    1. Wybierz kolejno opcje **Podatek** > **Deklaracje** > **Handel zagraniczny** > **Intrastat**.
    2. W okienku akcji wybierz pozycję **Transfer**.
    3. W oknie dialogowym **Intrastat (Przeniesienie)** w sekcji **Parametry** ustaw opcję **Faktura dla odbiorcy** na **wartość Tak**.
    4. Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Filtr Intrastat** i sprawdzić wynik. Dodano nowy wiersz, w którym w kolumnie **Korekta** jest wyświetlany znacznik wyboru.

        ![Wiersz korekty na stronie Intrastat](media/intrastat_deu_5.png)

16. Wybierz wiersz transakcji, a następnie wybierz kartę **Ogólne**, aby wyświetlić więcej szczegółów.

    ![Szczegóły korekty na karcie Ogólne na stronie Intrastat](media/intrastat_deu_6.png)

17. W okienku akcji wybierz pozycję **Dane wyjściowe** > **Raport**.
18. W oknie dialogowym **Raport Intrastat**, na skróconej karcie **Parametry**, w sekcji **Data** wybierz miesiąc utworzonego zamówienia sprzedaży.
19. W sekcji **Opcje** **eksportu** ustaw wartość **Tak** dla opcji **Generuj plik**.
20. W polu **Nazwa pliku** wprowadź wymaganą nazwę.
21. Wybierz przycisk **OK** i przejrzyj wygenerowany raport. W poniższej tabeli przedstawiono wartości w przykładowym raporcie.

    | **Imię i nazwisko**                  | **Faktura sprzedaży**  |   **Korekta**   | **Faktura kredytowa** |
    |---------------------------|--------------------|--------------------|-----------------|
    | declarationId             | 2021-07-D          | 2021-07-A          |                 |
    | referencePeriod           | 2021-07            | 2021-07            |                 |
    | PSIId                     | 11203/118/12345000 | 11203/118/12345000 |                 |
    | functionCode              | O                  | O                  |                 |
    | flowCode                  | D                  | A                  |                 |
    | CurrencyCode              | EUR                | EUR                |                 |
    | itemNumber                | 0000362            | 0000362            | 0000361         |
    | CN8Code                   | 9202034            | 9202034            | 9202034         |
    | goodsDescription          | Speaker            | Speaker            | Speaker         |
    | MSConsDestCode            | FR                 | FR                 | FR              |
    | countryOfOriginCode       | \-                 | \-                 | DE              |
    | netMass                   | 120                | -36                | 24              |
    | invoicedAmount            | 3290               | -987               | \-              |
    | StatisticalValue          | 3290               | -987               | 658             |
    | natureOfTransactionACode  | 1                  | 1                  | 2               |
    | natureOfTransactionBCode  | 1                  | 1                  | 1               |
    | modeOfTransportCode       | 01                 | 01                 | 01              |
    | regionCode                | 11                 | 11                 | 11              |
    | portAirportInlandportCode | 53                 | 53                 | 53              |

