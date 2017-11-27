---
title: Raporty arkuszy magazynowych
description: "Jeśli używasz konfigurowalnych raportów o zapasach opartych na raportowaniu elektronicznym, należy zdefiniować relacje między określonymi raportami a typami arkuszy."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalName
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 265144
ms.search.region: Estonia, Hungary, Latvia, Lithuania, Poland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ca43a81ab3e1dfcfec6a69369121265c54dae9a8
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="inventory-journal-reports"></a>Raporty arkuszy magazynowych

[!include[banner](../includes/banner.md)]


Jeśli używasz konfigurowalnych raportów o zapasach opartych na raportowaniu elektronicznym, należy zdefiniować relacje między określonymi raportami a typami arkuszy.

Aby skonfigurować relację między określonym raportem a typem arkusza, na stronie **Nazwy arkuszy magazynowych** (**Zarządzanie zapasami** &gt; **Ustawienia** &gt; **Nazwy arkuszy** &gt; **Zapasy**) nadaj raportowi nazwę. **Uwaga:** Aby utworzyć obsługiwane konfiguracje, pobierz wymagane konfiguracje raportowania elektronicznego. Aby uzyskać więcej informacji, zobacz [Pobieranie konfiguracji modułu Raportowanie elektroniczne z usługi Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md). Przykłady raportów o zapasów z obsługiwanymi konfiguracjami w Europie są wymienione w tabeli poniżej.
|                    |                                     |                  |                                         |
|--------------------|-------------------------------------|------------------|-----------------------------------------|
| **Kraj**        | **Opis raportu**              | **Typ arkusza** | **Nazwa mapowania formatu**                 |
| Litwa, Węgry | Raport zestawienia zapasów          | Zliczanie         | Zestawienie zapasów (Węgry, Litwa)            |
| Łotwa, Polska     | Dokument przeklasyfikowania zapasów | Przenoszenie         | InventoryReclassificationDocument\_PLLV |
| Estonia            | Dokument przeklasyfikowania zapasów | Przenoszenie         | InventoryReclassificationDocument\_EE   |
| Polska             | Wewnętrzne PW/RW                      | Transakcje         | InventJournalLinesDocPL                 |
| Łotwa             |  Dokument przesunięcia magazynowego         | Transakcje         | Movement\_LV                            |
| Łotwa             | Dokument zmniejszenia wartości zapasów       | Korekta       | InventJournalLines\_LV                  |
| Łotwa             | Przenieś dokument dostawy              | Przenoszenie         | InternalTransferDeliveryNote\_LV        |
| Łotwa             | Raport dokumentu inwentaryzacji            | Zliczanie         | CountedDocument\_LV                     |
| Łotwa             | Raport arkusza inwentaryzacyjnego                | Zliczanie         | Arkusz inwentaryzacyjny                           |






