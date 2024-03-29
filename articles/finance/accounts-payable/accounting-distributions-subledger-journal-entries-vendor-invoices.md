---
title: Zasady podziału księgowań i wpisów w arkuszu księgi dla faktur od dostawców
description: Zasady podziału księgowań są używane do określania sposobu księgowania kwot, to znaczy sposobu księgowania wydatków, podatków lub opłat na fakturze od dostawcy. Każdy kwota, która musi zostać zaksięgowana w trakcie zapisu w arkuszu dla faktury od dostawcy, będzie posiadać jedną lub więcej zasad podziału księgowań.
author: sunfzam
ms.date: 02/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendEditInvoice
audience: Application User
ms.reviewer: twheeloc
ms.custom: 26891
ms.assetid: 93dc608a-b5b4-4ec3-83c2-618e3d80a583
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f10ddf113f59da4800a97a48300ab1310bfb42dd
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/26/2022
ms.locfileid: "8358188"
---
# <a name="accounting-distributions-and-journal-entries-for-vendor-invoices"></a>Zasady podziału księgowań i wpisów w arkuszu księgi dla faktur od dostawców

[!include [banner](../includes/banner.md)]

Zasady podziału księgowań są używane do określania sposobu księgowania kwot, to znaczy sposobu księgowania wydatków, podatków lub opłat na fakturze od dostawcy. Każdy kwota, która musi zostać zaksięgowana w trakcie zapisu w arkuszu dla faktury od dostawcy, będzie posiadać jedną lub więcej zasad podziału księgowań. 

## <a name="accounting-distributions"></a>Zasady podziału księgowań 

