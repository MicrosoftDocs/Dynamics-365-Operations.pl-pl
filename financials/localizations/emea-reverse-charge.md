---
title: "Odwrócony podatek VAT | Microsoft Docs"
description: "W tym temacie opisano, jak skonfigurować odwrócony podatek od towarów i usług (VAT) dla krajów europejskich."
author: epodkolz
manager: AnnBe
ms.date: 05/12/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epodkolz
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 6cb473962f40ed9ef2f5f807f089098764f47009
ms.openlocfilehash: b3c94fa73410d9bdcaaec11dee04a7a239e4d45a
ms.contentlocale: pl-pl
ms.lasthandoff: 06/14/2017

---

# Opłata zwrotna VAT
<a id="reverse-charge-vat" class="xliff"></a>
W tym temacie opisano standardową metodę konfigurowania odwróconego podatku od towarów i usług (VAT) dla krajów europejskich.

Podatek odwrócony to schemat podatkowy, w którym odpowiedzialność za rozliczenie i sprawozdawczość podatku VAT jest przenoszona ze sprzedawcy na nabywcę towarów i/lub usług. W związku z tym odbiorcy towarów i/lub usług raportują w swoich deklaracjach VAT zarówno należny podatek VAT (w roli sprzedawcy), jak i naliczony podatek VAT (w roli nabywcy).

Dyrektywa Unii Europejskiej (UE) umożliwia państwom członkowskim samodzielne decydowanie, jak chcą dostosować ogólne wymagania do swoich wymagań lokalnych. W związku z tym w niektórych krajach schemat podatku odwróconego jest implementowany tylko dla niektórych towarów i/lub usług oraz istnieją dodatkowe warunki lub progi dla kwot sprzedaży. W innych krajach odpowiedzialność za płatność podatku VAT zależy od statusu dostawcy i nabywcy. Jeśli kupujący podlega obowiązkowi płacenia podatku VAT, fakt ten musi być czytelnie wskazany na fakturze wystawianej przez dostawcę. Na przykład faktura musi zawierać słowa „Podatek odwrócony” oraz muszą być oznaczone pozycje podlegające odwróconemu podatkowi VAT. 

Aby zastosować podatek odwrócony, należy skonfigurować następujące ustawienia.

## Ustawianie kodów podatków
<a id="set-up-sales-tax-codes" class="xliff"></a>
Zalecamy stosowanie oddzielnych kodów podatków dla operacji zakupu i sprzedaży.

<table>
<body>
<tr>
<td><strong>Kod podatku dla sprzedaży</strong></td>
<td>Utwórz kod podatku dla operacji sprzedaży z podatkiem odwróconym (<strong>Podatek</strong> > <strong>Podatki pośrednie</strong> > <strong>Podatek</strong> > <strong>Kody podatków</strong>).
</td>
</tr>
<tr>
<td><strong>Kod podatku dla zakupów</strong></td>
<td><p>Utwórz kody podatków dodatnich i ujemnych dla odwróconego podatku VAT dla zakupów (<strong>Podatek</strong> > <strong>Podatki pośrednie</strong> > <strong>Podatek</strong> > <strong>Kody podatków</strong>).</p>
<ol>
<li>Utwórz kod podatku o wartości dodatniej.</li>
<li>Utwórz kod podatku o wartości ujemnej. W opcji <strong>Zezwalaj na ujemny procent podatku</strong> ustaw wartość <strong>Tak</strong>.
Ten kod podatku ujemnego należy przypisać do grupy podatków od towarów, po czym przypisać tę grupę do towarów podlegających odwróconemu podatkowi VAT.</li>
</ol>
<p>Aby uzyskać więcej informacji, zobacz następną sekcję „Konfigurowanie grup podatków i grup podatków dla towarów”.</p>
</td>
</tr>
</tbody>
</table>

## Konfigurowanie grup podatków i grup podatków dla towarów
<a id="set-up-sales-tax-groups-and-item-sales-tax-groups" class="xliff"></a>
Zalecamy stosowanie oddzielnych grup podatków dla operacji zakupu i sprzedaży.

<table>
<tr>
<td><strong>Grupy podatków dla sprzedaży</strong></td>
<td>Utwórz grupę podatków dla operacji sprzedaży objętych podatkiem odwróconym (<strong>Podatek</strong> > <strong>Podatki pośrednie</strong> > <strong>Podatek</strong> > <strong>Grupy podatków</strong>). Na karcie <strong>Ustawienia</strong> podaj kod podatku dla podatku odwróconego w tej grupie. Zaznacz pola wyboru <strong>Zwolnienie</strong> i <strong>Opłata zwrotna</strong> dla kodu podatku.</td>
</tr>
<tr>
<td><strong>Grupy podatków dla zakupów</strong></td>
<td>Utwórz grupę podatków dla operacji zakupu objętych podatkiem odwróconym (<strong>Podatek</strong> > <strong>Podatki pośrednie</strong> > <strong>Podatek</strong> > <strong>Grupy podatków</strong>). Na karcie <strong>Ustawienia</strong> wprowadź kody podatków dodatnich i ujemnych w tej grupie. Zaznacz pole wyboru <strong>Opłata zwrotna</strong> dla kodu podatku, który ma wartość ujemną.</td>
</tr>
<tr>
<td><strong>Grupy podatków dla towaru</strong></td>
<td>Utwórz lub zaktualizuj grupę podatków dla towaru z kodem podatku o wartości ujemnej (<strong>Podatek</strong> > <strong>Podatki pośrednie</strong> > <strong>Podatek</strong> > <strong>Grupy podatków dla pozycji</strong>). Należy przypisać domyślną grupę podatków dla towaru do produktów i kategorii podlegających podatkowi odwróconemu.</td>
</tr>
</table>

