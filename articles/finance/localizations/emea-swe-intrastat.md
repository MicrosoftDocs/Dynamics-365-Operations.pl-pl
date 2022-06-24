---
title: Intrastat — Szwecja
description: Ten artykuł zawiera informacje o raportowaniu Intrastat w Szwecji.
author: anasyash
ms.date: 8/24/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: ''
ms.openlocfilehash: a81f0c19923d1a4747c2ecb8ab03dd86b45497ad
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886268"
---
# <a name="swedish-intrastat"></a>Szwedzki intrastat

[!include[banner](../includes/banner.md)]

Strona **Intrastat** służy do generowania i raportowania informacji o handlu między krajami Unii Europejskiej (UE). Szwedzka deklaracja Intrastat zawiera informacje o handlu towarami do zgłoszenia.

W szwedzkiej deklaracji Intrastat znajdują się następujące pola:

   - Kod ISO kraju partnera
   - Kod transakcji
   - Kod asortymentu
   - Jednostka dodatkowa
   - Masa
   - Kwota faktury

## <a name="set-up-intrastat"></a>Konfiguracja Intrastat

Zaimportuj najnowszą wersję następujących konfiguracji raportowania elektronicznego (ER):

   - Model Intrastat
   - Raport Intrastat
   - Intrastat (SE)

