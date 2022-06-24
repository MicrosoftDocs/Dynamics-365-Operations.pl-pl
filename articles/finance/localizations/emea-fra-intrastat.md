---
title: Intrastat — Francja
description: Ten artykuł zawiera informacje dotyczące deklaracji Intrastat we Francji.
author: anasyash
ms.date: 07/9/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: ''
ms.openlocfilehash: e86d7c8f28b1b3df0066a588d380965c21dc98a7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887861"
---
# <a name="french-intrastat"></a>Intrastat — Francja

[!include[banner](../includes/banner.md)]

Firmy we Francji zarejestrowane jako podatnik VAT (VAT) i prowadzące handel z innymi krajami Unii Europejskiej (UE) muszą zadeklarować wymianę towarów i usług do i z Francji. Deklaracja d'exchange de biens (Deklaracja handlu towarami lub DEB) to kombinacja listy sprzedaży do UE i raportu Intrastat. Raport ten należy składać co miesiąc dla wszystkich wewnątrzwspólnotowych sprzedaży towarów.

Raport DEB można wygenerować w jednym z dwóch elektronicznych formatów plików tekstowych: SAISUNIC 330 lub INTRACOM.

W poniższej tabeli przedstawiono pola zawarte we francuskiej deklaracji Intrastat w formacie SAISUNIC 330. W tabeli jest również wskazywany poziom raportu tego pola. Pole może mieć **4** (uproszczone), **1** (pełne) lub jedno i drugie.

| **Pole**                   | **Poziom raportu** |
|-----------------------------|------------------|
| Okres odwołania         | 4, 1              | 
| Numer deklaracji       | 4, 1              |
| Numer wiersza                 | 4, 1              |
| Kod ISO kraju (FR)       | 4, 1              | 
| Kod uzupełniający          | 4, 1              | 
| Numer siren                | 4, 1              | 
| Kod VAT odbiorcy        | 4, 1              | 
| Kod kierunku              | 4, 1              |
| Typ transakcji            | 4, 1              | 
| Poziom zobowiązania            | 4, 1              |
| Kod asortymentu              | 1                | 
| Krajowy NGP                | 1                | 
| Powiat (Dział)         | 1                |
| Charakter transakcji       | 1                | 
| Kraj pochodzenia      | 1                | 
| Kraj pochodzenia – import | 1                | 
| Ostateczne miejsce przeznaczenia - eksport | 1                | 
| Wartość faktury               | 4, 1              | 
| Wartość statystyczna           | 1                |
| Waga netto                  | 1                | 
| Jednostki dodatkowe            | 1                |
| Kod transportu              | 1                | 

W poniższej tabeli przedstawiono pola zawarte we francuskiej deklaracji Intrastat w formacie INTRACOM.
W tabeli jest również wskazywany poziom raportu tego pola. Pole może mieć **4** (uproszczone), **1** (pełne) lub jedno i drugie.

| **Pole**                   | **Poziom raportu**   | 
|-----------------------------|--------------------|
| Kod                        | 4, 1               | 
| Numer deklaracji       | 4, 1               |
| Liczba wierszy              | 4, 1               | 
| Syreny                       | 4, 1               |
| Powiat (Dział)         | 1                  |          
| Kod transportu              | 1                  |          
| Kraj pochodzenia           | 1                  |            
| Charakter transakcji       | 1                  |             
| Wartość faktury               | 4, 1               |             
| Metody dostawy           | 1                  |           
| Typ transakcji            | 4, 1               |            
| Poziom zobowiązania            | 4, 1               |           
| Kod asortymentu              | 1                  |            
| Krajowy NGP                | 1                  |            
| Waga netto                  | 1                  |            
| Wartość statystyczna           | 1                  |            
| Jednostki dodatkowe            | 1                  |            
| Kraj pochodzenia – import | 1                  |            
| Ostateczne miejsce przeznaczenia - eksport | 1                  |            
| Kod VAT odbiorcy        | 4, 1               |            
| Kod uzupełniający          | 4, 1               |           
| Okres odwołania         | 4, 1               |         

### <a name="set-up-intrastat"></a>Konfiguracja Intrastat

