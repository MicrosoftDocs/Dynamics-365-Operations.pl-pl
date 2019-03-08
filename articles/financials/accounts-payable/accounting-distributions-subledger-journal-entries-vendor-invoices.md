---
title: Zasady podziału księgowań i zapisów w arkuszu księgi podrzędnej dla faktur od dostawcy
description: Zasady podziału księgowań są używane do określania sposobu księgowania kwot, to znaczy sposobu księgowania wydatków, podatków lub opłat na fakturze od dostawcy. Każdy kwota, która musi zostać zaksięgowana w trakcie zapisu w arkuszu dla faktury od dostawcy, będzie posiadać jedną lub więcej zasad podziału księgowań.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendEditInvoice
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 26891
ms.assetid: 93dc608a-b5b4-4ec3-83c2-618e3d80a583
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f59eb2f61bc6bc887461683408b57c4672ce5bf1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "351362"
---
# <a name="accounting-distributions-and-subledger-journal-entries-for-vendor-invoices"></a>Zasady podziału księgowań i zapisów w arkuszu księgi podrzędnej dla faktur od dostawcy

[!include [banner](../includes/banner.md)]

Zasady podziału księgowań są używane do określania sposobu księgowania kwot, to znaczy sposobu księgowania wydatków, podatków lub opłat na fakturze od dostawcy. Każdy kwota, która musi zostać zaksięgowana w trakcie zapisu w arkuszu dla faktury od dostawcy, będzie posiadać jedną lub więcej zasad podziału księgowań. 

<a name="accounting-distributions"></a>Zasady podziału księgowań 
-------------------------

Za pomocą następujących przycisków na stronie Faktura od dostawcy, możesz wyświetlać i ewentualnie zmodyfikować zasady podziału księgowań dla faktury od dostawcy.
-   **Rozdziel kwoty** — Wyświetlanie i modyfikowanie zasad podziału księgowań dla pojedynczego wiersza i wszystkich wierszy podrzędnych, takich jak podatki lub opłaty. Można również wyświetlać i modyfikować zasady podziału księgowań dla wiersza podrzędnego bezpośrednio ze strony Transakcje podatkowe lub Transakcje opłat.
    -   Modyfikowanie kwot nagłówka faktury od dostawcy, takich jak opłaty lub kwoty zaokrąglenia.
    -   Modyfikowanie kwot wiersza faktury od dostawcy.
-   **Wyświetl dystrybucje** — Wyświetlanie zasad podziału księgowań dla wszystkich wierszy w dokumencie. Nie można zmodyfikować zasad podziału księgowań w tym widoku.
    -   Wyświetlenie kwot nagłówka i wiersza.

Jeśli faktura od dostawcy odwołuje się do zamówienia zakupu, można podzielić i zmodyfikować zasady podziału księgowań dla wierszy, które zawierają towar, który nie jest składowany. Jeśli wiersz faktury od dostawcy nie odwołuje się do wiersza zamówienia zakupu, można usunąć zasady podziału księgowań. Nie można rozdzielić lub usunąć wierszy dla opłat, podatków i rabatów wiersza. Konto księgowe można zmodyfikować, ale nie można zmienić kwot lub wartości procentowych.
> [!NOTE]                                                                                                                                 
> Jeśli wiersz nadrzędny zawiera towar, który nie jest składowany, a zasady podziału księgowań są podzielone, wiersz podrzędny zostanie podzielony automatycznie, aby dopasować wymiary finansowe wiersza nadrzędnego. Zasady podziału księgowań dla wiersza podrzędnego nie mogą być dodatkowo podzielone ani usunięte, ale w zależności od konfiguracji wiersza podrzędnego, może być możliwe modyfikowanie konta księgowego dla zasad podziału księgowań podrzędnego wiersza.

