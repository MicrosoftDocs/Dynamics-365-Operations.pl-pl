---
title: Księgowanie przyjęć i wysyłek dla Intrastat
description: W tym temacie pokazano na przykładzie, jak księgować przyjęcia i wysyłki dla Intrastat.
author: anasyash
ms.date: 8/23/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: ''
ms.openlocfilehash: 4ab4402740d199043519773b18732bdde9a0fb2f
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2022
ms.locfileid: "8724791"
---
# <a name="post-arrivals-and-dispatches-for-intrastat"></a>Księgowanie przyjęć i wysyłek dla Intrastat

[!include [banner](../includes/banner.md)]

W tym temacie pokazano na przykładzie, jak księgować przyjęcia i wysyłki dla Intrastat. W przykładzie użyto firmy **ITCO**.

## <a name="setup"></a>Konfiguracja

1. Zaimportuj najnowszą wersję następujących konfiguracji raportowania elektronicznego (ER):

    - Model Intrastat
    - Raport Intrastat
    - Intrastat (IT)

    Dokładniejsze informacje można znaleźć w temacie [Pobieranie konfiguracji ER z globalnego repozytorium usługi Configuration service](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

2. W Microsoft Dynamics 365 Finance zdefiniuj następujące sekwencje numerów jako ciągłe: **Gene\_397**, **Acco\_16403**, **Gene\_407**, and **PUR\_EU**.

    1. Wybierz kolejno opcje **Administrowanie organizacją** > **Sekwencje numerów** > **Sekwencje numerów**.
    2. W siatce zaznacz jeden z kodów sekwencji numerów.
    3. W okienku akcji wybierz pozycję **Edytuj**.
    4. Na skróconej karcie **Ogólne**, w sekcji **Konfiguracja** ustaw opcję **Ciągłe** na **Tak**.
    5. Na okienku akcji wybierz opcję **Zapisz**.

3. Ustaw adres magazynu.

    1. Wybierz kolejno opcje **Zarządzanie magazynem** &gt; **Ustawienia** &gt; **Magazyn** &gt; **Magazyny**.
    2. Na liście wybierz magazyn **11**.
    3. Na skróconej karcie **Adres** wybierz pozycję **Dodaj**.
    4. W oknie dialogowym **Nowy** **adres** w polu **Nazwa** **lub** **opis** wprowadź **Główny**.
    5. W polu **Kraj/region** wybierz **ITA (Włochy)**.
    6. W polu **Miasto** wybierz **Aprilia**.
    7. Kliknij przycisk **OK**.

4. Ustaw kody transakcji.

    1. Wybierz kolejno opcje **Podatek** > **Ustawienia** > **Handel zagraniczny** > **Kody transakcji**.
    2. Wybierz opcję **Nowy** i skonfiguruj kod transakcji przeniesień własności.

        - W polu **Kod transakcji** wpisz **1**.
        - W polu **Nazwa** wpisz **Przeniesienie własności**.

    3. Wybierz opcję **Nowy** i skonfiguruj kod transakcji zwrotów.

        - W polu **Kod** **transakcji** wpisz **2**.
        - W polu **Nazwa** wpisz **Zwrot towarów**.

5.  Konfigurowanie parametrów handlu zagranicznego.

    1. Wybierz kolejno opcje **Podatek** > **Ustawienia** > **Handel zagraniczny** > **Parametry handlu zagranicznego**.
    2. Na karcie **Intrastat**, na skróconej karcie **Ogólne**, w polu **Kod** **transakcji** wybierz wartość **1**.
    3. W polu **Faktura kredytowa** wybierz **2**.
    4. W polu **Okres raportowania sprzedaży** wybierz opcję **Miesiąc**.
    5. W polu **Okres raportowania zakupów** wybierz opcję **Miesiąc**.
    6. Na skróconej karcie **Raportowanie elektroniczne** w polu **Mapowanie formatu pliku** wybierz pozycję **Intrastat (IT)**.
    7. W polu **Mapowanie formatu raportowania** wybierz wartość **Raport Intrastat**.
    8. Na skróconej karcie **Hierarchia kodów asortymentu** w polu **Hierarchia kategorii** wybierz pozycję **Intrastat**.
    9. Na skróconej karcie **Wartość statystyczna** ustaw opcję **Drukuj i wyeksportuj dane statystyczne** na **Tak**.
    10. Na karcie **Właściwości kraju/regionu** sprawdź, czy istnieją następujące wiersze.

        | **Strona/kraj/region** | **Kod Intrastat** | **Waluta** | **Typ kraju/regionu** |
        |--------------------------|--------------------|--------------|-------------------------|
        | ITA                      | IT                 | EUR          | Krajowe                |
        | SMR                      | SM                 | EUR          | Specjalne krajowe        |

    11. Na pasku narzędzi wybierz pozycję **Nowy**, aby utworzyć następujący wiersz.

        | **Strona/kraj/region** | **Kod Intrastat** | **Waluta** | **Typ kraju/regionu** |
        |--------------------------|--------------------|--------------|-------------------------|
        | DNK                      | DK                 | DKK          | UE                      |

6. Skonfiguruj numery identyfikacji podatkowej.

    1. Wybierz kolejno opcje **Podatek** > **Ustawienia** > **Podatek** > **Numery identyfikacji podatkowej**.
    2. W okienku akcji wybierz pozycję **Nowy**, aby utworzyć następujące wiersze.

        | **Kraj/region** | **Numer identyfikacji podatkowej** | **Nazwa firmy** |
        |--------------------|-----------------------|------------------|
        | DEU                | DE3456789012          | DOSTAWCA UE        |
        | DNK                | DK0987654321          | ER odbiorcy      |

7. Ustaw adres dostawcy.

    1. Przejdź do pozycji **Rozrachunki z dostawcami** &gt; **Dostawcy** &gt; **Wszyscy dostawcy**.
    2. W siatce wybierz pozycję **Dostawca UE**.
    3. Na skróconej karcie **Adresy** wybierz pozycję **Dodaj**.
    4. W oknie dialogowym **Nowy adres** w polu **Nazwa lub opis** wprowadź **Niemcy**.
    5. W polu **kraj/region** wybierz **DEU**.
    6. Wybierz **OK**, aby utworzyć nowy adres.
    7. Na skróconej karcie **Faktura i dostawa**, w sekcji **Podatek**, w polu **Numer identyfikacji podatkowej** wybierz pozycję **Wszystko**, a następnie wybierz pozycję **DE1234567890**.
    8. Na okienku akcji wybierz opcję **Zapisz**.

8. Ustaw adresy odbiorcy.

    1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** > **Odbiorcy** > **Wszyscy odbiorcy**.
    2. W siatce zaznacz element **ITCO-000001**.
    3. Na skróconej karcie **Adresy** wybierz pozycję **Edytuj**.
    4. W oknie dialogowym **Nowy adres** w polu **Nazwa lub opis** wprowadź **San Marino**.
    5. W polu **kraj/region** wybierz **SMR**.
    6. Wybierz **OK**, aby utworzyć nowy adres.
    7. Na skróconej karcie **Faktura i dostawa** w sekcji **Faktura** w polu **Konto faktury** wybierz pozycję **TCO-000001**.
    8. W polu **Grupa sekwencji numerów** wybierz pozycję **IT\_VENDOM**.
    9. W okienku akcji wybierz **Zapisz** i zamknij stronę.
    10. Na stronie **Wszyscy odbiorcy** w siatce wybierz pozycję **ITCO-000002**.
    11. Na skróconej karcie **Adresy** wybierz pozycję **Dodaj**.
    12. W oknie dialogowym **Nowy adres** w polu **Nazwa lub opis** wprowadź **Dania**.
    13. W polu **kraj/region** wybierz **DNK**.
    14. Wybierz **OK**, aby utworzyć nowy adres.
    15. Na skróconej karcie **Demograficzne dotyczące sprzedaży** w polu **Waluta** wybierz pozycję **DKK**.
    16. Na skróconej karcie **Faktura i dostawa**, w sekcji **Podatek**, w polu **Numer identyfikacji podatkowej** wybierz pozycję **IT\_PUREU**.
    17. W polu **Numer identyfikacji podatkowej** wybierz pozycję **Wszystko**, a następnie wybierz pozycję **DK0987654321**.
    18. Na okienku akcji wybierz opcję **Zapisz**.

9. Skonfiguruj hierarchię kategorii.

    1. Wybierz kolejno opcje **Zarządzanie informacjami o produktach** > **Ustawienia** > **Kategorie i atrybuty** > **Hierarchie kategorii**.
    2. W siatce zaznacz element **Intrastat**.
    3. W okienku akcji kliknij pozycję **Nowy węzeł kategorii**.
    4. W polu **Nazwa** wpisz **Usługa**.
    5. W polu **Kod** wpisz **123456**.
    6. Na okienku akcji wybierz opcję **Zapisz**.

10. Konfigurowanie produktów.

    1. Przejdź do **Zarządzanie informacjami o produktach** > **Produkty** > **Zwolnione produkty**.
    2. W siatce zaznacz element **ITEM**.
    3. Na skróconej karcie **Zakup** w sekcji **Administracja** w polu **Dostawca** wybierz pozycję **ITCO-000001**.
    4. Na skróconej karcie **Handel zagraniczny**, w sekcji **Intrastat**, w polu **Asortyment** wybierz **\[100 200 30\] Głośnik**.
    5. W sekcji **Pochodzenie** w polu **kraj/region** wybierz **DEU**.
    6. W polu **Stan/prowincja** wybierz pozycję **BE**.
    7. Na skróconej karcie **Zarządzanie zapasami** w sekcji **Wymiary netto** w polu **Waga netto** wprowadź **5**.
    8. Na okienku akcji wybierz opcję **Zapisz**.
    9. Na stronie **Zwolnione produkty** w siatce wybierz pozycję **Pozycja usługi**.
    10. Na skróconej karcie **Handel zagraniczny**, w sekcji **Intrastat**, w polu **Asortyment** wybierz **\[123456\] Usługa**.
    11. Na okienku akcji wybierz opcję **Zapisz**.

11. Skonfiguruj metody transportu.

    1. Wybierz kolejno opcje **Podatek** > **Ustawienia** > **Handel zagraniczny** > **Metoda transportu**.
    2. W okienku akcji wybierz pozycję **Nowy**, aby utworzyć następujące metody transportu.

        | **Transport** | **Opis** |
        |---------------|-----------------|
        | 1             | Drogowy            |
        | 2             | Lotniczy             |

12. Skonfiguruj tryb dostawy,

    1. Przejdź do **Zaopatrzenie i sourcing** > **Ustawienia** > **Dystrybucja** > **Metody dostawy**.
    2. W okienku akcji wybierz opcję **Nowy**.
    3. W polu **Tryb dostawy** wprowadź wartość **1**.
    4. W polu **Opis** wprowadź wartość **Ciężarówka**.
    5. Na skróconej karcie **Handel zagraniczny** w polu **Transport** wybierz wartość **Drogowy**.
    6. Na okienku akcji wybierz opcję **Zapisz**.

13. Skonfiguruj warunki dostawy.

    1. Wybierz kolejno opcje **Rozrachunki z dostawcami** > **Ustawienia** > **Warunki płatności**.
    2. Z listy wybierz opcję **CFR**.
    3. Na skróconej karcie **Ogólne** w polu **Kod Intrastat** wpisz wartość **1**.

## <a name="post-arrivals-for-intrastat"></a>Księgowanie przyjęć dla Intrastat

### <a name="purchase-goods-by-using-a-purchase-order"></a>Zakup towarów za pomocą zamówienia zakupu

W tej części przykładu pokazano, jak używać zamówienia zakupu do zakupu towarów z krajów Unii Europejskiej (UE).

1. Wybierz kolejno opcje **Rozrachunki z dostawcami** > **Zamówienia zakupu** > **Wszystkie zamówienia zakupu**.
2.  W okienku akcji wybierz opcję **Nowy**.
3.  W oknie dialogowym **Tworzenie zamówienia zakupu** w polu **Konto dostawcy** wybierz pozycję **Dostawca UE**.
4.  Na skróconej karcie **Administracja** w polu **Język** wybierz opcję **it**.
5.  Kliknij przycisk **OK**.
6.  W widoku **Nagłówek** na skróconej karcie **Handel** **zagraniczny** sprawdź, czy w polu **Kod transakcji** znajduje się wartość **1**.
7.  Sprawdź, czy w polu **Powiat pochodzenia/docelowy** jest ustawiona wartość **RM**.
8.  Na skróconej karcie **Dostawa** w sekcji **Dostawa** w polu **Tryb dostawy** wybierz pozycję **1**.
9.  W polu **Warunki dostawy** wybierz pozycję **CFR**.
10. Na widoku **Wiersze**, na skróconej karcie **Wiersze zamówienia zakupu** w polu **Numer pozycji** wybierz pozycję **Pozycja**.
11. W polu **Oddział** wybierz wartość **1**.
12. W polu **Magazyn** wybierz wartość **11**.
13. W polu **Ilość** wpisz wartość **10**.
14. W polu **Cena jednostkowa** wpisz **100**.
15. Na karcie **Konfiguracja**, w sekcji **Podatek**, w polu **Grupa podatków dla pozycji** wybierz pozycję **22%EU**.
16. W okienku akcji na karcie **Zakup** w grupie **Akcje** wybierz opcję **Potwierdź**.
17. W okienku akcji na karcie **Faktura** w grupie **Generuj** wybierz **Faktura**.
18. W okienku akcji wybierz **Domyślne z**.
19. W polu **Domyślna ilość dla wierszy** wybierz pozycję **Ilość zamówiona** i kliknij **OK**.
20. Na skróconej karcie **Nagłówek faktury od dostawcy**, w sekcji **Identyfikacja faktury**, w polu **Numer** wprowadź wartość **0001**.
21. W sekcji **Daty faktury**, w polu **Data faktury** wprowadź datę **7/9/2021**.
22. W okienku akcji naciśnij przycisk **Zaksięguj**, aby zaksięgować fakturę

### <a name="purchase-services-by-using-a-vendor-invoice"></a>Usługi zakupu na podstawie faktury od dostawcy

W tej części przykładu pokazano, jak używać faktury od dostawcy do zakupu usług z krajów UE.

1. Wybierz kolejno opcje **Rozrachunki z dostawcami** > **Faktury** > **Arkusz faktur**.
2. W okienku akcji wybierz opcję **Nowy**.
3. W polu **Nazwa** wybierz pozycję **VEND\_EUINV**.
4. W okienku akcji wybierz pozycję **Wiersze**.
5. W polu **Data** wprowadź datę **7/9/2021**.
6. W polu **Typ konta** wybierz pozycję **Dostawca**.
7. W polu **Konto** wybierz pozycję **Dostawca UE**.
8. W polu **Data faktury** wybierz datę faktury **7/9/2021**.
9. W polu **Faktura** wpisz **ITA-0004**.
10. W polu **Środki** wpisz **120000**.
11. W polu the **Typ** **konta przeciwstawnego** wybierz pozycję **Księga**.
12. W polu the **Konto przeciwstawne** wybierz pozycję **110130**.
13. W polu **Grupa podatków** wybierz pozycję **IT\_PUREU**.
14. W polu **Grupa podatków dla pozycji** wybierz pozycję **22%EU**.
15. Na karcie **Handel zagraniczny** wykonaj jeden z następujących kroków:

    1. W polu **Kod transakcji** wybierz wartość **1**.
    2. W polu **Transport** wybierz opcję **2 Lotniczy**.
    3. W polu **Asortyment** wybierz pozycję **\[123456\] Usługa**.
    4. W polu **kraj/region** wybierz **ITA**.
    5. W polu **Stan/prowincja** wybierz pozycję **LAZ**.
    6. W polu **Powiat pochodzenia/docelowy** wybierz pozycję **LT**.


16. W okienku akcji wybierz pozycję **Księguj**.
17. Utwórz deklarację Intrastat dla przyjęć.

    1. Wybierz kolejno opcje **Podatek** > **Deklaracje** > **Handel zagraniczny** > **Intrastat**.
    2. W okienku akcji wybierz pozycję **Transfer**.
    3. W oknie dialogowym **Intrastat (Przeniesienie)** ustaw opcję **Faktura od dostawcy** na wartość **Tak**.
    4. Kliknij **OK**, aby przenieść transakcje, a następnie przejrzyj arkusz Intrastat.

   ![Strona arkusza Intrastat, karta Przegląd.](media/ita_intrastat_journal_vendor_invoice.png)

18. Przejrzyj kartę **Ogólne** zamówienia zakupu.

    ![Szczegóły wiersza arkusza Intrastat zamówienia zakupu](media/ita_intrastat_journal_purchase_order_line_details.png)

19. Przejrzyj kartę **Ogólne** faktury od dostawcy.

    ![Szczegóły wiersza arkusza Intrastat dla faktury od dostawcy](media/ita_intrastat_journal_vendor_invoice_line_details.png)

20. Wygeneruj raport Intrastat dla przyjęć.

    1. W okienku akcji wybierz pozycję **Dane wyjściowe** > **Raport**.
    2. W oknie dialogowym **Raport Intrastat**, w sekcji **Data**, w polu **Od dnia** wybierz datę **7/1/2021**.
    3. W polu **Data końcowa** wybierz datę **7/31/2021**.
    4. W sekcji **Opcje eksportu** ustaw wartość **Tak** dla opcji **Generuj plik** i **Generuj raport**.
    5. W polu **Nazwa pliku** wpisz **Plik przyjęć**.
    6. W polu **Nazwa pliku raportu** wpisz **Raport przyjęć**.
    7. W polu **Kierunek** wybierz opcję **Przyjęcia**.
    8. W polu **Numer odwołania** wpisz wartość **123456**.
    9. Kliknij **OK**, aby wygenerować raport Intrastat i plik Intrastat, oraz je przejrzyj.

    Na poniższej ilustracji pokazano przykładowy raport Intrastat.

    ![Raport przyjęć Intrastat.](media/ita_intrastat_arrivals_report.png)

    Na poniższe ilustracji pokazano przykładowy plik Intrastat.

    ![Plik przyjęć Intrastat.](media/ita_intrastat_arrivals_file.png)

## <a name="post-dispatches-for-intrastat"></a>Księgowanie wysyłek dla Intrastat

### <a name="sell-goods-by-using-a-sales-order"></a>Sprzedaż towarów za pomocą zamówienia sprzedaży

W tej części przykładu pokazano, jak używać zamówienia sprzedaży do sprzedaży towarów do krajów Unii Europejskiej (UE).

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** > **Zamówienia** > **Wszystkie zamówienia sprzedaży**.
2. W okienku akcji wybierz opcję **Nowy**.
3. W oknie dialogowym **Utwórz zamówienie sprzedaży** w polu **Konto klienta** wybierz **ITCO-000002**.
4. Kliknij przycisk **OK**.
5. W widoku **Nagłówek**, na skróconej karcie **Dostawa**, w sekcji **Różne informacje o dostawie**, w polu **Tryb dostawy** wybierz pozycję **1 Ciężarówka**.
6. W polu **Warunki dostawy** wybierz pozycję **CFR**.
7. W widoku **Wiersze**, na skróconej karcie **Wiersze zamówienia sprzedaży** w polu **Numer pozycji** wybierz pozycję **ITEM**.
8. W polu **Ilość** wpisz wartość **50**.
9. W polu **Oddział** wybierz wartość **1**.
10. W polu **Magazyn** wybierz wartość **11**.
11. W polu **Cena jednostkowa** wpisz **250**.
12. Na skróconej karcie **Szczegóły wiersza**, na karcie **Konfiguracja**, w sekcji **Podatek**, w polu **Grupa podatków dla pozycji** wybierz pozycję **22%EU**.
13. Na okienku akcji wybierz opcję **Zapisz**.
14. W okienku akcji, na karcie **Faktura**, w grupie **Generuj** wybierz pozycję **Faktura**, aby utworzyć fakturę dla zamówienia.
15. W oknie dialogowym **Księgowanie faktury**, na skróconej karcie **Parametry** w sekcji **Parametr** w polu **Ilość** wybierz pozycję **Wszystko**.
16. Na skróconej karcie **Konfiguracja** w polu **Data** **faktury** wybierz datę **7/9/2021**.
17. Kliknij przycisk **OK**.
18. Przejrzyj wiersze w arkuszu Intrastat.

    1. Wybierz kolejno opcje **Podatek** > **Deklaracje** > **Handel zagraniczny** > **Intrastat**.
    2. W okienku akcji wybierz pozycję **Transfer**.
    3. W oknie dialogowym **Intrastat (Przeniesienie)** ustaw opcję **Faktura dla odbiorcy** na wartość **Tak**.
    4. Kliknij **OK**, aby przenieść transakcje, i przejrzyj arkusz Intrastat. Transakcja faktury korygującej jest oznaczona jako korekta i ma ujemną kwotę faktury.

        ![Strona arkusza Intrastat](media/ita_intrastat_journal_sales_order.png)

        ![Szczegóły wiersza arkusza Intrastat zamówienia sprzedaży](media/ita_intrastat_journal_sales_order_line_details.png)

### <a name="return-goods-by-using-a-credit-note"></a>Zwracanie towarów przy użyciu faktury korygującej

W tej części przykładu pokazano, jak używać faktury korygującej do zwracania towarów z krajów Unii Europejskiej (UE).

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** > **Zamówienia** > **Wszystkie zamówienia sprzedaży**.
2. W okienku akcji wybierz opcję **Nowy**.
3. W oknie dialogowym **Utwórz zamówienie sprzedaży** w polu **Konto klienta** wybierz **ITCO-000002**.
4. Kliknij przycisk **OK**.
5. W widoku **Nagłówek**, na skróconej karcie **Dostawa**, w sekcji **Różne informacje o dostawie**, w polu **Tryb dostawy** wybierz pozycję **1 Ciężarówka**.
6. W polu **Warunki dostawy** wybierz pozycję **CFR**.
7. Na skróconej karcie **Handel zagraniczny** w polu **Kod transakcji** wybierz wartość **2**.
8. Na karcie **Wiersze**, na skróconej karcie **Wiersze zamówienia sprzedaży** w polu **Numer pozycji** wybierz wartość **ITEM**.
9. W polu **Ilość** wpisz wartość **-10**.
10. W polu **Oddział** wybierz wartość **1**.
11. W polu **Magazyn** wybierz wartość **11**.
12. W polu **Cena jednostkowa** wpisz **250**.
13. Na skróconej karcie **Szczegóły wiersza**, na karcie **Konfiguracja**, w sekcji **Podatek**, w polu **Grupa podatków dla pozycji** wybierz pozycję **22%EU**.
14. W sekcji **Zwrot towaru**, w polu **Identyfikator partii zwrotu** wybierz partię, która została wcześniej utworzona.
15. Na okienku akcji wybierz opcję **Zapisz**.
16. W okienku akcji, na karcie **Faktura**, w grupie **Generuj** wybierz pozycję **Faktura**, aby utworzyć fakturę dla zamówienia.
17. Na skróconej karcie **Parametry**, w sekcji **Parametr** w polu **Ilość** wybierz pozycję **Wszystkie**.
18. W oknie dialogowym **Księgowanie faktury**, na skróconej karcie **Konfiguracja** w polu **Data** **faktury** wprowadź datę **7/9/2021**.
19. Wybierz **OK**, aby zaksięgować fakturę.
20. Przejrzyj wiersze w arkuszu Intrastat.

    1. Wybierz kolejno opcje **Podatek** > **Deklaracje** > **Handel zagraniczny** > **Intrastat**.
    2. W okienku akcji wybierz pozycję **Transfer**.
    3. W oknie dialogowym **Intrastat (Przeniesienie)** ustaw opcję **Faktura dla odbiorcy** na wartość **Tak**.
    4. Kliknij **OK**, aby przenieść transakcje, i przejrzyj arkusz Intrastat. Transakcja faktury korygującej jest oznaczona jako korekta i ma ujemną kwotę faktury.

    ![Faktura korygująca arkusza Intrastat](media/ita_intrastat_journal_credit_note.png)

    ![Szczegóły wiersza arkusza Intrastat dla faktury korygującej](media/ita_intrastat_journal_credit_note_line_details.png)

### <a name="sell-goods-to-san-marino-by-using-a-sales-order"></a>Sprzedaż towarów do San Marino za pomocą zamówienia sprzedaży

W tej części przykładu pokazano, jak używać zamówienia sprzedaży do zakupu towarów do San Marino.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** > **Zamówienia** > **Wszystkie zamówienia sprzedaży**.
2. W okienku akcji wybierz opcję **Nowy**.
3. W oknie dialogowym **Utwórz zamówienie sprzedaży** w polu **Konto klienta** wybierz **ITCO-000001**.
4. Kliknij przycisk **OK**.
5. W widoku **Nagłówek**, na skróconej karcie **Dostawa**, w sekcji **Różne informacje o dostawie**, w polu **Tryb dostawy** wybierz pozycję **1**.
6. W polu **Warunki dostawy** wybierz pozycję **CFR**.
7. Na karcie **Wiersze**, na skróconej karcie **Wiersze zamówienia sprzedaży** w polu **Numer pozycji** wybierz wartość **ITEM**.
8. W polu **Ilość** wpisz wartość **30**.
9. W polu **Oddział** wybierz wartość **1**.
10. W polu **Magazyn** wybierz wartość **11**.
11. W polu **Cena jednostkowa** wpisz **200**.
12. Na okienku akcji wybierz opcję **Zapisz**.
13. W okienku akcji, na karcie **Faktura**, w grupie **Generuj** wybierz pozycję **Faktura**, aby utworzyć fakturę dla zamówienia.
14. Na skróconej karcie **Parametry**, w sekcji **Parametr** w polu **Ilość** wybierz pozycję **Wszystkie**.
15. W oknie dialogowym **Księgowanie faktury**, na skróconej karcie **Konfiguracja** w polu **Data** **faktury** wprowadź datę **7/9/2021**.
16. Wybierz **OK**, aby zaksięgować fakturę.
17. Przejrzyj wiersze w arkuszu Intrastat.

    1. Wybierz kolejno opcje **Podatek** > **Deklaracje** > **Handel zagraniczny** > **Intrastat**.
    2. W okienku akcji wybierz pozycję **Transfer**.
    3. W oknie dialogowym **Intrastat (Przeniesienie)** ustaw opcję **Faktura dla odbiorcy** na wartość **Tak**.
    4. Kliknij **OK**, aby przenieść transakcje, i przejrzyj arkusz Intrastat.

   ![Arkusz Intrastat dla San Marino](media/ita_intrastat_journal_sales_order_san_marino.png)

   ![Szczegóły wiersza arkusza Intrastat dla San Marino](media/ita_intrastat_journal_sales_order_san_marino_line_details.png)

18. Utwórz deklarację Intrastat dla wysyłek.

    1. Wybierz kolejno opcje **Podatek** &gt; **Deklaracje** &gt; **Handel zagraniczny** &gt; **Intrastat**.
    2. W okienku akcji wybierz pozycję **Dane wyjściowe** &gt; **Raport**.
    3. W oknie dialogowym **Raport Intrastat**, w sekcji **Data**, w polu **Od dnia** wybierz datę **7/1/2021**.
    4. W polu **Data końcowa** wybierz datę **7/31/2021**.
    5. W sekcji **Opcje eksportu** ustaw wartość **Tak** dla opcji **Generuj plik** i **Generuj raport**.
    6. W polu **Nazwa pliku** wpisz **Plik wysyłek**.
    7. W polu **Nazwa pliku raportu** wpisz **Raport wysyłek**.
    8. W polu **Kierunek** wybierz opcję **Wysyłki**.
    9. W polu **Numer odwołania** wpisz wartość **98754**.
    10. Kliknij **OK**, aby wygenerować raport Intrastat i plik Intrastat.

        Na poniższej ilustracji pokazano przykładowy wydruk raportu Intrastat.

        ![Raport Intrastat](media/ita_intrastat_report_for_dispatches.png)

        Na poniższej ilustracji pokazano przykładowy wydruk pliku Intrastat.

        ![Plik Intrastat dla wysyłek](media/ita_intrastat_file_for_dispatches.png)
