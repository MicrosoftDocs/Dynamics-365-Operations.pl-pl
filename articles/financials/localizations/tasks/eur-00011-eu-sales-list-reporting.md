---
title: EUR-00011 Konfigurowanie unijnego raportu listy sprzedaży
description: To zadanie prowadzi przez omówienie warunków wstępnych wymaganych na potrzeby raportowania listy sprzedaży do UE.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionRepositoryTable, ERSolutionImport, SysQueryForm, SysQueryFieldLookUp,  TaxTable, TaxGroup, TaxItemGroup, TaxCountryRegionParameters, TaxVATNumTable, IntrastatParameters, CustTable, DirPartyQuickCreateForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee87abdc276d80123bbbe44a67c667bb0df9acb6
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1538227"
---
# <a name="eur-00011-set-up-eu-sales-list-reporting"></a>EUR-00011 Konfigurowanie unijnego raportu listy sprzedaży

[!include [task guide banner](../../includes/task-guide-banner.md)]

To zadanie prowadzi przez omówienie warunków wstępnych wymaganych na potrzeby raportowania listy sprzedaży do UE. Aby uzyskać więcej informacji na temat raportowania list sprzedaży do UE, w tym o wymaganiach wstępnych, zobacz Pomoc programu Dynamics 365 for Finance and Operations.

To zadanie dotyczy wszystkich krajów/regionów Europy. Przewodnik został utworzony przy użyciu danych firmy demonstracyjnej DEMF i w związku z tym Niemiec jako przykładowego lokalnego kraju/regionu. W przewodniku jest również używana Portugalia jako przykładowy kraj/region UE.

Te zadania są przeznaczone dla administratorów systemu.


## <a name="import-electronic-reporting-configurations-for-eu-sales-list-reporting"></a>Importowanie konfiguracji raportowania elektronicznego na potrzeby raportowania listy sprzedaży do UE
1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
2. Kliknij opcję Ustaw jako aktywny.
3. Kliknij Repozytoria.
4. Kliknij przycisk Otwórz.
5. W okienku akcji kliknij pozycję Opcje.
6. Kliknij opcję Filtr/sortowanie zaawansowane.
7. Kliknij przycisk Dodaj.
8. W polu Pole wybierz opcję „Nazwa konfiguracji”.
9. W polu Kryteria wpisz „Lista sprzedaży do UE (DE)”.
10. Kliknij przycisk OK.
11. Kliknij przycisk Importuj.
12. Kliknij przycisk Tak.
13. W okienku akcji kliknij pozycję Opcje.
14. Kliknij opcję Filtr/sortowanie zaawansowane.
15. Kliknij pozycję Resetuj.
16. Kliknij przycisk Dodaj.
17. W polu Pole wybierz opcję „Nazwa konfiguracji”.
18. W polu Kryteria wpisz „Raport o liście sprzedaży do UE z podziałem na wiersze”.
19. Kliknij przycisk OK.
20. Kliknij przycisk Importuj.
21. Kliknij przycisk Tak.

## <a name="set-up-sales-tax-codes-for-eu-sales-list-reporting"></a>Konfigurowanie kodów podatków na potrzeby raportowania listy sprzedaży do UE
1. Wybierz kolejno opcje Podatek > Podatki pośrednie > Podatek > Kody podatków.
2. Użyj szybkiego filtru, aby wyfiltrować pole Kod podatku według wartości „VAT19”.
3. Rozwiń sekcję Konfiguracja raportu.
    * Upewnij się, że opcja Wykluczone ma ustawioną wartość Nie.  
    * W celu zmiany tego ustawienia może być konieczne odblokowanie zadań w przewodniku.  

## <a name="set-up-sales-tax-groups-for-eu-sales-list-reporting"></a>Konfigurowanie grup podatków na potrzeby raportowania listy sprzedaży do UE
1. Wybierz kolejno opcje Podatek > Podatki pośrednie > Podatek > Grupy podatków.
2. Użyj szybkiego filtru, aby wyfiltrować pole Grupa podatków według wartości „AR-DOM”.
3. Kliknij przycisk Edytuj.
4. Rozwiń sekcję Ustawienia.
5. Na liście zaznacz pierwszy wiersz.
6. Zaznacz pole wyboru Zwolnienie.
7. Na liście zaznacz drugi wiersz.
8. Zaznacz pole wyboru Zwolnienie.
9. Na liście zaznacz trzeci wiersz.
10. Zaznacz pole wyboru Zwolnienie.

