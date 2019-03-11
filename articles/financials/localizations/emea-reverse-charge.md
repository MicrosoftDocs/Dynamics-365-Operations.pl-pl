---
title: Opłata zwrotna VAT
description: W tym temacie opisano, jak skonfigurować odwrócony podatek od towarów i usług (VAT) dla krajów europejskich i Arabii Saudyjskiej.
author: epodkolz
manager: AnnBe
ms.date: 04/05/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Saudi Arabia, Spain, Sweden, United Kingdom
ms.author: epodkolz
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 26f7f3f11408cac387c58a5345b566ac50ed426f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "371533"
---
# <a name="reverse-charge-vat"></a>Opłata zwrotna VAT


[!include [banner](../includes/banner.md)]


W tym temacie opisano standardową metodę konfigurowania odwróconego podatku od towarów i usług (VAT) dla Arabii Saudyjskiej i krajów europejskich.

Podatek odwrócony to schemat podatkowy, w którym odpowiedzialność za rozliczenie i sprawozdawczość podatku VAT jest przenoszona ze sprzedawcy na nabywcę towarów i/lub usług. W związku z tym odbiorcy towarów i/lub usług raportują w swoich deklaracjach VAT zarówno należny podatek VAT (w roli sprzedawcy), jak i naliczony podatek VAT (w roli nabywcy).

W niektórych krajach i regionach schemat podatku odwróconego jest implementowany tylko dla niektórych towarów i/lub usług oraz istnieją dodatkowe warunki lub progi dla kwot sprzedaży. W innych krajach i regionach odpowiedzialność za płatność podatku VAT zależy od statusu dostawcy i nabywcy. Jeśli kupujący podlega obowiązkowi płacenia podatku VAT, fakt ten musi być czytelnie wskazany na fakturze wystawianej przez dostawcę. Na przykład faktura musi zawierać słowa „Podatek odwrócony” oraz muszą być oznaczone pozycje podlegające odwróconemu podatkowi VAT. 

Aby zastosować podatek odwrócony, należy skonfigurować następujące ustawienia.

## <a name="set-up-sales-tax-codes"></a>Ustawianie kodów podatków
Zalecamy stosowanie oddzielnych kodów podatków dla operacji sprzedaży i zakupu.

<table>
<body>
<tr>
<td><strong>Kod podatku dla sprzedaży</strong></td>
<td>Utwórz kod podatku dla operacji sprzedaży z podatkiem odwróconym (<strong>Podatek</strong> &gt; <strong>Podatki pośrednie</strong> &gt; <strong>Podatek</strong> &gt; <strong>Kody podatków</strong>).
</td>
</tr>
<tr>
<td><strong>Kod podatku dla zakupów</strong></td>
<td><p>Utwórz kody podatków dodatnich i ujemnych dla odwróconego podatku VAT dla zakupów (<strong>Podatek</strong> &gt; <strong>Podatki pośrednie</strong> &gt; <strong>Podatek</strong> &gt; <strong>Kody podatków</strong>).</p>
<ol>
<li>Utwórz kod podatku o wartości dodatniej.</li>
<li>Utwórz kod podatku o wartości ujemnej. W opcji <strong>Zezwalaj na ujemny procent podatku</strong> ustaw wartość <strong>Tak</strong>.
Ten kod podatku ujemnego należy przypisać do grupy podatków od towarów, po czym przypisać tę grupę do towarów podlegających odwróconemu podatkowi VAT.</li>
</ol>
<p>Aby uzyskać więcej informacji, zobacz następną sekcję &quot;Konfigurowanie grup podatków i grup podatków dla towarów&quot;.</p>
</td>
</tr>
</tbody>
</table>

## <a name="set-up-sales-tax-groups-and-item-sales-tax-groups"></a>Konfigurowanie grup podatków i grup podatków dla towarów
Zalecamy stosowanie oddzielnych grup podatków dla operacji sprzedaży i zakupu.

<table>
<tr>
<td><strong>Grupy podatków dla sprzedaży</strong></td>
<td>Utwórz grupę podatków dla operacji sprzedaży objętych podatkiem odwróconym (<strong>Podatek</strong> &gt; <strong>Podatki pośrednie</strong> &gt; <strong>Podatek</strong> &gt; <strong>Grupy podatków</strong>). Na karcie <strong>Ustawienia</strong> podaj kod podatku dla podatku odwróconego w tej grupie. Zaznacz pola wyboru <strong>Zwolnienie</strong> i <strong>Opłata zwrotna</strong> dla kodu podatku.</td>
</tr>
<tr>
<td><strong>Grupy podatków dla zakupów</strong></td>
<td>Utwórz grupę podatków dla operacji zakupu objętych podatkiem odwróconym (<strong>Podatek</strong> &gt; <strong>Podatki pośrednie</strong> &gt; <strong>Podatek</strong> &gt; <strong>Grupy podatków</strong>). Na karcie <strong>Ustawienia</strong> wprowadź kody podatków dodatnich i ujemnych w tej grupie. Zaznacz pole wyboru <strong>Opłata zwrotna</strong> dla kodu podatku, który ma wartość ujemną.</td>
</tr>
<tr>
<td><strong>Grupy podatków dla towaru</strong></td>
<td>Utwórz lub zaktualizuj grupę podatków dla towaru z kodem podatku o wartości ujemnej (<strong>Podatek</strong> &gt; <strong>Podatki pośrednie</strong> &gt; <strong>Podatek</strong> &gt; <strong>Grupy podatków dla pozycji</strong>). Należy przypisać domyślną grupę podatków dla towaru do produktów i kategorii podlegających podatkowi odwróconemu.</td>
</tr>
</table>

