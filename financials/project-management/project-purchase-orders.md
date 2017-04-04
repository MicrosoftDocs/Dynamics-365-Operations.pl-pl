---
title: "Zamówienia zakupu dla projektu"
description: "W tym artykule opisano różne metody, których można używać do tworzenia zamówień zakupu dla projektu. Wybrana metoda zależy od przeznaczenia zamówienia zakupu oraz od czasu zużywania kupionych towarów i zapisywania ich w ciężar projektu."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 82305cfe38e7193cece3b9e7784fb81fd40f9c70
ms.lasthandoff: 03/31/2017


---

# <a name="purchase-orders-for-a-project"></a>Zamówienia zakupu dla projektu

W tym artykule opisano różne metody, których można używać do tworzenia zamówień zakupu dla projektu. Wybrana metoda zależy od przeznaczenia zamówienia zakupu oraz od czasu zużywania kupionych towarów i zapisywania ich w ciężar projektu.

W usłudze Microsoft Dynamics 365 dla operacji wiele metod można użyć do tworzenia zamówienia zakupu dla projektu. Wybrana metoda zależy od przeznaczenia zamówienia zakupu, czasu zużywania kupionych towarów i oraz momentu zapisania kupionych towarów w ciężar projektu.

### <a name="methods-for-creating-a-purchase-order"></a>Metody tworzenia zamówienia zakupu

Można użyć jednej z następujących metod w celu utworzenia zamówienia zakupu w module Zarządzanie projektami i ich księgowanie. Przeznaczenie zamówienia zakupu decyduje o tym, kiedy jest ono zużywane i w efekcie kiedy towary są zapisywane w ciężar projektu.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Metoda</th>
<th>Cel</th>
<th>Zużycie towarów</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Tworzenie zamówienia zakupu bezpośrednio z projektu</td>
<td>Użyj tej metody do zakupu towaru u zewnętrznego dostawcy w celu zużycia w projekcie. Zamówienie zakupu można utworzyć na dwa sposoby:
<ul>
<li>Z samego projektu. W tym przypadku projekt jest już zdefiniowany dla zamówienia zakupu.</li>
<li>Przechodząc do zamówienia zakupu projektu. Należy wybrać zarówno dostawcę, jak i projekt, dla których zostanie utworzone zamówienie zakupu.</li>
</ul></td>
<td>Towary są zużywane przy aktualizacji faktury dostawcy.</td>
</tr>
<tr class="even">
<td>Tworzenie zamówienia zakupu na podstawie zamówienia sprzedaży.</td>
<td>Ten metody należy używać do kupowania towarów w przypadku tworzenia zamówienia sprzedaży z projektu.</td>
<td>Towary są zużywane, gdy zamówienie sprzedaży jest fakturowane do odbiorcy.</td>
</tr>
<tr class="odd">
<td>Tworzenie zamówienia zakupu z zapotrzebowania na towar.</td>
<td>Tej metody należy używać do kupowania towarów w przypadku tworzenia zapotrzebowania na towar z projektu.</td>
<td>Towary są zużywane przy aktualizacji dokumentu dostawy dla zapotrzebowania na towar.</td>
</tr>
</tbody>
</table>

> [!NOTE] 
> Podczas aktualizacji faktury dostawcy lub dokumentu dostawy, zostaniesz poproszony o aktualizacji dokumentu dostawy na zapotrzebowania na towar.