Więcej informacji można znaleźć w temacie [Pobieranie konfiguracji ER z globalnego repozytorium usługi Configuration service](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

## <a name="set-up-foreign-trade-parameters"></a>Konfigurowanie parametrów handlu zagranicznego

1. W Microsoft Dynamics 365 Finance wybierz kolejno opcje **Podatek** > **Ustawienia** > **Parametry handlu zagranicznego**.
2. Na karcie **Intrastat**, na skróconej karcie **Intrastat** w polu **Mapowanie formatu pliku** wybierz pozycję **Intrastat (SE)**.
3. W polu **Mapowanie formatu raportów** wybierz wartość **Raport Intrastat**.
4. Na skróconej karcie **hierarchii kodów asortymentu** w polu **Hierarchia kategorii** wybierz pozycję **Intrastat**.
5. W polu **Kod transakcji** wybierz kod transakcji dla przeniesień właściwości. Kod ten będzie wykorzystywany do tworzenia transakcji powodujących faktyczne lub planowane przeniesienie własności za odszkodowaniem (finansowej lub innej). Można go również użyć do poprawek. Firmy ze Szwecji używają jednocyfrowych kodów transakcji.
6. W polu **Nota kredytowa** wybierz kod transakcji zwrotu towarów.
7. Na karcie **Właściwości kraju/regionu**, w polu **Kraj/region**, podaj listę wszystkich krajów lub regionów, w których organizacja prowadzi interesy. Dla każdego kraju należącego do UE w polu **Typ kraju/regionu** wybierz pozycję **UE**, aby kraj były wyświetlany w raporcie Intrastat.

## <a name="set-up-the-product-parameters-for-the-intrastat-declaration"></a>Konfigurowanie parametrów produktu na potrzeby deklaracji Intrastat

1. Przejdź do **Zarządzanie informacjami o produktach** > **Produkty** > **Zwolnione produkty**.
2. Wybierz produkt w siatce.
3. Na skróconej karcie **Handel zagraniczny**, w sekcji **Intrastat**, w polu **Asortyment** wybierz odpowiedni kod asortymentu.
4. Na skróconej karcie **Zarządzanie zapasami** w polu **Waga netto** wprowadź masę produktu w kilogramach.
5. Przejdź do **Podatek** > **Ustawienia** > **Handel zagraniczny** > **Kompresja Intrastat** i wybierz pola, które należy porównać, gdy informacje Intrastat podsumowano. Dla szwedzkiego Intrastat określ wartości w następujących obowiązkowych polach:

    - Asortyment
    - Kod transakcji
    - Kierunek
    - Kraj/region
    - Korekta
    - Faktura VAT

## <a name="intrastat-transfer"></a>Przeniesienie do Intrastat

Na stronie **Intrastat** w okienku akcji możesz wybrać **Transfer**, aby automatycznie przesyłać informacje o handlu wewnątrzwspólnotowym z zamówień sprzedaży, faktur niezależnych, zamówień zakupu, faktur od dostawców, pokwitowań produktów od dostawców , faktury projektowe i zlecenia przeniesienia. Przekazywane będą tylko dokumenty, w których krajem lub regionem przeznaczenia jest kraj UE (w przypadku wysyłek) lub przesyłka (w przypadku przywozów).

Transakcje można również wprowadzać ręcznie, wybierając opcję **Nowe** w okienku akcji.

### <a name="generate-an-intrastat-report"></a>Wygeneruj raport Intrastat

1. Wybierz kolejno opcje **Podatek** > **Deklaracje** > **Handel zagraniczny** > **Intrastat**.
2. W okienku akcji wybierz pozycję **Dane wyjściowe** > **Raport**.
3. W oknie dialogowym **Raport Intrastat** można ustawić następujące pola.

    | Pole            | opis                                                                                                                         |
    |------------------|-------------------------------------------------------------------------------------------------------------------------------------|
    | Data rozpoczęcia        | Wybierz datę rozpoczęcia raportu.                                                                                               |
    | Data zakończenia          | Wybierz datę zakończenia raportu.                                                                                                 |
    | Generuj plik    | Ustaw tę opcję na wartość **Tak**, aby był generowany plik .txt raportu Intrastat.                                                       |
    | Nazwa pliku        | Umożliwia wprowadzanie nazwy pliku .txt.                                                                                                    |
    | Generuj raport  | Ustaw tę opcję na wartość **Tak**, aby był generowany plik .xlsx raportu Intrastat.                                                     |
    | Nazwa pliku raportu | Umożliwia wprowadzanie nazwy pliku .xlsx.                                                                                                   |
    | Kierunek        | Wybierz **opcję Przyjęcia** do raportu o wewnątrzwspólnotowych przyjęć. Wybierz **opcję Wysyłki** do raportu o wysyłkach wewnątrzwspólnotowych. |

4. Wybierz przycisk **OK** i przejrzyj wygenerowane raporty.

## <a name="example"></a>Przykład

W tym przykładzie pokazano, jak księgować przyjęcia i wysyłki dla Intrastat. Użyj firmy **DEMF**.

### <a name="preliminary-setup"></a>Konfiguracja wstępna

1. Wybierz kolejno opcje **Administrowanie organizacją** > **Organizacja** > **Firmy** i wybierz firmę **DEMF**.
2. Na skróconej karcie **Adresy** naciśnij przycisk **Edytuj**, a następnie w polu **Kraj/region** wybierz pozycję **SWE (Szwecja)**.
3. Zaimportuj najnowszą wersję następujących konfiguracji ER:

    - Model Intrastat
    - Raport Intrastat
    - Intrastat (SE)

### <a name="create-transaction-codes"></a>Tworzenie kodów transakcji

1. Wybierz kolejno opcje **Podatek** > **Ustawienia** > **Handel zagraniczny** > **Kody transakcji**.
2. W okienku akcji wybierz opcję **Nowy**.
3. W polu **Kod** **transakcji** wpisz **1**.
4. W polu **Nazwa** wpisz **Normalne transakcje**.
5. Na okienku akcji wybierz opcję **Zapisz**.

### <a name="set-up-foreign-trade-parameters"></a>Konfigurowanie parametrów handlu zagranicznego

1. Wybierz kolejno opcje **Podatek** > **Ustawienia** > **Handel zagraniczny** > **Parametry handlu zagranicznego**.
2. Na karcie **Intrastat**, na skróconej karcie **Ogólne**, w polu **Kod** **transakcji** wybierz wartość **1**.
3. Na skróconej karcie **Raportowanie elektroniczne** w polu **Mapowanie formatu pliku** wybierz pozycję **Intrastat (SE)**.
4. W polu **Mapowanie formatu raportów** wybierz wartość **Raport Intrastat**.
5. Na skróconej karcie **hierarchii kodów asortymentu** w polu **Hierarchia kategorii** upewnij się, że wybrano pozycję **Intrastat**.
6. Kliknij kartę **Właściwości kraju/regionu** i wybierz **Nowe**.
7. W polu **Kraj/region partii** wybierz **SWE**.
8. W polu **Typ kraju/regionu** wybierz opcję **Krajowy**.
9. W polu **Kraj/region strony** wybierz **DEU**, a następnie w polu **Typ kraju/regionu** wybierz **UE**.

### <a name="set-up-product-information"></a>Konfigurowanie informacji o produktach

1. Przejdź do **Zarządzanie informacjami o produktach** > **Produkty** > **Zwolnione produkty**.
2. W siatce zaznacz element **D0001**.
3. Na skróconej karcie **Handel zagraniczny**, w sekcji **Intrastat**, w polu **Asortyment** wybierz **100 200 30**.
4. Na skróconej karcie **Zarządzanie zapasami** w sekcji **Pomiary wagi** w polu **Waga netto** wprowadź **5**.
5. Na okienku akcji wybierz opcję **Zapisz**.

### <a name="change-the-site-address"></a>Zmienianie adresu lokalizacji

1. Wybierz kolejno opcje **Zarządzanie magazynem** > **Ustawienia** > **Magazyn** > **Lokalizacje**.
2. W siatce zaznacz element **1**.
3. Na skróconej karcie **Adresy** wybierz pozycję **Edytuj**.
4. W oknie dialogowym **Edycja adresu** w polu **Kraj/region** wybierz pozycję **SWE**.
5. Kliknij przycisk **OK**.

### <a name="create-a-sales-order-with-an-eu-customer"></a>Tworzenie zamówienia sprzedaży z odbiorcą z UE

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** > **Zamówienia** > **Wszystkie zamówienia sprzedaży**.
2. W okienku akcji wybierz opcję **Nowy**.
3. W oknie dialogowym **Utwórz zamówienie sprzedaży**, na skróconej karcie **Klient**, w sekcji **Klient**, w polu **Konto klienta** wybierz **DE-015**.
4. Na **skróconej karcie Ogólne** w sekcji **Wymiary magazynu** w polu **Lokacja** wybierz pozycję **1**.
5. W polu **Magazyn** wybierz wartość **11**.
6. Kliknij przycisk **OK**.
7. Na karcie **Wiersze**, na skróconej karcie **Wiersze zamówienia sprzedaży** w polu **Numer pozycji** wybierz wartość **D0001**. W polu **Ilość** wpisz wartość **10**.
8. Na skróconej karcie **Szczegóły wiersza**, na karcie **Handel zagraniczny** upewnij się, że pola **Kod transakcji** i **Asortyment** są ustawiane automatycznie.
9. Na okienku akcji wybierz opcję **Zapisz**.
10. W okienku akcji na karcie **Faktura** w sekcji **Generuj** wybierz **Faktura**.
11. W **oknie dialogowym Księgowanie faktury**, na skróconej karcie **Parametry** w sekcji **Parametr** w polu **Ilość** zaznacz opcję **Wszystko**.
12. Wybierz **OK**, aby zaksięgować fakturę.

### <a name="transfer-the-transaction-to-the-intrastat-journal-and-review-the-result"></a>Przenieś transakcję do arkusza Intrastat i przejrzyj wynik.

1. Wybierz kolejno opcje **Podatek** > **Deklaracje** > **Handel zagraniczny** > **Intrastat**.
2. W okienku akcji wybierz pozycję **Transfer**.
3. W oknie dialogowym **Intrastat (Przeniesienie)** w sekcji **Parametry** ustaw opcję **Faktura dla odbiorcy** na **wartość Tak**.
4. Wybierz **Filtry**.
5. W oknie dialogowym **Filtr Intrastat** na karcie **Zakres** wybierz pierwszy wiersz i upewnij się, że pole **Pole** jest ustawione na **Data**.
6. W polu **Kryteria** wybierz bieżącą datę.
7. Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Filtr Intrastat**.
8. Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Filtr Intrastat** i sprawdzić wynik. W wierszu pokazane jest pierwsze utworzone wcześniej zamówienie sprzedaży.

    ![Wiersze arkusza Intrastat zamówienia sprzedaży](media/swe_intrastat_journal_sales_order.png)

9. Wybierz wiersz transakcji, a następnie wybierz kartę **Ogólne**, aby wyświetlić więcej szczegółów.

    ![Szczegóły wiersza arkusza Intrastat zamówienia sprzedaży](media/swe_intrastat_journal_sales_order_line_details.png)

10. W okienku akcji wybierz pozycję **Dane wyjściowe** > **Raport**.
11. W oknie dialogowym **Raport Intrastat**, na skróconej karcie **Parametry**, w sekcji **Data** wybierz miesiąc utworzonego zamówienia sprzedaży.
12. W sekcji **Opcje** **eksportu** ustaw wartość **Tak** dla opcji **Generuj plik**. Następnie w polu **Nazwa pliku** wprowadź wymaganą nazwę.
13. W polu **Generuj raport** wybierz opcję **Tak**. Następnie w polu **Nazwa pliku raportu** wprowadź wymaganą nazwę.
14. W polu **Kierunek** wybierz opcję **Wysyłki**.
15. Naciśnij przycisk **OK** i przejrzyj wygenerowany raport w formacie .txt. W poniższej tabeli przedstawiono wartości w przykładowym raporcie.

    | Kod ISO kraju partnera | Kod transakcji | Kod asortymentu | Jednostka dodatkowa | Masa | Kwota faktury |
    |--------------------------|------------------|----------------|-----------------|--------|----------------|
    | IT                       | 1                | 10020030       | 0               | 50     | 3290           |

16. Przejrzyj wygenerowany raport w formacie Excel.

    ![Raport Intrastat](media/swe_intrastat_report_for_dispatches.png)

### <a name="create-a-purchase-order"></a>Tworzenie zamówienia zakupu

1. Wybierz kolejno opcje **Rozrachunki z dostawcami** > **Zamówienia zakupu** > **Wszystkie zamówienia zakupu**.
2. W okienku akcji wybierz opcję **Nowy**.
3. W oknie dialogowym **Tworzenie zamówienia zakupu** w polu **Konto dostawcy** wybierz pozycję **DE-001**.
4. Kliknij przycisk **OK**.
5. Na karcie **Nagłówek** na skróconej karcie **Handel** **zagraniczny** sprawdź, czy w polu **Kod transakcji** znajduje się wartość **1**.
6. Na karcie **Wiersze**, na skróconej karcie **Wiersze zamówienia zakupu** w polu **Numer pozycji** wybierz wartość **D0001**. W polu **Ilość** wpisz wartość **6**.
7. W okienku akcji na karcie **Zakup** w grupie **Akcje** wybierz opcję **Potwierdź**.
8. W okienku akcji na karcie **Faktura** w grupie **Generuj** wybierz **Faktura**.
9. W okienku akcji wybierz **Domyślne z**. W polu **Domyślna ilość dla wierszy** zaznacz wartość **Ilość zamówiona**. Następnie wybierz opcję **OK**.
10. Na skróconej karcie **Nagłówek faktury od dostawcy**, w sekcji **Identyfikacja faktury**, w polu **Numer** wprowadź wartość **0001**.
11. W okienku akcji naciśnij przycisk **Zaksięguj**, aby zaksięgować fakturę

### <a name="create-an-intrastat-declaration-for-arrivals"></a>Tworzenie deklaracji Intrastat dla przyjęć

1. Wybierz kolejno opcje **Podatek** > **Deklaracje** > **Handel zagraniczny** > **Intrastat**.
2. W okienku akcji wybierz pozycję **Transfer**.
3. W oknie dialogowym **Intrastat (Przeniesienie)** ustaw opcję **Faktura od dostawcy** na wartość **Tak**.
4. Kliknij **OK**, aby przenieść transakcje, i przejrzyj arkusz Intrastat.

    ![Arkusz Intrastat zamówienia zakupu](media/swe_intrastat_journal_purchase_order.png)

5. Przejrzyj kartę **Ogólne** zamówienia zakupu.

    ![Szczegóły wiersza arkusza Intrastat zamówienia zakupu](media/swe_intrastat_journal_purchase_order_line_details.png)

6. W okienku akcji wybierz pozycję **Dane wyjściowe** > **Raport**.
7. W oknie dialogowym **Raport Intrastat**, na skróconej karcie **Parametry**, w sekcji **Data** wybierz miesiąc utworzonego zamówienia sprzedaży.
8. W sekcji **Opcje** **eksportu** ustaw wartość **Tak** dla opcji **Generuj plik**. Następnie w polu **Nazwa pliku** wprowadź wymaganą nazwę.
9. W polu **Generuj raport** wybierz opcję **Tak**. Następnie w polu **Nazwa pliku raportu** wprowadź wymaganą nazwę.
10. W polu **Kierunek** wybierz opcję **Przyjęcia**.
11. Naciśnij przycisk **OK** i przejrzyj wygenerowany raport w formacie .txt. W poniższej tabeli przedstawiono wartości w przykładowym raporcie.

    | Kod ISO kraju partnera | Kod transakcji | Kod asortymentu | Jednostka dodatkowa | Masa | Kwota faktury |
    |--------------------------|------------------|----------------|-----------------|--------|----------------|
    | IT                       | 1                | 10020030       | 0               | 30     | 1714           |

12. Przejrzyj wygenerowany raport w formacie Excel.

    ![Raport przyjęć Intrastat](media/swe_intrastat_arrivals_report.png)
