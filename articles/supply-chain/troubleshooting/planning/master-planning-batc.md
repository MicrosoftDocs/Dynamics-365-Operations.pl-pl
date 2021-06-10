---
title: Nie można filtrować pozycji planowania głównego według powiązanych z nimi wartości grup zapotrzebowania
description: Nie można filtrować pozycji planowania głównego według powiązanych z nimi wartości grup zapotrzebowania.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: fa0b614b6710c65811add8725a0e255ce2c34b88
ms.sourcegitcommit: 3c15a26e9708adc9a75082dc551f0a3a0a7d89f4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049485"
---
# <a name="you-cant-filter-master-planning-items-by-their-related-coverage-group-values"></a>Nie można filtrować pozycji planowania głównego według powiązanych z nimi wartości grup zapotrzebowania

Numer artykułu z bazy wiedzy: 4612572

## <a name="symptoms"></a>Objawy

Chcesz wyfiltrować pozycje, które zostaną uwzględnione w zadaniu wsadowym planowania głównego, na podstawie wartości powiązanych rekordów z tabeli pokrycia pozycji. (Na przykład chcesz filtrować towary według ich **Dostawcy** i/lub wartość **Grupy zapotrzebowania**). Konfiguracja filtra dla zadania wsadowego pozwala na utworzenie złączenia z tabeli **Elementy** do tabeli **Zapotrzebowanie na towar**, a następnie określenie wartości pól z tabeli zapotrzebowania elementów w zapytaniu. Jednak po zakończeniu tej konfiguracji system nadal tworzy planowane zlecenia dla całego zakresu pozycji, a nie tylko dla pozycji, które pasują do określonych wartości pól z tabeli zakresu pozycji.

## <a name="resolution"></a>Rozwiązanie

Filtr zadań wsadowych może filtrować tylko elementy. Mimo że można dodać połączenia do tabeli **Zapotrzebowanie na towar**, ustawienia filtru względem tej tabeli nie wpływają na wynik kwerendy. W czasie pracy system przeprowadza planowanie dla wszystkich grup zapotrzebowania i wszystkich wariantów, które mają odfiltrowane elementy. Po włączeniu produktu do badania, wszelkie grupy pokrycia, które są zawarte w filtrze elementu, nie będą miały wpływu na wynik planowania.