## <a name="distributing-amounts"></a>Przydzielanie kwot
Podczas wprowadzania faktury od dostawcy, każda kwota będzie podzielona w następujący sposób.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Typ wiersza dla faktury od dostawcy</th>
<th>Kolejność priorytetów, która określa, skąd jest wyświetlane konto główne</th>
<th>Kolejność priorytetów, która określa, który domyślny wymiar finansowy jest wyświetlany</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Produkt magazynowany</td>
<td><ol>
<li>Zasady podziału księgowań dla wiersza zamówienia zakupu.</li>
<li>Pole Konto główne po wybraniu opcji Koszty zakupu produktów na stronie Księgowanie.</li>
</ol></td>
<td><ol>
<li>Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</li>
<li>Użyj domyślnych wartości wymiaru finansowego dla faktury od dostawcy.</li>
</ol></td>
</tr>
<tr class="even">
<td>Kategoria zaopatrzenia lub towar, który nie jest składowany</td>
<td><ol>
<li>Zasady podziału księgowań dla wiersza zamówienia zakupu, jeśli wiersz faktury od dostawcy odwołuje się do wiersza zamówienia zakupu.</li>
<li>Pole Konto główne po wybraniu opcji Koszty zakupu na stronie Księgowanie.</li>
</ol></td>
<td><ol>
<li>Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</li>
<li>Jeśli konto główne jest kontem alokacji, użyj domyślnej wartości głównego z definicji konta alokacji.</li>
<li>Użyj domyślnych wartości wymiaru finansowego dla faktury od dostawcy.</li>
<li>Użyj wartości wymiaru finansowego z wiersza faktury od dostawcy.</li>
<li>Użyj domyślnych wartości wymiarów finansowych z konta głównego na stronie Plan kont.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Środek trwały</td>
<td><ol>
<li>Zasady podziału księgowań dla wiersza zamówienia zakupu, jeśli wiersz faktury od dostawcy odwołuje się do wiersza zamówienia zakupu.</li>
<li>Jeśli opcja Nabycie jest wybrana w polu Typ transakcji w formularzu Faktura od dostawcy, pole Konto główne po wybraniu opcji Nabycie na stronie Profile księgowania środków trwałych.</li>
<li>Jeśli opcja Korekta wartości początkowej jest wybrana w polu Typ transakcji, pole Konto główne po wybraniu opcji Korekta wartości początkowej na stronie Profile księgowania środków trwałych.</li>
</ol></td>
<td><ol>
<li>Użyj zasady podziału księgowań dla wiersza zamówienia zakupu, jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu.</li>
<li>Użyj wartości wymiaru finansowego z wiersza faktury od dostawcy.</li>
<li>Użyj domyślnych wartości wymiarów finansowych z konta głównego na stronie Plan kont.</li>
</ol></td>
</tr>
<tr class="even">
<td>Projekt zdefiniowany w wierszu faktury od dostawcy</td>
<td><ol>
<li>Zasady podziału księgowań dla wiersza zamówienia zakupu, jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu.</li>
<li>Po wybraniu opcji Saldo w Księgowaniu kosztów — pole towaru na stronie Grupy projektu, pole Konto główne, gdy wybrana jest opcja Koszt na stronie Konfiguracja księgowania.</li>
<li>Po wybraniu opcji Zyski i straty w Księgowaniu kosztów — pole towaru na stronie Grupy projektu, pole Konto główne, gdy wybrana jest opcja Koszt — towar na stronie Konfiguracja księgowania.</li>
</ol></td>
<td><ol>
<li>Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Rabat wiersza</td>
<td><ol>
<li>Zasady podziału księgowań dla wiersza zamówienia zakupu, jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu.</li>
<li>Pole Konto główne, gdy opcja Rabat jest wybrana na stronie Księgowanie.</li>
<li>Jeśli nie zdefiniowano konta głównego dla rabatów w profilu księgowania, zasada podziału księgowań dla ceny rozszerzonej w wierszu zamówienia zakupu.</li>
</ol></td>
<td><ol>
<li>Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</li>
<li>Użyj wymiarów finansowych z zasad podziału księgowań dla rozszerzonej ceny w wierszu faktury od dostawcy.</li>
<li>Użyj wartości wymiaru finansowego dla wiersza faktury od dostawcy.</li>
<li>Użyj domyślnych wartości wymiarów finansowych z konta głównego na stronie Plan kont.</li>
</ol></td>
</tr>
<tr class="even">
<td>Opłata za zakup, która jest wprowadzona na karcie Cena i rabat wiersza zamówienia zakupu</td>
<td><ol>
<li>Zasady podziału księgowań dla wiersza zamówienia zakupu, jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu.</li>
<li>Zasada podziału księgowań rozszerzonej ceny w wierszu zamówienia zakupu.</li>
</ol></td>
<td><ol>
<li>Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</li>
<li>Użyj wymiarów finansowych z zasad podziału księgowań dla rozszerzonej ceny w wierszu faktury od dostawcy.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Opłata za wiersz</td>
<td><ol>
<li>Zasady podziału księgowań dla wiersza zamówienia zakupu, jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu.</li>
<li>Jeśli wybrano Konto księgowe w polu debetu Typ w formularzu Kod opłat, pole debetu Konto na stronie Kod opłat.</li>
<li>Jeśli wybrano Towar w polu debetu Typ w formularzu Kod opłat, zasady podziału księgowań dla ceny rozszerzonej w wierszu zamówienia zakupu.</li>
<li>Jeśli wybrano Odbiorca/Dostawca w polu debetu Typ w formularzu Kod opłat, pole kredytu Konto na stronie Kod opłat.</li>
</ol></td>
<td><ol>
<li>Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</li>
<li>Użyj wymiarów finansowych z zasad podziału księgowań dla rozszerzonej ceny w wierszu faktury od dostawcy.</li>
<li>Użyj wartości wymiaru finansowego z wiersza faktury od dostawcy.</li>
<li>Użyj domyślnych wartości wymiarów finansowych z konta głównego na stronie Plan kont.</li>
</ol></td>
</tr>
<tr class="even">
<td>Podatek, pod następującym warunkiem:
<ul>
<li>Opcja Zastosuj zasady opodatkowania dla Stanów Zjednoczonych jest wybrana na stronie Parametry księgi głównej.</li>
</ul></td>
<td><ol>
<li>Zasady podziału księgowań dla wiersza zamówienia zakupu, jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu.</li>
<li>Zasady podziału księgowań dla ceny rozszerzonej lub opłaty.</li>
</ol></td>
<td><ol>
<li>Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</li>
<li>Użyj wymiarów finansowych z zasad podziału księgowań dla rozszerzonej ceny w wierszu faktury od dostawcy.</li>
<li>Użyj wartości wymiaru finansowego z wiersza faktury od dostawcy.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Podatek, pod następującymi warunkami:
<ul>
<li>Opcja Zastosuj zasady opodatkowania dla Stanów Zjednoczonych nie jest wybrana na stronie Parametry księgi głównej.</li>
<li>Pole Użyj podatku dla grupy podatku nie jest zaznaczone na stronie Grupy podatku.</li>
</ul></td>
<td><ol>
<li>Jeśli kwota podatku jest objęta zwrotem, pole Podatek naliczony na stronie Grupy księgowania.</li>
<li>Jeśli kwota podatku nie jest objęta zwrotem, cena rozszerzona lub zasada podziału księgowań dla opłaty.</li>
</ol></td>
<td><ol>
<li>Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</li>
<li>Użyj wymiarów finansowych z ceny rozszerzonej lub zasad podziału księgowań dla opłaty w wierszu faktury od dostawcy.</li>
<li>Użyj wartości wymiaru finansowego z wiersza faktury od dostawcy.</li>
<li>Użyj domyślnych wartości wymiarów finansowych z konta głównego na stronie Plan kont.</li>
</ol></td>
</tr>
<tr class="even">
<td>Podatek, pod następującymi warunkami:
<ul>
<li>Opcja Zastosuj zasady opodatkowania dla Stanów Zjednoczonych nie jest wybrana na stronie Parametry księgi głównej.</li>
<li>Pole Użyj podatku dla grupy podatku jest zaznaczone na stronie Grupy podatku.</li>
</ul></td>
<td><ol>
<li>Jeśli kwota podatku jest objęta zwrotem, pole Podatek naliczony na stronie Grupy księgowania.</li>
<li>Jeśli kwota podatku nie jest objęta zwrotem, pole Wydatki podatku nienaliczonego na stronie Grupy księgowania.</li>
</ol></td>
<td><ol>
<li>Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</li>
<li>Użyj wymiarów finansowych z ceny rozszerzonej lub zasad podziału księgowań dla opłaty w wierszu faktury od dostawcy.</li>
<li>Użyj wartości wymiaru finansowego z wiersza faktury od dostawcy.</li>
<li>Użyj domyślnych wartości wymiarów finansowych z konta głównego na stronie Plan kont.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Opłata w nagłówku</td>
<td><ol>
<li>Jeśli wybrano Konto księgowe w polu debetu Typ w formularzu Kod opłat, pole debetu Konto na stronie Kod opłat.</li>
<li>Jeśli wybrano Odbiorca/Dostawca w polu debetu Typ w formularzu Kod opłat, pole kredytu Konto na stronie Kod opłat.</li>
</ol></td>
<td><ol>
<li>Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</li>
<li>Jeśli konto główne jest kontem alokacji, użyj domyślnej wartości głównego z definicji konta alokacji.</li>
<li>Użyj domyślnych wartości szablonu wymiaru finansowego z nagłówka faktury od dostawcy.</li>
<li>Użyj wartości wymiaru finansowego z wiersza faktury od dostawcy.</li>
<li>Użyj domyślnych wartości wymiarów finansowych z konta głównego na stronie Plan kont.</li>
</ol></td>
</tr>
<tr class="even">
<td>Rabat dla nagłówka</td>
<td><ol>
<li>Pole Konto główne dla typu księgowania Rabat na fakturze dostawcy na stronie Konta dla transakcji automatycznych.</li>
</ol></td>
<td><ol>
<li>Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</li>
<li>Użyj wymiarów finansowych z zasad podziału księgowań dla rozszerzonej ceny w wierszu faktury od dostawcy.</li>
<li>Użyj wartości wymiaru finansowego z wiersza faktury od dostawcy.</li>
<li>Użyj domyślnych wartości wymiarów finansowych z konta głównego na stronie Plan kont.</li>
</ol></td>
</tr>
</tbody>
</table>