1.  W [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) w bibliotece zasobów udostępnionych pobierz najnowsze wersje następujących konfiguracji raportowania elektronicznego (ER) dla deklaracji Intrastat:

    - Model Intrastat
    - Raport Intrastat
    - Intrastat INTRACOM (Francja)
    - Intrastat SAISUNIC (Francja)

    Aby uzyskać więcej informacji, zobacz [Pobieranie konfiguracji modułu Raportowanie elektroniczne z usługi Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

2.  W rozwiązaniu Dynamics 365 Finance przejdź do **Podatek** > **Ustawienia** >  **Handel zagraniczny** > **Parametry handlu zagranicznego** i wykonaj następujące kroki:

    1. Na karcie **Intrastat**, w skróconej karcie **Raportowanie elektroniczne** w polu **Mapowanie formatu pliku** wybierz **Intrastat INTRACOM (FR)** lub **Intrastat SAISUNIC (FR)**.
    2. W polu **Mapowanie formatu raportów** wybierz wartość **Raport Intrastat**.
    3. Na skróconej karcie **hierarchii kodów asortymentu** w polu **Hierarchia kategorii** wybierz pozycję **Intrastat**.
    4. Na skróconej karcie **Ogólne** w polu **Kod transakcji** wybierz kod używany do przeniesienia towarów.
    5. W polu **Nota kredytowa** wybierz kod używany do zwrotów towarów.
    6. W polu **Poziom zobowiązania dla eksportu** wprowadź poziom szczegółowości raportu o eksporcie. Wybierany poziom wpływa na wiersze wyświetlane w raporcie. Aby uzyskać więcej informacji, zobacz tabele na początku tego artykułu.

3. Przejdź do **Administrowanie organizacją** > **Organizacje** > **Firmy**, wybierz swoją firmę, a następnie wykonaj następujące kroki:

    1. Na skróconej karcie **Numery rejestracji** w polu **Kod NAF** wprowadź kod NAF. Aby uzyskać więcej informacji, zobacz [FR-00003 kody NAF i numery Siret](tasks/fr-00003-naf-codes-siret-numbers.md).
    2. Na skróconej karcie **Handel zagraniczny i logistyka**, w sekcji **Intrastat** ustaw pola **numeru identyfikacji podatkowej VAT** i **Import numerów zwolnionych z VAT**.
    3. Na skróconej karcie **Rejestracja podatkowa** w polu **Numer identyfikacji podatkowej** wpisz numer identyfikacji podatkowej swojej firmy.

4. Aby określić kody NAF i numery identyfikacji podatkowej dla odbiorców, przejdź do **Rozrachunki z odbiorcami** > **Odbiorcy** > **Wszyscy odbiorcy** i wykonaj następujące czynności:

    1. Wybierz klienta.
    2. Na skróconej karcie **Faktura i dostawa**, w sekcji **Podatek**, w polu **Numer identyfikacji podatkowej** wprowadź numer identyfikacji podatkowej odbiorcy.
    3. Na skróconej karcie **Dane demograficzne** dotyczące sprzedaży w polu **Siret francuski** wprowadź numer Siret firmy.
    4. W polu **Kod NAF** wpisz kod NAF firmy.
    5. Powtórz te kroki dla innych odbiorców.

5. Aby określić kody NAF i numery identyfikacji podatkowej dla dostawców, przejdź do **Rozrachunki z dostawcami** > **Dostawcy** > **Wszyscy dostawcy** i wykonaj następujące czynności:

    1. Wybierz dostawcę.
    2. Na skróconej karcie **Faktura i dostawa**, w sekcji **Podatek**, w polu **Numer identyfikacji podatkowej** wprowadź numer identyfikacji podatkowej dostawcy.
    3. Na skróconej karcie **Demografia zakupów** dotyczące sprzedaży w polu **Siret francuski** wprowadź numer Siret firmy.
    4. W polu **Kod NAF** wpisz kod NAF firmy.
    5. Powtórz te kroki dla innych dostawców.

6. Przejdź do **Podatek** > **Ustawienia** > **Handel zagraniczny** > **Kompresja Intrastat** i wybierz pola, które należy porównać, gdy informacje Intrastat podsumowano. Dla francuskiego Intrastat wybierz opcję **Procedura statystyczna**, **Województwo pochodzenia**, **Kraj/region pochodzenia**, **Warunki dostawy**, **Transport**, **Korekta**, **Kraj/region**, **Powiat pochodzenia/docelowy**, **Kierunek**, **Kraj/region nadawcy**, **Województwo nadawcy**, **Województwo**, **Kod transakcji** i **Asortyment**.

7. Przejdź do **Zarządzanie magazynem** > **Ustawienia** > **Magazyn** > **Magazyny**, wybierz magazyn, a następnie wykonaj następujące czynności:

    1. Na skróconej karcie **Adresy** wybierz **Dodaj** lub **Edytuj**.
    2. W oknie dialogowym w polu **Miasto** wybierz miasto magazynu. Stan miasta będzie używany jako hrabstwo w raporcie DEB.

### <a name="ngp-codes"></a>Kody NGP

W raporcie DEB kodowanie produktów składa się z następujących elementów:

  - Ośmiu cyfrowy kod CN8, który reprezentuje nazewnictwo taryf i statystyk UE.
  - Jeśli ma zastosowanie, jednocyfrowy kod towaru Nazewnictwo Générale des Pénérale des Pénérale (NGP).

W roku 2021, NGP dotyczy tylko trzech typów produktów:

  - Niektóre produkty z krów, owiec i kóz
  - Sprzęt wojskowy
  - Wina francuskie

 Musisz skonfigurować kody NGP i przypisać je do powiązanych produktów. Pole **NGP** zostanie automatycznie ustawione na stronie **arkusza Intrastat**.

#### <a name="set-up-an-ngp-code"></a>Konfigurowanie kodu NGP

1. Wybierz kolejno opcje **Podatek** > **Ustawienia** > **Handel zagraniczny** > **Kody NGP**.
2. W okienku akcji wybierz opcję **Nowe**, aby utworzyć kod NGP.
3. W **polu NGP** wprowadź kod jednocyfrowy.
4. W polu **Opis** wprowadź opis kodu.

#### <a name="assign-an-ngp-code-to-a-product"></a>Przypisz kod NGP do produktu

1. Przejdź do **Zarządzanie informacjami o produktach** > **Produkty** > **Zwolnione produkty**.
2. Wybierz produkt w siatce.
3. Na skróconej karcie **Handel zagraniczny**, w sekcji **Intrastat**, w polu **NGP** wybierz odpowiedni kod NGP.

## <a name="intrastat-journal"></a>Arkusz Intrastat

Przejdź do **Podatek** > **Deklaracje** > **Zagraniczny** **handel** > **Intrastat**, aby zarządzać swoimi transakcjami, które dotyczą zagranicznych handel z krajami UE. Aby uzyskać więcej informacji, zobacz [Omowienie Intrastat](emea-intrastat.md).

Kolumna **NGP** jest specyficzna dla Francji. Pokazuje kod NGP produktu. Jeśli NGP nie ma zastosowania do produktu, **jest wyświetlana wartość 0** (zero). Możesz dostosować kod NGP. Wybierz transakcję, a następnie, na karcie **Ogólne**, w sekcji **Kody**, w polu **NGP** wybierz wymagany kod NGP.

### <a name="intrastat-transfer"></a>Przeniesienie do Intrastat

Na stronie **Intrastat** w okienku akcji możesz wybrać **Transfer**, aby automatycznie przesyłać informacje o handlu wewnątrzwspólnotowym z zamówień sprzedaży, faktur niezależnych, zamówień zakupu, faktur od dostawców, pokwitowań produktów od dostawców , faktury projektowe i zlecenia przeniesienia. Przekazywane będą tylko dokumenty, w których krajem lub regionem przeznaczenia jest kraj UE (w przypadku wysyłek) lub przesyłka (w przypadku przywozów).

Ponieważ raport DEB jest połączeniem listy sprzedaży do UE i raportu Intrastat, obejmuje on również transakcje *trójkątne*, w których dostawa bezpośrednia jest realizowana z jednego kraju UE (strona A) do innego kraju UE (strona C) oraz francuska osoba prawna (strona B) znajduje się w środku trójstronnej umowy.

### <a name="generate-a-deb-intrastat-report"></a>Wygeneruj raport DEB (Intrastat)

1. Wybierz kolejno opcje **Podatek** > **Deklaracje** > **Handel zagraniczny** > **Intrastat**.
2. W okienku akcji wybierz pozycję **Dane wyjściowe** > **Raport**.
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

## <a name="example"></a>Przykład

W poniższym przykładzie pokazano, jak skonfigurować francuski raport Intrastat i utworzyć raport DEB. Użyj firmy **DEMF**.

1. W [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) w bibliotece zasobów udostępnionych pobierz najnowsze wersje następujących konfiguracji raportowania elektronicznego (ER) dla formatu deklaracji Intrastat:

    - Model Intrastat
    - Raport Intrastat
    - Intrastat INTRACOM (Francja)

2. W Finance należy skonfigurować kod transakcji:

    1. Wybierz kolejno opcje **Podatek** > **Ustawienia** > **Handel zagraniczny** > **Kody transakcji**.
    2. W okienku akcji wybierz opcję **Nowy**.
    3. W polu **Kod transakcji** wpisz **11**.
    4. W polu **Nazwa** wpisz **Zakup lub sprzedaż**.
    5. Na okienku akcji wybierz opcję **Zapisz**.

3.  Skonfiguruj hierarchię produktów w sieci sprzedaży:

    1. Wybierz kolejno opcje **Zarządzanie informacjami o produktach** > **Ustawienia** > **Kategorie i atrybuty** > **Hierarchie kategorii**.
    2. W siatce zaznacz element **Intrastat**. W okienku akcji na karcie **Hierarchia kategorii** w grupie **Obsługa** wybierz opcję **Edytuj**.
    3. W okienku akcji kliknij pozycję **Nowy węzeł kategorii**.
    4. W polu **Nazwa** wpisz **Autres Libournais**.
    5. W polu **Kod** wpisz **2204 21 42**
    6. Na okienku akcji wybierz opcję **Zapisz**.

4. Przejdź do **Podatek** > **Ustawienia** > **Handel zagraniczny** > **Parametry handlu zagranicznego** i wykonaj następujące kroki:

    1. Na karcie **Intrastat**, na skróconej karcie **Ogólne**, w polu **Kod transakcji** wybierz wartość **11**.
    2. Na **skróconej karcie Raportowanie elektroniczne** w polu **Mapowanie formatu pliku** wybierz pozycję **Intrastat INTRACOM (FR)**.
    3. W polu **Mapowanie formatu raportów** wybierz wartość **Raport Intrastat**.
    4. Na skróconej karcie **hierarchii kodów asortymentu** w polu **Hierarchia kategorii** wybierz pozycję **Intrastat**.

5. Konfigurowanie kodu NGP:

    1. Wybierz kolejno opcje **Podatek** > **Ustawienia** > **Handel zagraniczny** > **Kody NGP**.
    2. W okienku akcji wybierz opcję **Nowy**.
    3. W polu **NGP** wprowadź **8**.
    4. W polu **Nazwa opisu** wpisz **NGP 8**.
    5. Na okienku akcji wybierz opcję **Zapisz**.

6. Przypisz kod NGP do produktu:

    1. Przejdź do **Zarządzanie informacjami o produktach** > **Produkty** > **Zwolnione produkty**.
    2. W siatce zaznacz element **0001**.
    3. Na skróconej karcie **Handel zagraniczny** w polu **NGP** wybierz wartość **8**.
    4. W polu **Asortyment** wybierz **2204 21 42**.
    5. Na okienku akcji wybierz opcję **Zapisz**.

7. Utwórz zamówienie sprzedaży z nowym produktem:

    1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** > **Zamówienia** > **Wszystkie zamówienia sprzedaży**.
    2. W okienku akcji wybierz opcję **Nowy**.
    3. W oknie dialogowym **Utwórz** **zamówienie** **sprzedaży** w sekcji **Klient** w polu **Konto** **klienta** wybierz **100001**.
    4. W sekcji **Adres**, w polu **Adres dostawy** wybierz znak plus (**+**), aby utworzyć adres.
    5. W oknie dialogowym **Nowy adres** w polu **Nazwa opisu** wprowadź **Niemcy**.
    6. W polu **kraj/region** wybierz **DEU**.
    7. Kliknij przycisk **OK**.
    8. W **Tworzenie zamówienia sprzedaży** wybierz **OK**.
    9. W skróconej karcie **Wiersze zamówienia** **sprzedaży** w polu **Numer towaru** wybierz wartość **0001**.
    10. Na okienku akcji wybierz opcję **Zapisz**.
    11. W okienku akcji na karcie **Faktura** w grupie **Generuj** wybierz **Faktura**.
    12. W **oknie dialogowym Księgowanie faktury**, na skróconej karcie **Parametry** w sekcji **Parametr** w polu **Ilość** zaznacz opcję **Wszystko**. Następnie wybierz **OK**, aby zaksięgować fakturę.

8.  Tworzenie raportu DEB:

    1. Wybierz kolejno opcje **Podatek** > **Deklaracje** > **Handel zagraniczny** > **Intrastat**:
    2. W okienku akcji. wybierz **Przeniesienie**.
    3. W oknie dialogowym **Intrastat (Przeniesienie)** w sekcji **Parametry** ustaw opcję **Faktura dla odbiorcy** na **wartość Tak**. Następnie wybierz opcję **OK**.
    4. Sortuj transakcje według **pola Data**. Najwyższa transakcja to transakcja wynikowa. Pole **NGP** jest ustawiane automatycznie.
    5. W okienku akcji wybierz pozycję **Dane wyjściowe** &gt; **Raport**.
    6. W oknie dialogowym **Raport Intrastat**, na skróconej karcie **Parametry**, w sekcji **Data** wybierz miesiąc utworzonego zamówienia sprzedaży.
    7. W sekcji **Opcje eksportu** ustaw wartość **Tak** dla opcji **Generuj plik**.
    8. W polu **Nazwa pliku** wprowadź wymaganą nazwę.
    9. Wybierz **przycisk OK** i przejrzyj raport.