## Konfigurowanie grup podatku odwróconego
<a id="set-up-reverse-charge-groups" class="xliff"></a>
Na stronie **Grupy towarów sprzedawanych z opłatą zwrotną** (**Podatek** > **Ustawienia** > **Podatek** > **Grupy towarów sprzedawanych z opłatą zwrotną**) można zdefiniować grupy produktów lub usług albo pojedyncze produkty lub usługi, do których będzie stosowany podatek odwrócony. Dla każdej grupy towarów z podatkiem odwróconym utwórz listę towarów, grup towarów i kategorii do sprzedaży i/lub zakupów.

## Konfigurowanie reguł podatku odwróconego
<a id="set-up-reverse-charge-rules" class="xliff"></a>
Na stronie **Reguły opłaty zwrotnej** (**Podatek** > **Ustawienia** > **Podatek** > **Reguły opłaty zwrotnej**) można zdefiniować reguły stosowania do transakcji zakupu i sprzedaży. Można skonfigurować cały zbiór reguł stosowania podatku odwróconego. Dla każdej reguły ustaw następujące pola:

- **Typ dokumentu** — Zaznacz opcję **Zamówienie zakupu**, **Arkusz faktur od dostawców**, **Zamówienie sprzedaży**, **Faktura niezależna**, **Arkusz faktur dla odbiorcy** i/lub **Faktura dostawcy**.
- **Typ kraju/regionu partnera** — Zaznacz opcję **Krajowe**, **UE** lub **Zagraniczny**. Alternatywnie jeśli regułę można zastosować do wszystkich partnerów handlowych, niezależnie od kraju lub regionu w adresie, zaznacz opcję **Wszystko**.
- **Krajowy adres dostawy** — Zaznaczenie tego pola wyboru spowoduje stosowanie reguły do dostaw w tym samym kraju lub regionie. Tego pola wyboru nie można zaznaczyć dla typów dokumentów **Arkusz faktur od dostawców** i **Arkusz faktur dla odbiorcy**.
- **Grupa pozycji sprzedawanych z opłatą zwrotną** — Zaznacz grupę, do której można stosować regułę.
- **Kwota progowa** — Schemat podatku odwróconego jest stosowany do faktury tylko wtedy, gdy wartość towarów i/lub usług należących do grupy towarów objętych podatkiem odwróconym przekracza limit określony w tym miejscu.

Można użyć pól **Data wprowadzenia** i **Data ważności**, aby zdefiniować okres, w którym reguła obowiązuje.

Ponadto można określić, czy po spełnieniu warunku dla tego wiersza dokumentu będzie wyświetlane powiadomienie, a wiersz dokumentu będzie aktualizowany o domyślną grupę podatku z podatkiem odwróconym. Dostępne są następujące opcje:

- **Brak** — Wiersz dokumentu nie jest aktualizowany.
- **Monituj** — Jest wyświetlane powiadomienie potwierdzające, że można zastosować podatek odwrócony.
- **Ustaw** — Wiersz dokumentu jest aktualizowany bez dodatkowego powiadamiania.

## Konfigurowanie parametrów domyślnych
<a id="set-up-default-parameters" class="xliff"></a>
Aby włączyć tę funkcję, na stronie **Parametry księgi głównej** na karcie **Opłata zwrotna** w opcji **Włącz opłatę zwrotną** zaznacz wartość **Tak**. W polach **Grupa podatków dla zamówienia zakupu** i **Grupa podatków dla zamówienia sprzedaży** zaznacz domyślne grupy podatków. Jeśli jest spełniony warunek zastosowania podatku odwróconego, wiersz zamówienia zakupu lub sprzedaży jest aktualizowany o te grupy podatków.

## Podatek odwrócony w fakturze sprzedaży
<a id="reverse-charge-on-a-sales-invoice" class="xliff"></a>
W sprzedaży objętej schematem podatku odwróconego sprzedawca nie nalicza podatku VAT. Zamiast tego faktura wskazuje towary podlegające odwróconemu podatkowi VAT i sumę podatku VAT w odwróceniu.

Podczas księgowania faktury sprzedaży zawierającej podatek odwrócony transakcje podatkowe mają kierunek podatku **Podatek należny** i zerową wartość podatku, a pole wyboru **Opłata zwrotna** jest zaznaczone.

## Podatek odwrócony w fakturze zakupu
<a id="reverse-charge-on-a-purchase-invoice" class="xliff"></a>
W zakupach w schemacie podatku odwróconego nabywca, który otrzymuje fakturę zawierającą podatek odwrócony, na potrzeby księgowania podatku VAT występuje jako nabywca i sprzedawca.

Podczas księgowania faktury zakupu zawierającej podatek odwrócony są tworzone dwie transakcje podatku. Jedna transakcja ma kierunek podatku **Podatek naliczony**. Druga transakcja ma kierunek podatku **Podatek należny**, a pole wyboru **Opłata zwrotna** jest zaznaczone.

