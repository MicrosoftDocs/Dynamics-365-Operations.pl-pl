---
title: Omówienie planowania optymalizacji
description: Ten temat zawiera omówienie funkcji sprzedaży przez biuro obsługi w optymalizacji planowania.
author: ChristianRytt
manager: tfehr
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 110045d4c7e4f32c29b73096dd4df3a09b5434ac
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435004"
---
# <a name="planning-optimization-overview"></a>Omówienie planowania optymalizacji

[!include [banner](../../includes/banner.md)]

Dodatek do optymalizacji planowania dla rozwiązania Microsoft Dynamics 365 Supply Chain Management umożliwia naliczenie planowania głównego poza Dynamics 365 Supply Chain Management i pokrewną bazą danych SQL. Korzyści związane z funkcjami optymalizacji planowania obejmują lepszą wydajność i minimalny wpływ na bazę danych SQL podczas uruchamiania planowania głównego. Szybkie przebiegi planowania można wykonać nawet w godzinach pracy, dzięki czemu terminarze mogą natychmiast reagować na zmiany popytu lub parametrów.

Aby skorzystać z optymalizacji planowania, należy zainstalować dodatek Optymalizacja planowania z projektu w Microsoft Dynamics usługach Lifecycle Services (usługi LCS) i włączyć funkcję optymalizacji planowania w module Supply Chain Management. Aby uzyskać więcej informacji, zobacz [Rozpocznij pracę z optymalizacją planowania](get-started.md).

Na poniższej ilustracji przedstawiono zalety uruchamiania optymalizacji planowania w godzinach pracy.

![Zalety uruchomienia optymalizacji planowania w godzinach pracy](media/PlanningOptimization1.png)

## <a name="improved-performance"></a>Zwiększona wydajność

Optymalizacja planowania może być używana w scenariuszach obejmujących długotrwałe plany główne. Jest on opracowany z myślą o bardzo szybkich obliczeniach dotyczących bardzo dużych ilości danych. Ponieważ jest on zbudowany jako usługa wielodostępna funkcji Hyper-i ma skalowalność, wiele wystąpień może równocześnie pracować w celu obliczenia planu. Ponadto usługa planowania usuwa ładunek planowania głównego z systemu i pracuje ze strumieniem danych, który minimalizuje obciążenie serwera.

Optymalizacja planowania może pomóc w osiągnięciu następujących celów:

- Zwiększanie wydajności planowania za pomocą krótszego środowiska uruchomieniowego.
- Zmniejszenie wpływu na inne procesy w trakcie procesu planowania głównego
- Należy wykonać częstsze procedury planowania. (Nie ma ograniczeń do codziennego uruchamiania.)
- Należy mieć pewność, że przyszły rozwój rynku nie spowoduje przeciążenia systemu planowania.

## <a name="architecture-and-data-flow"></a>Architektura i przepływ danych

Jeśli dodatek Optymalizacja planowania jest zainstalowany z usługi LCS, ustanawiane jest bezpieczne połączenie z usługą optymalizacji planowania. Usługa znajduje się w tym samym kraju lub regionie centrum danych, co wystąpienie Supply Chain Management. Po skonfigurowaniu optymalizacji planowania, po uruchomieniu modułu planowanie główne, dane główne i dane transakcyjne są wysyłane z modułu Supply Chain Management do usługi optymalizacji planowania.

Jeśli dodatek Optymalizacja planowania nie zostanie odinstalowany, wszystkie powiązane dane w usłudze optymalizacji planowania są usuwane.

### <a name="high-level-data-flow-for-regeneration-runs"></a>Przepływ danych wysokiego poziomu dla przebiegów regeneracji

1. Klient Supply Chain Management wysyła sygnał zażądania uruchomienia planowania z optymalizacji planowania.
2. Optymalizacja planowania żąda wymaganych danych za pośrednictwem zintegrowanego łącznika.
3. Baza danych SQL wysyła żądane informacje o konfiguracji, wzorcu i danych transakcyjnych w celu planowania optymalizacji za pośrednictwem łącznika. Łącznik przetwarza informacje pomiędzy Supply Chain Management i usługa optymalizacji planowania.
4. Usługa optymalizacji planowania zawiera dane związane z planowaniem w pamięci i wykonuje wymagane obliczenia.
5. Wyniki planowania są wysyłane do bazy danych Supply Chain Management za pośrednictwem łącznika. Wyniki zawierają informacje, takie jak planowane zamówienia i informacje dotyczące oznaczania transakcji. Optymalizacja planowania wysyła sygnał do modułu Supply Chain Management w celu wskazania, że przebieg planowania został zakończony. Wysyła również odpowiednie komunikaty i ostrzeżenia.

Ilustracja poniżej przedstawia przepływ danych.

![Przepływ danych dla przebiegów regeneracji](media/PlanningOptimization2.png)

## <a name="related-resources"></a>Powiązane zasoby

[Rozpocznij pracę z optymalizacją planowania](get-started.md)

[Analiza dopasowywania optymalizacją planowania](planning-optimization-fit-analysis.md)

[Wyświetlanie dzienników historii i planowania planów](plan-history-logs.md)

[Stosowanie filtrów do planu](plan-filters.md)

[Anuluj planowanie pracy](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]