Za pomocą następujących przycisków na stronie Faktura od dostawcy, możesz wyświetlać i ewentualnie zmodyfikować zasady podziału księgowań dla faktury od dostawcy.
-   **Rozdziel kwoty** — Wyświetlanie i modyfikowanie zasad podziału księgowań dla pojedynczego wiersza i wszystkich wierszy podrzędnych, takich jak podatki lub opłaty. Można również wyświetlać i modyfikować zasady podziału księgowań dla wiersza podrzędnego bezpośrednio ze strony **Transakcje podatkowe** lub **Transakcje opłat**.
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
<li>Pole <strong>Konto główne</strong> po wybraniu opcji Koszty zakupu produktów na stronie <strong>Księgowanie</strong>.</li>
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
<li>Pole <strong>Konto główne</strong> po wybraniu opcji Koszty zakupu na stronie <strong>Księgowanie</strong>.</li>
</ol></td>
<td><ol>
<li>Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</li>
<li>Jeśli konto główne jest kontem alokacji, użyj domyślnej wartości głównego z definicji konta alokacji.</li>
<li>Użyj domyślnych wartości wymiaru finansowego dla faktury od dostawcy.</li>
<li>Użyj wartości wymiaru finansowego z wiersza faktury od dostawcy.</li>
<li>Użyj domyślnych wartości wymiarów finansowych z konta głównego na stronie <strong>Plan kont</strong>.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Środek trwały</td>
<td><ol>
<li>Zasady podziału księgowań dla wiersza zamówienia zakupu, jeśli wiersz faktury od dostawcy odwołuje się do wiersza zamówienia zakupu.</li>
<li>Jeśli opcja <strong>Nabycie</strong> jest wybrana w polu <strong>Typ transakcji</strong> w formularzu <strong>Faktura od dostawcy</strong>, pole <strong>Konto główne</strong> po wybraniu opcji <strong>Nabycie</strong> na stronie <strong>Profile księgowania środków trwałych</strong>.</li>
<li>Jeśli opcja <strong>Korekta wartości początkowej</strong> jest wybrana w polu <strong>Typ transakcji</strong>, pole <strong>Konto główne</strong> po wybraniu opcji <strong>Korekta wartości początkowej</strong> na stronie <strong>Profile księgowania środków trwałych</strong>.</li>
</ol></td>
<td><ol>
<li>Użyj zasady podziału księgowań dla wiersza zamówienia zakupu, jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu.</li>
<li>Użyj wartości wymiaru finansowego z wiersza faktury od dostawcy.</li>
<li>Użyj domyślnych wartości wymiarów finansowych z konta głównego na stronie <strong>Plan kont</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Projekt zdefiniowany w wierszu faktury od dostawcy</td>
<td><ol>
<li>Zasady podziału księgowań dla wiersza zamówienia zakupu, jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu.</li>
<li>Po wybraniu opcji <strong>Saldo</strong> w <strong>Księgowaniu kosztów — pole towaru</strong> na stronie <strong>Grupy projektu</strong>, pole <strong>Konto główne</strong>, gdy wybrana jest opcja <strong>Koszt</strong> na stronie <strong>Konfiguracja księgowania</strong>.</li>
<li>Po wybraniu opcji <strong>Zyski i straty</strong> w <strong>Księgowaniu kosztów — pole towaru</strong> na stronie <strong>Grupy projektu</strong>, pole <strong>Konto główne</strong>, gdy wybrana jest opcja <strong>Koszt — towar</strong> na stronie <strong>Konfiguracja księgowania</strong>.</li>
</ol></td>
<td><ol>
<li>Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Rabat wiersza</td>
<td><ol>
<li>Zasady podziału księgowań dla wiersza zamówienia zakupu, jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu.</li>
<li>Pole <strong>Konto główne</strong>, gdy opcja <strong>Rabat</strong> jest wybrana na stronie <strong>Księgowanie</strong>.</li>
<li>Jeśli nie zdefiniowano konta głównego dla rabatów w profilu księgowania, zasada podziału księgowań dla ceny rozszerzonej w wierszu zamówienia zakupu.</li>
</ol></td>
<td><ol>
<li>Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</li>
<li>Użyj wymiarów finansowych z zasad podziału księgowań dla rozszerzonej ceny w wierszu faktury od dostawcy.</li>
<li>Użyj wartości wymiaru finansowego dla wiersza faktury od dostawcy.</li>
<li>Użyj domyślnych wartości wymiarów finansowych z konta głównego na stronie <strong>Plan kont</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Opłata za zakup, która jest wprowadzona na karcie <strong>Cena i rabat</strong> wiersza zamówienia zakupu</td>
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
<li>Jeśli wybrano <strong>Konto księgowe</strong> w polu <strong>Typ debetu</strong> w formularzu <strong>Kod opłat</strong>, pole <strong>Konto debetu</strong> na stronie <strong>Kod opłat</strong>.</li>
<li>Jeśli wybrano <strong>Towar</strong> w polu <strong>Typ debetu</strong> w formularzu <strong>Kod opłat</strong>, zasady podziału księgowań dla ceny rozszerzonej w wierszu zamówienia zakupu.</li>
<li>Jeśli wybrano <strong>Odbiorca/Dostawca</strong> w polu <strong>Typ debetu</strong> na stronie <strong>Kod opłat</strong>, pole <strong>Konto kredytu</strong> na stronie <strong>Kod opłat</strong>.</li>
</ol></td>
<td><ol>
<li>Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</li>
<li>Użyj wymiarów finansowych z zasad podziału księgowań dla rozszerzonej ceny w wierszu faktury od dostawcy.</li>
<li>Użyj wartości wymiaru finansowego z wiersza faktury od dostawcy.</li>
<li>Użyj domyślnych wartości wymiarów finansowych z konta głównego na stronie <strong>Plan kont</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Podatek, pod następującym warunkiem:
<ul>
<li>Opcja <strong>Zastosuj zasady opodatkowania</strong> dla Stanów Zjednoczonych jest wybrana na stronie <strong>Parametry księgi głównej</strong>.</li>
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
<li>Opcja <strong>Zastosuj zasady opodatkowania</strong> dla Stanów Zjednoczonych nie jest wybrana na stronie <strong>Parametry księgi głównej</strong>.</li>
<li>Pole <strong>Użyj podatku</strong> dla grupy podatku nie jest zaznaczone na stronie <strong>Grupy podatku</strong>.</li>
</ul></td>
<td><ol>
<li>Jeśli kwota podatku jest objęta zwrotem, pole <strong>Podatek naliczony</strong> na stronie <strong>Grupy księgowania</strong>.</li>
<li>Jeśli kwota podatku nie jest objęta zwrotem, cena rozszerzona lub zasada podziału księgowań dla opłaty.</li>
</ol></td>
<td><ol>
<li>Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</li>
<li>Użyj wymiarów finansowych z ceny rozszerzonej lub zasad podziału księgowań dla opłaty w wierszu faktury od dostawcy.</li>
<li>Użyj wartości wymiaru finansowego z wiersza faktury od dostawcy.</li>
<li>Użyj domyślnych wartości wymiarów finansowych z konta głównego na stronie <strong>Plan kont</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Podatek, pod następującymi warunkami:
<ul>
<li>Opcja Zastosuj zasady opodatkowania dla Stanów Zjednoczonych nie jest wybrana na stronie <strong>Parametry księgi głównej</strong>.</li>
<li>Pole <strong>Użyj podatku</strong> dla grupy podatku jest zaznaczone na stronie <strong>Grupy podatku</strong>.</li>
</ul></td>
<td><ol>
<li>Jeśli kwota podatku jest objęta zwrotem, pole <strong>Podatek naliczony</strong> na stronie <strong>Grupy księgowania</strong>.</li>
<li>Jeśli kwota podatku nie jest objęta zwrotem, pole <strong>Wydatki podatku nienaliczonego</strong> na stronie <strong>Grupy księgowania</strong>.</li>
</ol></td>
<td><ol>
<li>Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</li>
<li>Użyj wymiarów finansowych z ceny rozszerzonej lub zasad podziału księgowań dla opłaty w wierszu faktury od dostawcy.</li>
<li>Użyj wartości wymiaru finansowego z wiersza faktury od dostawcy.</li>
<li>Użyj domyślnych wartości wymiarów finansowych z konta głównego na stronie <strong>Plan kont</strong>.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Opłata w nagłówku</td>
<td><ol>
<li>Jeśli wybrano <strong>Konto księgowe</strong> w polu <strong>Typ debetu</strong> w formularzu <strong>Kod opłat</strong>, pole <strong>Konto debetu</strong> na stronie <strong>Kod opłat</strong>.</li>
<li>Jeśli wybrano <strong>Odbiorca/Dostawca</strong> w polu <strong>Typ debetu</strong> na stronie <strong>Kod opłat</strong>, pole <strong>Konto kredytu</strong> na stronie <strong>Kod opłat</strong>.</li>
</ol></td>
<td><ol>
<li>Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</li>
<li>Jeśli konto główne jest kontem alokacji, użyj domyślnej wartości głównego z definicji konta alokacji.</li>
<li>Użyj domyślnych wartości szablonu wymiaru finansowego z nagłówka faktury od dostawcy.</li>
<li>Użyj wartości wymiaru finansowego z wiersza faktury od dostawcy.</li>
<li>Użyj domyślnych wartości wymiarów finansowych z konta głównego na stronie <strong>Plan kont</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Rabat dla nagłówka</td>
<td><ol>
<li>Pole <strong>Konto główne</strong> dla typu księgowania <strong>Rabat na fakturze dostawcy</strong> na stronie <strong>Konta dla transakcji automatycznych</strong>.</li>
</ol></td>
<td><ol>
<li>Jeśli wiersz faktury odwołuje się do wiersza zamówienia zakupu, należy użyć zasady podziału księgowań dla wiersza zamówienia zakupu.</li>
<li>Użyj wymiarów finansowych z zasad podziału księgowań dla rozszerzonej ceny w wierszu faktury od dostawcy.</li>
<li>Użyj wartości wymiaru finansowego z wiersza faktury od dostawcy.</li>
<li>Użyj domyślnych wartości wymiarów finansowych z konta głównego na stronie <strong>Plan kont</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>


