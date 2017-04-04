---
title: Raporty arkuszy magazynowych
description: "Użycie magazynu można konfigurować raportów opartych na raportowanie elektroniczne, należy zdefiniować relacje między określonego raportu i typu arkusza."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventJournalName
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265144
ms.assetid: 0f07f62f-1053-46e9-b235-a7b38cbda409
ms.search.region: Estonia, Hungary, Latvia, Lithuania, Poland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: eed3398651612743958722814ec5594ec34e4e5e
ms.lasthandoff: 03/31/2017


---

# <a name="inventory-journal-reports"></a>Raporty arkuszy magazynowych

Użycie magazynu można konfigurować raportów opartych na raportowanie elektroniczne, należy zdefiniować relacje między określonego raportu i typu arkusza.

Aby zdefiniować relacje między określonego raportu i typu arkusza na **nazw arkuszy magazynowych** stronę (**Zarządzanie zapasami**&gt;**instalacji**&gt;**nazwy arkuszy**&gt;**zapasów**), wprowadź nazwę dla raportu. **Uwaga:** do ustawiania konfiguracji obsługiwanych, Pobierz konfiguracji wymagane raportowania elektronicznego. Aby uzyskać więcej informacji, zobacz [pobrać elektroniczne raportowanie konfiguracje z cyklem życia usług](/dynamics365/operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs). Przykłady raportów zapasów z obsługiwanych konfiguracji w Europie są wymienione w poniższej tabeli.
|                    |                                     |                  |                                         |
|--------------------|-------------------------------------|------------------|-----------------------------------------|
| **Country**        | **Opis raportu**              | **Journal type** | **Nazwa mapowania format**                 |
| Litwa, Węgry | Raport zestawienie zapasów          | Zliczanie         | Zestawienie magazynowe (HU, LT)            |
| Łotwa, Polska     | Dokument przeklasyfikowania zapasów | Przenoszenie         | InventoryReclassificationDocument\_PLLV |
| Estonia            | Dokument przeklasyfikowania zapasów | Przenoszenie         | InventoryReclassificationDocument\_EE   |
| Polska             | Wewnętrzne PW/RW                      | Transakcje         | InventJournalLinesDocPL                 |
| Łotwa             |  Dokument przesunięcia magazynowego         | Transakcje         | Ruch\_LV                            |
| Łotwa             | Dokument zmniejszenia wartości zapasów       | Korekta       | InventJournalLines\_LV                  |
| Łotwa             | Przenieś dokument dostawy              | Przenoszenie         | InternalTransferDeliveryNote\_LV        |
| Łotwa             | Raport dokument inwentaryzacji            | Zliczanie         | CountedDocument\_LV                     |
| Łotwa             | Raport arkusza inwentaryzacyjnego                | Zliczanie         | Arkusz inwentaryzacyjny                           |