## <a name="set-up-item-sales-tax-groups-for-eu-sales-list-reporting"></a>Konfigurowanie grup podatków dla towarów na potrzeby raportowania listy sprzedaży do UE
1. Wybierz kolejno opcje Podatek > Podatki pośrednie > Podatek > Grupy podatków dla towaru.
2. Użyj szybkiego filtru, aby wyfiltrować pole Grupa podatków dla towaru według wartości „PEŁNE”.
    * Upewnij się, że opcja Typ raportowania ma ustawioną wartość „Towar”.  
    * W celu zmiany wartości tego pola może być konieczne odblokowanie zadań w przewodniku.  
3. Użyj szybkiego filtru, aby wyfiltrować pole Grupa podatków dla towaru według wartości „CZERWONE”.
    * Upewnij się, że opcja Typ raportowania ma ustawioną wartość „Usługa”.  
    * W celu zmiany wartości tego pola może być konieczne odblokowanie zadań w przewodniku.  

## <a name="set-up-countryregion-parameters-for-eu-sales-list-reporting"></a>Konfigurowanie parametrów kraju/regionu na potrzeby raportowania listy sprzedaży do UE
1. Wybierz kolejno opcje Podatek > Ustawienia > Podatek > Parametry kraju/regionu.
2. Kliknij przycisk Nowy.
3. W polu Kraj/region wpisz „PRT”.
4. W polu Podatek wpisz „PT”.

## <a name="create-tax-exempt-numbers"></a>Tworzenie numerów identyfikacji podatkowej
1. Wybierz kolejno opcje Podatek > Ustawienia > Podatek > Numery identyfikacji podatkowej.
2. Kliknij przycisk Nowy.
3. W polu Kraj/region wpisz „PRT”.
4. W polu Numer identyfikacji podatkowej wpisz „PT12345”.

## <a name="set-up-eu-sales-list-reporting-parameters"></a>Konfigurowanie parametrów raportowania listy sprzedaży do UE
1. Wybierz kolejno opcje Podatek > Ustawienia > Handel zagraniczny > Parametry handlu zagranicznego.
2. Kliknij kartę Lista sprzedaży do UE.
3. W polu Przenieś zakupy wybierz opcję Tak.
4. Rozwiń sekcję Reguły zaokrąglania.
5. W polu Reguła zaokrąglania wpisz „0,1”.
6. W polu Użyj wartości minimalnej zaznacz opcję Tak.
7. W polu Liczba cyfr dziesiętnych wpisz wartość „2”.
8. Rozwiń sekcję Raportowanie elektroniczne.
9. W polu Mapowanie formatu plików wybierz opcję „Lista sprzedaży do UE (DE)”.
10. W polu Mapowanie formatu raportów wybierz opcję „Raport o liście sprzedaży do UE z podziałem na wiersze”.
11. Kliknij kartę Właściwości kraju/regionu.
    * Upewnij się, że dla kraju/regionu DEU pole Typ kraju/regionu ma ustawioną wartość „Krajowy”.  
    * W celu zmiany wartości tego pola może być konieczne odblokowanie zadań w przewodniku.  
12. Kliknij przycisk Nowy.
13. W polu Kraj/region wpisz „PRT”.
14. W polu Kod Intrastat wpisz „PT”.
15. W polu Typ kraju/regionu wybierz opcję „UE”.
16. Kliknij kartę Sekwencje numerów.
    * Upewnij się, że kod sekwencji numerów jest określony dla odwołania „Lista sprzedaży do UE”.  

## <a name="create-a-customer-for-eu-sales-list-reporting-demo-purposes"></a>Tworzenie odbiorcy do celów demonstracji raportowania listy sprzedaży do UE
1. Wybierz kolejno opcje Rozrachunki z odbiorcami > Odbiorcy > Wszyscy odbiorcy.
2. Kliknij przycisk Nowy.
3. W polu Konto odbiorcy wpisz „PRT-001”.
4. W polu Nazwa wpisz „Odbiorca z Portugalii”.
5. W polu Grupa odbiorców wybierz opcję „10”.
6. W polu Grupa podatków wybierz opcję „AR-DOM”.
7. W polu Numer identyfikacji podatkowej wybierz opcję „PT12345”.
8. W polu Kraj/region wpisz „PRT”.
9. Kliknij przycisk Zapisz.

