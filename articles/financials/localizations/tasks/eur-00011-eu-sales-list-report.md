---
title: EUR-00011 Generowanie raportu listy sprzedaży do UE
description: Ta procedura prowadzi przez proces generowania raportu o liście sprzedaży do UE.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  EUSalesList, EUSalesListSelection, SysQueryForm, SysLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9fcafa2beca5d998b2556ba73e9f3cc2bdd314ba
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "371523"
---
# <a name="eur-00011-generate-the-eu-sales-list-report"></a>EUR-00011 Generowanie raportu listy sprzedaży do UE

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura prowadzi przez proces generowania raportu o liście sprzedaży do UE. Obejmuje to przeniesienie wewnątrzwspólnotowych transakcji handlowych na listę sprzedaży do UE i wykonanie raportu. Elementem procedury jest także utworzenie wewnątrzwspólnotowego transakcji handlowej dla celów demonstracyjnych. Aby uzyskać więcej informacji na temat raportowania list sprzedaży do UE, w tym o wymaganiach wstępnych, zobacz Pomoc programu Dynamics 365 for Finance and Operations.

Ta procedura dotyczy wszystkich krajów/regionów Europy. Procedura została utworzona przy użyciu danych firmy demonstracyjnej DEMF i w związku z tym Niemiec jako przykładowego lokalnego kraju/regionu. W procedurze jest również używana Portugalia jako przykładowy kraj/region UE. Zanim będzie można wykonać tę procedurę, trzeba skonfigurować funkcję raportowania listy sprzedaży do UE.

Procedura jest przeznaczona dla księgowych.


## <a name="create-an-intra-community-sales-transaction-for-demo-purposes"></a>Tworzenie wewnątrzwspólnotowej transakcji sprzedaży dla celów demonstracyjnych
1. Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.
2. Kliknij przycisk Nowy.
3. W polu Konto odbiorcy wpisz „PRT-001”.
4. Kliknij przycisk OK.
5. W polu Numer pozycji wpisz „D0001”.
6. Rozwiń sekcję Szczegóły wiersza.
7. Kliknij kartę Ustawienia.
8. W polu Grupa podatków dla towaru wpisz wartość „PEŁNE”.
9. Kliknij przycisk Dodaj wiersz.
10. W polu Numer pozycji wpisz „D0003”.
11. W polu Grupa podatków dla towaru wpisz wartość „CZERWONE”.
12. Kliknij przycisk Zapisz.
13. W okienku akcji kliknij pozycję Faktura.
14. Kliknij opcję Faktura.
15. Rozwiń sekcję Parametry.
16. W polu Ilość zaznacz opcję Wszystko.
17. Rozwiń sekcję Ustawienia.
18. W polu Data faktury ustaw datę „01/11/2016”.
19. Kliknij przycisk OK.
20. Kliknij przycisk OK.

## <a name="transfer-intra-community-trade-transactions-to-the-eu-sales-list"></a>Przenoszenie wewnątrzwspólnotowych transakcji handlowych na listę sprzedaży do UE
1. Wybierz kolejno opcje Podatek > Deklaracje > Handel zagraniczny > Lista sprzedaży do UE.
2. Kliknij przycisk Przeniesienie.
3. W polu Towar wybierz opcję Tak, aby przenieść transakcje dotyczące towaru.
4. W polu Usługa wybierz opcję Tak, aby przenieść transakcje dotyczące usług.
    * Można również określić dodatkowe filtry dla wewnątrzwspólnotowych transakcji handlowych w celu ich przeniesienia.  
5. Kliknij przycisk Przeniesienie.
    * Sprawdź, czy wewnątrzwspólnotowa transakcja sprzedaży została pomyślnie przeniesiona na listę sprzedaży do UE.  

## <a name="generate-the-eu-sales-list-report"></a>Generowanie raportu listy sprzedaży do UE
1. Kliknij opcję Raportowanie.
2. W polu Okres raportowania wybierz opcję „Miesięcznie”.
3. W polu Od dnia ustaw wartość daty równą „01/01/2016”.
4. W polu Generuj plik zaznacz opcję Tak.
5. W polu Generuj raport zaznacz opcję Tak.
6. W polu Nazwa pliku wpisz „EUSalesList”.
7. W polu Nazwa pliku raportu wpisz „EUSalesList”.
8. W polu Identyfikator rejestracji listy sprzedaży do UE wpisz „123”.
    * To pole jest dostępne jedynie dla Niemiec.  
    * Można również określić dodatkowe filtry dla wewnątrzwspólnotowych transakcji handlowych w celu ich umieszczenia w raporcie.  
9. Kliknij przycisk OK.
    * Sprawdź, czy pojawia się wyskakujące okienko z potwierdzeniem, że plik i raport kontrolny są pobierane.  

## <a name="mark-eu-sales-list-lines-as-reported"></a>Oznaczanie wierszy listy sprzedaży do UE jako zgłoszonych
1. Kliknij opcję Zaznacz.
2. Kliknij opcję Zaznacz jako zgłoszony.
3. Na liście zaznacz wiersz z polem Data faktury.
4. W polu Kryteria wpisz „01/01/2016..01/31/2016”.
5. Na liście zaznacz wiersz z polem Stan raportowania.
6. W polu Kryteria wybierz opcję „Uwzględnione”.
    * Można również określić dodatkowe filtry dla wewnątrzwspólnotowych transakcji handlowych w celu ich oznaczenia jako Raportowany.  
7. Kliknij przycisk OK.
8. W polu Wybór wybierz opcję „Raportowany”.

## <a name="mark-eu-sales-list-lines-as-closed"></a>Oznaczanie wierszy listy sprzedaży do UE jako zamkniętych
1. Kliknij opcję Zaznacz.
2. Kliknij opcję Zaznacz jako zamknięty.
3. Na liście zaznacz wiersz z polem Data faktury.
4. W polu Kryteria wpisz „01/01/2016..01/31/2016”.
5. Na liście zaznacz wiersz z polem Stan raportowania.
6. W polu Kryteria wybierz opcję „Raportowany”.
    * Można również określić dodatkowe filtry dla wewnątrzwspólnotowych transakcji handlowych w celu ich oznaczenia jako Zamknięte.  
7. Kliknij przycisk OK.
8. W polu Wybór wybierz opcję „Zamknięte”.

