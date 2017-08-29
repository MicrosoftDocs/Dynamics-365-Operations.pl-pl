--- 
title: "Konfigurowanie urzędów skarbowych"
description: "Urzędy skarbowe to jednostki, do których należy zgłaszać i przekazywać zebrane podatki."
author: twheeloc
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: e0d8b87e23932ce843791778f65eb77240cc28f4
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-sales-tax-authorities"></a>Konfigurowanie urzędów skarbowych

[!include[task guide banner](../../includes/task-guide-banner.md)]

Urzędy skarbowe to jednostki, do których należy zgłaszać i przekazywać zebrane podatki. Można płacić podatki urzędowi skarbowemu bezpośrednio lub za pośrednictwem konta dostawcy, które należy utworzyć dla urzędu skarbowego. W takim przypadku firma może używać swoich zwykłych procedur płatności, aby płacić podatki na czas. Jeśli nie skonfigurujesz urzędu skarbowego jako dostawcy, ktoś musi przygotować ręczną płatność na rzecz urzędu skarbowego w odpowiednim terminie. W zadaniu wykorzystano firmę demonstracyjną USMF.

1. Wybierz kolejno opcje Podatek > Podatki pośrednie > Podatek > Urzędy skarbowe.
2. Kliknij przycisk Nowy.
3. W polu Organ wpisz wartość.
4. W polu Nazwa wpisz wartość.
5. W polu Konto dostawcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
6. Na liście znajdź i zaznacz odpowiedni rekord.
7. Na liście kliknij łącze w wybranym wierszu.
8. Wybierz układ raportu dla swojego kraju/regionu, jeśli taki układ jest dostępny. Jeśli układy raportów nie odpowiadają wymaganiom urzędu skarbowego, użyj domyślnego układu.
9. Wprowadź wartości w formularzu Zaokrąglanie i polach Zaokrąglenie, aby określić sposób zaokrąglania łącznej kwoty podatku do zapłaty. Wszelkie różnice zaokrąglania będą księgowana na kontach transakcji automatycznych skonfigurowanych w Księdze głównej.
10. W polu Zaokrąglenie wpisz liczbę.
11. Kliknij przycisk Zapisz.


