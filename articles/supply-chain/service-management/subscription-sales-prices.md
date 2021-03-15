---
title: Subskrypcja — ceny sprzedaży
description: W przypadku tworzenia subskrypcji cena sprzedaży jest ustalana na podstawie konfiguracji ceny sprzedaży utworzonej w formularzu Cena sprzedaży — subskrypcja.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASalespriceSubscription
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 35f4e3f3bdbdad7a48b89bad7da96d221f09bdb4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974231"
---
# <a name="subscription-sales-prices"></a>Subskrypcja — ceny sprzedaży   

[!include [banner](../includes/banner.md)]


W przypadku tworzenia subskrypcji cena sprzedaży jest ustalana na podstawie konfiguracji ceny sprzedaży utworzonej w formularzu **Cena sprzedaży — subskrypcja**.

W formularzu **Cena sprzedaży — subskrypcja** można utworzyć ceny sprzedaży dla określonej subskrypcji lub o szerszym zastosowaniu. Aby cena sprzedaży była stosowana do subskrypcji, kod okresu i waluta subskrypcji muszą być takie same, jak kod okresu i waluta ceny sprzedaży.

Jeśli kod okresu i waluta są takie same dla subskrypcji i ceny sprzedaży, ceny sprzedaży subskrypcji są wybierane na podstawie priorytetów przedstawionych w poniższej tabeli. Pusta komórka w tabeli wskazuje puste pole, a znak X wskazuje wartość równą wartości określonej w subskrypcji, na podstawie której jest generowana transakcja.

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Priorytet </p></th>
<th><p><strong>Kategoria</strong></p></th>
<th><p><strong>Identyfikator projektu</strong></p></th>
<th><p><strong>Subskrypcja</strong></p></th>
<th><p><strong>Waluta sprzedaży</strong></p></th>
<th><p><strong>Kod okresu</strong></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>6</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>


Podczas tworzenia opłaty subskrypcji jako cena sprzedaży subskrypcji jest wybierana cena sprzedaży o najwyższym poziomie szczegółowości, zgodnie z powyższą tabelą.

## <a name="update-and-index-subscription-sales-prices"></a>Aktualizacja i subskrypcje indeksu cen sprzedaży

Cenę sprzedaży subskrypcji można zaktualizować przez aktualizację ceny podstawowej lub indeksu. Aktualizacja polega na określeniu procentu lub nowej wartości.

## <a name="subscription-fee-sales-prices"></a>Ceny sprzedaży dla opłaty subskrypcji

W przypadku tworzenia opłaty subskrypcji cena sprzedaży jest ustalana na podstawie konfiguracji cen sprzedaży subskrypcji. Można użyć ceny podstawowej z konfiguracji ceny sprzedaży subskrypcji lub utworzyć indeksowane ceny sprzedaży.

## <a name="example"></a>Przykład

Chcesz skonfigurować cenę sprzedaży subskrypcji równą 500 euro dla nowego projektu 9030. W formularzu **Cena sprzedaży — subskrypcja** tworzy się wiersz ceny sprzedaży subskrypcji w sposób przedstawiony w tabeli poniżej.

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Obowiązuje od</p></th>
<th><p>Kategoria</p></th>
<th><p>Project</p></th>
<th><p>Subskrypcja</p></th>
<th><p>Kod okresu</p></th>
<th><p>Waluta sprzedaży</p></th>
<th><p>Cena sprzedaży</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28-08-2006</p></td>
<td></td>
<td><p>9030</p></td>
<td></td>
<td><p>Miesiąc</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


Należy zauważyć, że pola **Kategoria** i **Subskrypcja** są puste.

Następnie tworzysz poniższe subskrypcje:

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Subskrypcja serwisu</p></th>
<th><p>Project</p></th>
<th><p>Grupa subskrypcji</p></th>
<th><p>Kategoria</p></th>
<th><p>Waluta</p></th>
<th><p>Kod okresu</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>00020_135</p></td>
<td><p>9030</p></td>
<td><p>Sub1</p></td>
<td><p>KatSub1</p></td>
<td><p>EUR</p></td>
<td><p>Miesięczna</p></td>
</tr>
<tr class="even">
<td><p>00021_135</p></td>
<td><p>9030</p></td>
<td><p>Sub1</p></td>
<td><p>KatSub2</p></td>
<td><p>EUR</p></td>
<td><p>Miesięczna</p></td>
</tr>
</tbody>
</table>