## <a name="distributing-taxes"></a>Dystrybuowanie podatków

Zasady podziału księgowań dla podatków można utworzyć dopiero po obliczeniu podatków. Aby obliczyć podatek, należy wykonać jedną z następujących czynności na stronie **Faktura od dostawcy**:
-   Wyświetl sumę faktury.
-   Wyświetlanie podatku.
-   Wyświetlanie arkusza księgi podrzędnej.
-   Wyświetlanie zasad podziału księgowań dla kompletnej faktury od dostawcy.
-   Wstrzymywanie faktury od dostawcy.
-   Księgowanie faktury od dostawcy.

## <a name="subledger-journals-for-vendor-invoices"></a>Arkusze księgi podrzędnej dla faktur od dostawcy
Przed zaksięgowaniem faktury od dostawcy, można wyświetlić pełny wpis księgowy faktury, który obejmuje obciążenia i uznania, aby zweryfikować, że faktura została zaksięgowana na właściwych kontach. Ten widok pełnego wpisu księgowania nazywa się arkuszem księgi podrzędnej. 

Jeżeli zapis w arkuszu księgi podrzędnej jest nieprawidłowy w podglądzie przed zapisaniem faktury od dostawcy w arkuszu, nie można modyfikować zapisu w arkuszu księgi podrzędnej. Zamiast tego należy zmodyfikować zasady podziału księgowań albo profil księgowania. Zasady podziału księgowań służą do definiowania jednej strony wpisu księgowania: debetu lub kredytu. Zapis księgowania transakcji przeciwstawnych w arkuszu księgi podrzędnej jest tworzony za pomocą profilów księgowania, takich jak konto dostawcy lub podatek.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
