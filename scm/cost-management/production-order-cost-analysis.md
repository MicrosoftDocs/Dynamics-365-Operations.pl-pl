---
title: "Analiza kosztów zlecenia produkcyjnego"
description: "Ten artykuł zawiera informacje o analizach kosztów, jakie można wykonywać na zakończonych i bieżących zleceniach produkcyjnych. Koszty szacowane i rzeczywiste można analizować na stronie Obliczanie ceny lub w raporcie Szacowanie kosztów i wycena. Można oglądać informacje o szacowanych i rzeczywistych kosztach (oraz ilościach) dla każdego składnika, operacji marszruty i kosztu pośredniego."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventCostTrans, ProdCalcTrans, ProdTableJour, ProdTableListPage
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 79634
ms.assetid: ded5da04-f787-49f7-b5e5-75c2a2b92930
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 1905749fa8db33b960d082d1e22f11206b400eb0
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="production-order-cost-analysis"></a>Analiza kosztów zlecenia produkcyjnego

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera informacje o analizach kosztów, jakie można wykonywać na zakończonych i bieżących zleceniach produkcyjnych. Koszty szacowane i rzeczywiste można analizować na stronie Obliczanie ceny lub w raporcie Szacowanie kosztów i wycena. Można oglądać informacje o szacowanych i rzeczywistych kosztach (oraz ilościach) dla każdego składnika, operacji marszruty i kosztu pośredniego.

Koszty rzeczywiste zlecenia produkcyjnego są obliczane na podstawie zgłoszonego zużycia materiałów i operacji marszruty. Szczegółowe dane transakcji dotyczących zgłoszonego zużycia materiałów, operacji marszruty i kosztów pośrednich zlecenia produkcyjnego są wyświetlane na stronie **Księgowanie produkcji**.

## <a name="variance-analysis-for-a-completed-production-order"></a>Analiza odchyleń zakończonego zlecenia produkcyjnego
Odchylenia odzwierciedlają wynik porównania zgłoszonych działań produkcyjnych z obliczonym kosztem standardowym towaru produkcyjnego. Nie odzwierciedlają one wyników porównania z szacowanymi kosztami zlecenia produkcyjnego. Zgłaszane działania produkcyjne obejmują zużycie materiału i operacje marszruty (razem z powiązanymi kosztami pośrednimi) oraz ilość zgłoszoną jako gotową. Obliczane są następujące cztery typy odchyleń:

-   Odchylenie rozmiaru partii
-   Odchylenie ilości produkcji
-   Rozbieżność cen produkcji
-   Odchylenie podstawiania produkcji

Poniższy diagram przedstawia cztery odchylenia, które składają się na różnicę między kosztami rzeczywistymi zlecenia produkcyjnego a kosztami obliczonymi w rekordzie kosztu towaru po zakończeniu zlecenia produkcyjnego. 

![Odchylenia odzwierciedlające różnice w zakończonym zleceniu produkcyjnym](./media/control.jpg) 

Odchylenia produkcji można analizować za pomocą strony **Odchylenie** lub raportu **Odchylenia produkcji**. Korzystając z odpowiednich opcji wyświetlania, można przeglądać szczegóły odchyleń według towarów, zasobów operacyjnych lub grup kosztów. Zasady podziału kosztów określone w parametrach zapasów decydują o tym, czy odchylenia są śledzone według grup kosztów. Można także używać opcji wyświetlania **jeden**, **wiele** i **suma**, aby obejrzeć zbiorcze odchylenia. Szczegóły odchyleń pomagają poznać źródło każdego odchylenia. Aby przewidzieć odchylenia przed zakończeniem zlecenia produkcyjnego, należy przeanalizować szczegółowe informacje zawarte w raporcie **Szacowanie kosztów i wycena**.

## <a name="cost-analysis-for-current-production-orders"></a>Analiza kosztów bieżących zleceń produkcyjnych
Oddzielne raporty zapewniają informację o każdym typie transakcji. Raporty te służą do analizowania kosztów zgłoszonych działań produkcyjnych. Informacje są wyświetlane tylko dla bieżących zleceń produkcyjnych o stanie **Rozpoczęte** lub **Zgłoszone jako gotowe**.

-   **Materiały w toku** — Ten raport zawiera listę transakcji pobrania zgłoszonych dla bieżących zleceń produkcyjnych do określonego dnia transakcji. Raport wskazuje ilość wydanego składnika oraz kwotę kosztu dla każdej transakcji. Aby uzyskać informacje o jednym składniku, należy użyć kryteriów wyboru. Można na przykład wyświetlić informacje o ilości składnika wydanej dla odnośnych zleceń produkcyjnych. Wydana ilość nie jest aktualizowana przez ilości zgłoszone jako gotowe dla towaru nadrzędnego. W związku z tym rzeczywista ilość materiałów w toku może być zawyżona.
-   **Praca w toku** — Ten raport zawiera listę transakcji marszruty (lub transakcji zadań) zgłoszonych dla bieżących zleceń produkcyjnych do określonego dnia transakcji. Raport wskazuje godziny, kwotę i ilość (wyrobów dobrych i wadliwych) zgłoszone w każdej transakcji. Ponadto zawiera informacje takie jak numer operacji, identyfikator operacji i zasób operacyjny. W raporcie są również wyświetlane łączny czas i kwota dla wszystkich transakcji zlecenia produkcyjnego oraz ilość wyrobów zgłoszonych jako gotowe.
-   **Koszty pośrednie w procesie** — Ten raport wyświetla koszty pośrednie, które wystąpiły w zleceniach produkcyjnych. Te dane bazują na zgłoszonym zużyciu operacji marszruty i składników do określonego dnia transakcji. Raport wskazuje typ kosztu pośredniego (dopłata lub stawka), kod arkusza wyceny dla kosztu pośredniego i kwotę kosztu dla każdej transakcji. Raport nie dostarcza informacji o transakcji karty marszruty lub listy pobrania, która wygenerowała koszt pośredni.
-   **Wycena produkcji w toku** — Ten raport zawiera informacje o łącznym zużyciu materiału, operacjach marszruty i kosztach pośrednich zlecenia produkcyjnego do określonego dnia transakcji.
-   **Pozycje gotowe w toku** — Ten raport zawiera listę bieżących zleceń produkcyjnych oraz transakcji zgłoszenia wyrobów jako gotowe do określonego dnia transakcji.


<a name="see-also"></a>Informacje dodatkowe
--------

[Typowe przyczyny odchyleń produkcji](common-sources-of-production-variances.md)