Teraz tworzysz opłaty subskrypcji dla obu subskrypcji w grupie subskrypcji Sub1:

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Subskrypcje serwisowe** \> **Grupy subskrypcji**.

2.  W formularzu **Grupy subskrypcji** kliknij kolejno opcje **Funkcja** \> **Utwórz opłatę subskrypcji**.

3.  W formularzu **Utwórz opłatę subskrypcji** wprowadź odpowiednie informacje. Aby uzyskać więcej informacji, zobacz [Tworzenie transakcji opłat subskrypcji](create-subscription-fee-transactions.md).

Opłaty subskrypcyjne, których cena sprzedaży wynosi 500 euro, są tworzone dla obu subskrypcji, jak pokazano w tabeli poniżej.

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Data projektu</p></th>
<th><p>Subskrypcja serwisu</p></th>
<th><p>Project</p></th>
<th><p>Kategoria</p></th>
<th><p>Rozpoczęcie</p></th>
<th><p>Data końcowa</p></th>
<th><p>Waluta sprzedaży</p></th>
<th><p>Cena sprzedaży</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28-08-2006</p></td>
<td><p>00020_135</p></td>
<td><p>9030</p></td>
<td><p>KatSub1</p></td>
<td><p>01-01-2007</p></td>
<td><p>31-03-2007</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
<tr class="even">
<td><p>28-08-2006</p></td>
<td><p>00021_135</p></td>
<td><p>9030</p></td>
<td><p>KatSub2</p></td>
<td><p>01-01-2007</p></td>
<td><p>31-03-2007</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


Następnie decydujesz się określić ceny sprzedaży dla kategorii KatSub1 i projektu 9030. Dlatego tworzysz nowy wiersz ceny sprzedaży z ceną sprzedaży 550 euro dla kombinacji projektu 9030 i kategorii opłaty KatSub1. Dla projektu 9030 są teraz dwa wiersze ceny sprzedaży subskrypcji, jak widać w tabeli poniżej:

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Obowiązuje od</p></th>
<th><p>Kategoria</p></th>
<th><p>Project</p></th>
<th><p>Subskrypcja</p></th>
<th><p>Kod okresu</p></th>
<th><p>Waluta</p></th>
<th><p>Cena sprzedaży</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28-08-2007</p></td>
<td></td>
<td><p>9030</p></td>
<td></td>
<td><p>Miesiąc</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
<tr class="even">
<td><p>28-08-2007</p></td>
<td><p>KatSub1</p></td>
<td><p>9030</p></td>
<td></td>
<td><p>Miesiąc</p></td>
<td><p>EUR</p></td>
<td><p>550</p></td>
</tr>
</tbody>
</table>


Powtarzasz procedurę opisaną powyżej w celu utworzenia opłat subskrypcji dla obu subskrypcji w grupie subskrypcji Sub1. Tabela poniżej pokazuje transakcje, które są tworzone dla każdej subskrypcji dołączonej do grupy subskrypcji:

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Data projektu</p></th>
<th><p>Subskrypcja</p></th>
<th><p>Project</p></th>
<th><p>Kategoria</p></th>
<th><p>Rozpoczęcie</p></th>
<th><p>Data zakończenia</p></th>
<th><p>Waluta sprzedaży</p></th>
<th><p>Cena sprzedaży</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28-07-2007</p></td>
<td><p>00020_135</p></td>
<td><p>9030</p></td>
<td><p>KatSub1</p></td>
<td><p>01-01-2008</p></td>
<td><p>31-03-2008</p></td>
<td><p>EUR</p></td>
<td><p>550</p></td>
</tr>
<tr class="even">
<td><p>28-07-2008</p></td>
<td><p>00021_135</p></td>
<td><p>9030</p></td>
<td><p>KatSub2</p></td>
<td><p>01-01-2008</p></td>
<td><p>31-03-2008</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


W pierwszej transakcji — dla subskrypcji 00020\_135 — cena sprzedaży 550 euro została ustalona na podstawie cen sprzedaży subskrypcji skonfigurowanej dla kombinacji określonego projektu i kategorii. W drugiej transakcji — dla subskrypcji 00021\_135 — cena sprzedaży 500 euro została ustalona jako cena sprzedaży subskrypcji projektu, ponieważ nie ma skonfigurowanej ceny dla kombinacji projektu 9030 i kategorii KatSub2.

## <a name="see-also"></a>Informacje dodatkowe

[Aktualizacja i subskrypcje indeksu cen sprzedaży](update-and-index-subscription-sales-prices.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]