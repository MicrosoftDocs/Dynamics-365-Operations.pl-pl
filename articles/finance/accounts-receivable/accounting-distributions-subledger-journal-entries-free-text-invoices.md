---
title: Zasady podziału księgowań i wpisy w arkuszu księgi dla faktur niezależnych
description: Zasady podziału księgowań służą do określania sposobu księgowania kwot, takich jak przychody, podatki lub opłaty, na fakturze niezależnej. Każdy kwota, która musi zostać zaksięgowana w trakcie zapisu w arkuszu dla faktury niezależnej, będzie posiadać jedną lub więcej zasad podziału księgowań.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: roschlom
ms.custom: 3141
ms.assetid: fecd17a2-d7b4-4a20-ac81-eb71abbfa9d1
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3d5b35347d63bffbf5b9261cbd93f49120ded19a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5248070"
---
# <a name="accounting-distributions-and-subledger-entries-for-free-text-invoices"></a>Zasady podziału księgowań i wpisy księgi podrzędnej dla faktur niezależnych

[!include [banner](../includes/banner.md)]

Zasady podziału księgowań służą do określania sposobu księgowania kwot, takich jak przychody, podatki lub opłaty, na fakturze niezależnej. Każdy kwota, która musi zostać zaksięgowana w trakcie zapisu w arkuszu dla faktury niezależnej, będzie posiadać jedną lub więcej zasad podziału księgowań.

<a name="accounting-distributions"></a>Zasady podziału księgowań
------------------------

Za pomocą następujących przycisków na stronie Faktura niezależna, możesz wyświetlać i ewentualnie zmienić zasady podziału księgowań dla faktury niezależnej.

-   **Rozdziel kwoty** — Wyświetlanie i modyfikowanie zasad podziału księgowań dla pojedynczego wiersza i wszystkich wierszy podrzędnych, takich jak podatki lub opłaty. Można również wyświetlać i modyfikować zasady podziału księgowań dla wiersza podrzędnego bezpośrednio ze strony Transakcje podatkowe lub Transakcje opłat.
    -   Zmienianie kwot nagłówka faktury niezależnej, takich jak opłaty lub kwoty zaokrąglenia.
    -   Zmienianie kwot wiersza faktury niezależnej.
-   **Wyświetl dystrybucje** — Wyświetlanie zasad podziału księgowań dla wszystkich wierszy w dokumencie. Nie można zmienić zasad podziału księgowań w tym widoku.
    -   Wyświetlenie kwot nagłówka i wiersza.

## <a name="distributing-amounts"></a>Przydzielanie kwot
Podczas wprowadzania faktury niezależnej, każda kwota będzie podzielona w następujący sposób.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Typ kwoty pieniężnej</th>
<th>Skąd jest wyświetlane konto główne</th>
<th>Kolejność priorytetów, która określa, który domyślny wymiar finansowy jest wyświetlany</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Wiersz faktury niezależnej</td>
<td>Konto księgi dla wiersza faktury niezależnej.</td>
<td><ol>
<li>Jeśli konto główne jest kontem alokacji, użyj domyślnej wartości głównego z definicji konta alokacji.</li>
<li>Jeśli konto główne nie jest kontem alokacji, użyj szablonu domyślnego wymiaru finansowego w wierszu faktury niezależnej.</li>
<li>Użyj domyślnych wartości wymiaru finansowego dla wiersza faktury niezależnej.</li>
<li>Użyj domyślnych wartości wymiarów finansowych z konta księgowego na stronie Plan kont.</li>
</ol></td>
</tr>
<tr class="even">
<td>Wiersz faktury niezależnej dla kombinacji środka trwałego i modelu ewidencji
<div class="alert">
<table>
<thead>
<tr class="header">
<th><strong>Uwaga </strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Konto główne w wierszu faktury niezależnej będzie kontem likwidacji środków trwałych.</td>
</tr>
</tbody>
</table>
</div></td>
<td>Konto księgi dla wiersza faktury niezależnej.</td>
<td><ol>
<li>Użyj domyślnych wartości wymiaru finansowego dla wiersza faktury niezależnej.</li>
<li>Użyj domyślnych wartości wymiarów finansowych z konta księgowego na stronie Plan kont.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Kwota rabatu faktury niezależnej</td>
<td>Pole Konto główne rabatów odbiorcy na stronie Rabaty gotówkowe.</td>
<td><ol>
<li>Jeśli konto główne jest kontem alokacji, użyj domyślnej wartości głównego z definicji konta alokacji.</li>
<li>Jeśli konto główne nie jest kontem alokacji, użyj szablonu domyślnego wymiaru finansowego w wierszu faktury niezależnej.</li>
<li>Użyj domyślnych wartości wymiaru finansowego dla wiersza faktury niezależnej.</li>
<li>Użyj domyślnych wartości wymiarów finansowych z konta księgowego na stronie Plan kont.</li>
</ol></td>
</tr>
<tr class="even">
<td>Kwota podatku na fakturze niezależnej</td>
<td>Pole Podatek należny na stronie Grupy księgowania.</td>
<td><ol>
<li>Należy użyć wymiarów finansowych, które zostały zdefiniowane w kwocie wiersza faktury niezależnej dystrybucjach dla kwoty wiersza opłaty.</li>
<li>Użyj domyślnych wartości wymiaru finansowego dla wiersza faktury niezależnej.</li>
<li>Użyj domyślnych wartości wymiarów finansowych z konta księgowego na stronie Plan kont.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Kwota wiersza opłaty faktury niezależnej</td>
<td>Pole Konto kredytowe na stronie Kod opłat.</td>
<td><ol>
<li>Jeśli konto główne jest kontem alokacji, użyj domyślnej wartości głównego z definicji konta alokacji.</li>
<li>Jeśli konto główne nie jest kontem alokacji, użyj szablonu domyślnego wymiaru finansowego w wierszu faktury niezależnej.</li>
<li>Użyj domyślnych wartości wymiaru finansowego dla wiersza faktury niezależnej.</li>
<li>Użyj domyślnych wartości wymiarów finansowych z konta księgowego na stronie Plan kont.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="distributing-taxes"></a>Dystrybuowanie podatków
Zasady podziału księgowań dla podatków można utworzyć dopiero po obliczeniu podatków. Aby obliczyć podatek, należy wykonać jedną z następujących czynności w formularzu Faktura od dostawcy:
-   Wyświetlanie podatku.
-   Wyświetl sumę faktury.
-   Wyświetl przepływy pieniężne.
-   Wyświetlanie zasad podziału księgowań dla całej faktury niezależnej.
-   Wyświetlanie arkusza księgi podrzędnej.

## <a name="subledger-journals-for-free-text-invoices"></a> Arkusze księgi podrzędnej dla faktur niezależnych
Przed zaksięgowaniem faktury niezależnej, można wyświetlić pełny wpis księgowy faktury, który obejmuje obciążenia i uznania, aby zweryfikować, że faktura została zaksięgowana na właściwych kontach. Ten widok pełnego wpisu księgowania nazywa się arkuszem księgi podrzędnej. Jeżeli zapis w arkuszu księgi podrzędnej jest nieprawidłowy w podglądzie przed zapisaniem faktury niezależnej w arkuszu, nie można modyfikować zapisu w arkuszu księgi podrzędnej. Zamiast tego należy zmienić zasady podziału księgowań albo profil księgowania. Zasady podziału księgowań służą do definiowania jednej strony wpisu księgowania: debetu lub kredytu. Zapis księgowania transakcji przeciwstawnych w arkuszu księgi podrzędnej jest tworzony z profilów księgowania, takich jak konto odbiorca lub podatek.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]