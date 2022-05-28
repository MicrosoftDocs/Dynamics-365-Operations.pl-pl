---
title: Raport wiekowania dla odbiorców
description: Raport wiekowania dla odbiorców zawiera salda należne od odbiorców, posortowane według interwałów dat lub okresów wiekowania.
author: JodiChristiansen
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ecd8a402f5bc72cf503607b8b42b892749859639
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735211"
---
# <a name="customer-aging-report"></a>Raport wiekowania dla odbiorców 

Raport **Wiekowanie odbiorców** zawiera salda należne od odbiorców, posortowane według interwałów dat lub okresów wiekowania.

Podczas generowania tego raportu, wyświetlane są następujące parametry domyślne. Możesz używać tych parametrów filtrowania danych, które będą wyświetlane w raporcie. Aby uzyskać więcej informacji, zobacz [Konfigurowanie kolekcji](set-up-collections.md).

<table>
<colgroup>
<col>
<col>
</colgroup>
<thead>
<tr class="header">
<th><p>Pole</p></th>
<th><p>opis</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Klasyfikacja faktur</strong></p></td>
<td><p>Wybierz jedną lub kilka klasyfikacji faktur do uwzględnienia w raporcie.</p>
<div class="alert">

**Uwaga:** Ten formant jest dostępny tylko wtedy, gdy wybrano klucz konfiguracji <STRONG>Sektor publiczny</STRONG>.</P>


</div></td>
</tr>
<tr class="even">
<td><p><strong>Uwzględnij transakcje bez klasyfikacji faktur</strong></p></td>
<td><p>Jeśli to pole wyboru jest zaznaczone, w raporcie będą wyświetlane wszystkie transakcje, które nie mają przypisanej klasyfikacji faktur.</p>
<div class="alert">

**Uwaga:** Ten formant jest dostępny tylko wtedy, gdy wybrano klucz konfiguracji <STRONG>Sektor publiczny</STRONG>.</P>

</div></td>
</tr>
<tr class="odd">
<td><p><strong>Wiekowanie na dzień</strong></p></td>
<td><p>Umożliwia wprowadzenie daty używanej w bieżącym zasobniku wiekowania.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Saldo na</strong></p></td>
<td><p>Umożliwia wprowadzenie daty, według której będą wyświetlane salda odbiorców. Jest ona również określana jako data graniczna transakcji.</p></td>
</tr>
<tr class="even">
<td><p><strong>Rozpoczęcie</strong></p></td>
<td><p>Służy do wprowadzania daty należącej do pierwszego przedziału okresu lub okresu wiekowania do uwzględnienia w raporcie.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Kryterium</strong></p></td>
<td><p>Służy do wybrania typu daty, na której ma się opierać raport.</p>
<ul>
<li><p><strong>Data transakcji</strong> – data księgowania wybranej transakcji. Na przykład może to być data faktury stanowiąca podstawę obliczania terminu płatności.</p></li>
<li><p><strong>Data ukończenia</strong> — termin transakcji na podstawie warunków płatności.</p></li>
<li><p><strong>Data dokumentu</strong> — data dokumentu zdefiniowanego przez użytkownika stanowiąca podstawę obliczeń terminu.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Definicja okresu wiekowania</strong></p></td>
<td><p>Wybierz definicję okresu wiekowania. Pole <strong>Interwał</strong> nie jest używane w przypadku wybrania definicji okresu wiekowania.</p>
<p>W wydrukowanym raporcie nie można używać definicji okresów wiekowania mających więcej niż sześć okresów wiekowania.</p>
<div class="alert">

**Uwaga:** okresy wiekowania można skonfigurować na stronie <STRONG>Definicje okresów wiekowania</STRONG>.</P>


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Drukuj opis okresu wiekowania</strong></p></td>
<td><p>Wybierz opcję <strong>Tak</strong>, aby na górze każdej kolumny okresu wiekowania w raporcie uwzględnić opisy okresów wiekowania. Wybierz opcję <strong>Nie</strong>, aby wydrukować raport bez nagłówków kolumn.</p></td>
</tr>
<tr class="even">
<td><p><strong>Interwał</strong></p></td>
<td><p>Służy do definiowania okresu do zastosowania za pomocą wprowadzenia liczby jednostek dni lub miesięcy w każdym okresie. Na przykład aby wyświetlić informacje wiekowania według tygodnia, wpisz 7 w tym polu i wybierz <strong>Dzień</strong> w polu <strong>Dzień/Mies</strong>.</p>
<div class="alert">

**Uwaga:** Informacje wprowadzone w tym polu są używane tylko, jeśli nie wybrano definicji okresu wiekowania. W przeciwnym razie kierunek drukowania jest definiowany w definicji okresu wiekowania.</P>


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Dzień/Mies.</strong></p></td>
<td><p>Służy do wybierania jednostki, <strong>Dzień</strong> lub <strong>Miesiąc</strong>, która jest stosowana do definiowania okresu w polu <strong>Interwał</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Kierunek drukowania</strong></p></td>
<td><p>Umożliwia określenie, czy mają być obliczane salda i drukowany raport wiekowania w przeszłych i przyszłych okresach. Daty są oceniane w odniesieniu do daty wybranej w polu <strong>Saldo na dzień</strong>. Należy wybrać opcję <strong>Wstecz</strong>, aby umieścić informacje dla minionych okresów. Należy wybrać opcję<strong>Dalej</strong>, aby umieścić informacje dla przyszłych okresów.</p>
<div class="alert">
  
<STRONG>Uwaga:</STRONG> Informacje wprowadzone w tym polu są używane tylko, jeśli nie wybrano definicji okresu wiekowania.</P>


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Szczegóły</strong></p></td>
<td><p>Wybierz, aby wyświetlić listę transakcji transakcji zawartych w saldach wyświetlonych w raporcie.</p></td>
</tr>
<tr class="even">
<td><p><strong>Uwzględnij kwoty w walucie transakcji</strong></p></td>
<td><p>Wybierz tę opcję, aby uwzględnić w walucie transakcji kwoty, oprócz kwot w walucie rozliczeniowej. Jeśli to pole wyboru nie jest zaznaczone, kwoty w raporcie są wyświetlane tylko w walucie rozliczeniowej.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Saldo ujemne</strong></p></td>
<td><p>Wybierz tę opcję, aby uwzględnić konta odbiorców, które mają salda ujemne.</p></td>
</tr>
<tr class="even">
<td><p><strong>Wyklucz zerowe konta bilansowe</strong></p></td>
<td><p>Wybierz tę opcję, aby wykluczyć konta odbiorców, które mają salda zerowe.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pozycjonowanie płatności</strong></p></td>
<td><p>Wybranie tej opcji umożliwia wyświetlenie płatności, które nie zostały rozliczone. Są one wyświetlane w pierwszej kolumnie raportu.</p></td>
</tr>
</tbody>
</table>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