## <a name="set-up-reverse-charge-groups"></a>Konfigurowanie grup podatku odwróconego
Na stronie **Grupy towarów sprzedawanych z opłatą zwrotną** (**Podatek** &gt; **Ustawienia** &gt; **Podatek** &gt; **Grupy towarów sprzedawanych z opłatą zwrotną**) można zdefiniować grupy produktów lub usług albo pojedyncze produkty lub usługi, do których będzie stosowany podatek odwrócony. Dla każdej grupy towarów z podatkiem odwróconym utwórz listę towarów, grup towarów i kategorii do sprzedaży i/lub zakupów.

## <a name="set-up-reverse-charge-rules"></a>Konfigurowanie reguł podatku odwróconego
Na stronie **Reguły opłaty zwrotnej** (**Podatek** &gt; **Ustawienia** &gt; **Podatek** &gt; **Reguły opłaty zwrotnej**) można zdefiniować reguły stosowania do transakcji zakupu i sprzedaży. Można skonfigurować cały zbiór reguł stosowania podatku odwróconego. Dla każdej reguły ustaw następujące pola:

- **Typ dokumentu** — Zaznacz opcję **Zamówienie zakupu**, **Arkusz faktur od dostawców**, **Zamówienie sprzedaży**, **Faktura niezależna**, **Arkusz faktur dla odbiorcy** i/lub **Faktura dostawcy**.
- **Typ kraju/regionu partnera** — Zaznacz opcję **Krajowe**, **UE** lub **Zagraniczny**. Alternatywnie jeśli regułę można zastosować do wszystkich partnerów handlowych, niezależnie od kraju lub regionu w adresie, zaznacz opcję **Wszystko**.
- **Krajowy adres dostawy** — Zaznaczenie tego pola wyboru spowoduje stosowanie reguły do dostaw w tym samym kraju lub regionie. Tego pola wyboru nie można zaznaczyć dla typów dokumentów **Arkusz faktur od dostawców** i **Arkusz faktur dla odbiorcy**.
- **Grupa pozycji sprzedawanych z opłatą zwrotną** — Zaznacz grupę, do której można stosować regułę.
- **Kwota progowa** — Schemat podatku odwróconego jest stosowany do faktury tylko wtedy, gdy wartość towarów i/lub usług należących do grupy towarów objętych podatkiem odwróconym przekracza limit określony w tym miejscu.

Można również użyć pól **Data wprowadzenia** i **Data ważności**, aby zdefiniować okres, w którym reguła obowiązuje.

Ponadto można określić, czy po spełnieniu warunku dla tego wiersza dokumentu będzie wyświetlane powiadomienie, a wiersz dokumentu będzie aktualizowany o domyślną grupę podatku z podatkiem odwróconym. Dostępne są następujące opcje:

- **Brak** — Wiersz dokumentu nie jest aktualizowany.
- **Monituj** — Jest wyświetlane powiadomienie potwierdzające, że można zastosować podatek odwrócony.
- **Ustaw** — Wiersz dokumentu jest aktualizowany bez dodatkowego powiadamiania.

## <a name="set-up-default-parameters"></a>Konfigurowanie parametrów domyślnych
Aby włączyć funkcję opłaty zwrotnej VAT, na stronie **Parametry księgi głównej** na karcie **Opłata zwrotna** w opcji **Włącz opłatę zwrotną** zaznacz wartość **Tak**. W polach **Grupa podatków dla zamówienia zakupu** i **Grupa podatków dla zamówienia sprzedaży** zaznacz domyślne grupy podatków. Jeśli jest spełniony warunek zastosowania podatku odwróconego, wiersz zamówienia zakupu lub sprzedaży jest aktualizowany o te grupy podatków.

## <a name="reverse-charge-on-a-sales-invoice"></a>Podatek odwrócony w fakturze sprzedaży
W sprzedaży objętej schematem podatku odwróconego sprzedawca nie nalicza podatku VAT. Zamiast tego faktura wskazuje towary podlegające odwróconemu podatkowi VAT i sumę podatku VAT w odwróceniu.

Podczas księgowania faktury sprzedaży zawierającej podatek odwrócony transakcje podatkowe mają kierunek podatku **Podatek należny** i zerową wartość podatku, a pole wyboru **Opłata zwrotna** jest zaznaczone.

## <a name="reverse-charge-on-a-purchase-invoice"></a>Podatek odwrócony w fakturze zakupu
W zakupach w schemacie podatku odwróconego nabywca, który otrzymuje fakturę zawierającą podatek odwrócony, na potrzeby księgowania podatku VAT występuje jako nabywca i sprzedawca.

Podczas księgowania faktury zakupu zawierającej podatek odwrócony są tworzone dwie transakcje podatku. Jedna transakcja ma kierunek podatku **Podatek naliczony**. Druga transakcja ma kierunek podatku **Podatek należny**, a pole wyboru **Opłata zwrotna** jest zaznaczone.

Na zrzucie ekranu poniżej jedna transakcja ma kierunek **Podatek naliczony**, a druga transakcja ma kierunek jest **Podatek należny**. 

![Zaksięgowany podatek](media/apac-sau-posted-sales-tax.png)