<a name="distributing-taxes"></a>Dystrybuowanie podatków
------------------

Zasady podziału księgowań dla podatków można utworzyć dopiero po obliczeniu podatków. Aby obliczyć podatek, należy wykonać jedną z następujących czynności na stronie Faktura od dostawcy:
-   Wyświetl sumę faktury.
-   Wyświetlanie podatku.
-   Wyświetlanie arkusza księgi podrzędnej.
-   Wyświetlanie zasad podziału księgowań dla kompletnej faktury od dostawcy.
-   Wstrzymywanie faktury od dostawcy.
-   Księgowanie faktury od dostawcy.

## <a name="subledger-journals-for-vendor-invoices"></a>Arkusze księgi podrzędnej dla faktur od dostawcy
Przed zaksięgowaniem faktury od dostawcy, można wyświetlić pełny wpis księgowy faktury, który obejmuje obciążenia i uznania, aby zweryfikować, że faktura została zaksięgowana na właściwych kontach. Ten widok pełnego wpisu księgowania nazywa się arkuszem księgi podrzędnej. 

Jeżeli zapis w arkuszu księgi podrzędnej jest nieprawidłowy w podglądzie przed zapisaniem faktury od dostawcy w arkuszu, nie można modyfikować zapisu w arkuszu księgi podrzędnej. Zamiast tego należy zmodyfikować zasady podziału księgowań albo profil księgowania. Zasady podziału księgowań służą do definiowania jednej strony wpisu księgowania: debetu lub kredytu. Zapis księgowania transakcji przeciwstawnych w arkuszu księgi podrzędnej jest tworzony za pomocą profilów księgowania, takich jak konto dostawcy lub podatek.





