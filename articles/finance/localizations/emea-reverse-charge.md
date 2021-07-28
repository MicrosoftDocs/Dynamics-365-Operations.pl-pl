---
title: Mechanizm opłaty zwrotnej dla schematu VAT/GST
description: W tym temacie opisano, jak skonfigurować odwrócony podatek od towarów i usług (VAT) dla krajów europejskich i Arabii Saudyjskiej i Singapurze.
author: epodkolz
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Saudi Arabia, Spain, Sweden, United Kingdom, Singapore, Bahrain, Kuwait, Oman, Qatar
ms.author: epodkolz
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: a537509fe034d85f8f4f441dc82d54efd3ed4f28
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6348889"
---
# <a name="reverse-charge-mechanism-for-vatgst-scheme"></a>Mechanizm opłaty zwrotnej dla schematu VAT/GST

[!include [banner](../includes/banner.md)]

W tym temacie opisano generalne podejście dotyczące konfigurowania funkcji opłaty zwrotnej dla krajów/regionów, które przyjmują schematy VAT lub GST.
                                                                                 
Dostęp w kraju/regionie do tych funkcji jest zarządzany przez następujące funkcje w obszarze roboczym **Zarządzanie funkcjami**.

| Funkcja                                              | Kraj/region                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Brak określonej funkcji                                | Austria </br>Belgia </br>Bułgaria </br>Chorwacja </br>Cypr </br>Czechy </br>Dania  </br>Estonia  </br>Finlandia  </br>Francja  </br>Niemcy  </br>Węgry  </br>Islandia  </br>Irlandia  </br>Włochy  </br>Łotwa  </br>Liechtenstein  </br>Litwa  </br>Luksemburg  </br>Holandia  </br>Norwegia Polska </br>Portugalia </br>Rumunia  </br>Arabia Saudyjska </br>Singapur  </br>Słowacja  </br>Słowenia  </br>Hiszpania  </br>Szwecja  </br>Szwajcaria  </br>Wielka Brytania  </br>Zjednoczone Emiraty Arabskie |
| Opłata zwrotna dla dodatkowych krajów            | Bahrajn  </br>Kuwejt  </br>Oman  </br>Katar                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Włącz mechanizm opłaty zwrotnej dla schematu podatku VAT/GST | Wszystkie pozostałe kraje/regiony, z wyjątkiem:  </br>Brazylia  </br>Indie  </br>Rosja                                                                                                                                                                                                                                                                                                                                                                                         |
 
 Więcej informacji zawiera sekcja [Włączanie mechanizmu opłaty zwrotnej dla systemu VAT/GST](#enable-reverse-charge) w dalszej części tego tematu.

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

## <a name="set-up-sales-tax-groups-and-item-sales-tax-groups"></a><a name="sales-tax-item-sales-tax-groups"></a>Konfigurowanie grup podatków i grup podatków dla towarów
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

## <a name="set-up-reverse-charge-item-groups"></a><a name="reverse-charge-item-group"></a>Konfigurowanie towarów sprzedawanych z opłatą zwrotną
Na stronie **Grupy towarów sprzedawanych z opłatą zwrotną** (**Podatek** &gt; **Ustawienia** &gt; **Podatek** &gt; **Grupy towarów sprzedawanych z opłatą zwrotną**) można zdefiniować grupy produktów lub usług albo pojedyncze produkty lub usługi, do których będzie stosowany podatek odwrócony. Dla każdej grupy towarów z podatkiem odwróconym utwórz listę towarów, grup towarów i kategorii do sprzedaży i/lub zakupów.

## <a name="set-up-reverse-charge-rules"></a><a name="reverse-charge-rules"></a>Konfigurowanie reguł podatku odwróconego
Na stronie **Reguły opłaty zwrotnej** (**Podatek** &gt; **Ustawienia** &gt; **Podatek** &gt; **Reguły opłaty zwrotnej**) można zdefiniować reguły stosowania do transakcji zakupu i sprzedaży. Można skonfigurować cały zbiór reguł stosowania podatku odwróconego. Dla każdej reguły ustaw następujące pola:

- **Typ dokumentu** — Zaznacz opcję **Zamówienie zakupu**, **Arkusz faktur od dostawców**, **Zamówienie sprzedaży**, **Faktura niezależna**, **Arkusz faktur dla odbiorcy** i/lub **Faktura dostawcy**.
- **Typ kraju/regionu partnera** — Zaznacz opcję **Krajowe**, **UE**, **GCC** lub **Zagraniczny**. Alternatywnie jeśli regułę można zastosować do wszystkich partnerów handlowych, niezależnie od kraju lub regionu w adresie, zaznacz opcję **Wszystko**.
- **Krajowy adres dostawy** — Zaznaczenie tego pola wyboru spowoduje stosowanie reguły do dostaw w tym samym kraju lub regionie. Tego pola wyboru nie można zaznaczyć dla typów dokumentów **Arkusz faktur od dostawców** i **Arkusz faktur dla odbiorcy**.
- **Grupa pozycji sprzedawanych z opłatą zwrotną** — Zaznacz grupę, do której można stosować regułę.
- **Kwota progowa** — Schemat podatku odwróconego jest stosowany do faktury tylko wtedy, gdy wartość towarów i/lub usług należących do grupy towarów objętych podatkiem odwróconym przekracza limit określony w tym miejscu.

Można również użyć pól **Data wprowadzenia** i **Data ważności**, aby zdefiniować okres, w którym reguła obowiązuje.

Ponadto można określić, czy po spełnieniu warunku dla tego wiersza dokumentu będzie wyświetlane powiadomienie, a wiersz dokumentu będzie aktualizowany o domyślną grupę podatku z podatkiem odwróconym. Dostępne są następujące opcje:

- **Brak** — Wiersz dokumentu nie jest aktualizowany.
- **Monituj** — Jest wyświetlane powiadomienie potwierdzające, że można zastosować podatek odwrócony.
- **Ustaw** — Wiersz dokumentu jest aktualizowany bez dodatkowego powiadamiania.

## <a name="set-up-countryregion-properties"></a><a name="Set-up-Country/region-properties"></a>Ustawianie właściwości kraju/regionu
Na stronie **Parametry handlu zagranicznego** (**Podatek** &gt; **Konfiguracja** &gt; **Podatek od sprzedaży** &gt; **Handel zagraniczny** &gt; **Parametry handlu zagranicznego**) na karcie **Właściwości kraju/regionu** ustaw kraj/region bieżącej osoby prawnej na wartość *Krajowa*. Ustawianie **kraju/regionu** w UE, dla kraju/regionu UE który uczestniczy w handlu wewnątrz UE z aktualną firmą, jako *UE*. Ustawianie **kraju/regionu** w GCC, dla kraju/regionu GCC który uczestniczy w handlu wewnątrz UE z aktualną firmą, jako *GCC*.

## <a name="set-up-default-parameters"></a>Konfigurowanie parametrów domyślnych
Aby włączyć funkcję opłaty zwrotnej VAT, na stronie **Parametry księgi głównej** na karcie **Opłata zwrotna** w opcji **Włącz opłatę zwrotną** zaznacz wartość **Tak**. W polach **Grupa podatków dla zamówienia zakupu** i **Grupa podatków dla zamówienia sprzedaży** zaznacz domyślne grupy podatków. Jeśli jest spełniony warunek zastosowania podatku odwróconego, wiersz zamówienia zakupu lub sprzedaży jest aktualizowany o te grupy podatków.

## <a name="reverse-charge-on-a-sales-invoice"></a><a name="reverse-charge-sale"></a>Podatek odwrócony w fakturze sprzedaży
W sprzedaży objętej schematem podatku odwróconego sprzedawca nie nalicza podatku VAT. Zamiast tego faktura wskazuje towary podlegające odwróconemu podatkowi VAT i sumę podatku VAT w odwróceniu.

Podczas księgowania faktury sprzedaży zawierającej podatek odwrócony transakcje podatkowe mają kierunek podatku **Podatek należny** i zerową wartość podatku, a pola wyboru **Opłata zwrotna** oraz **Wyłączone** są zaznaczone.

## <a name="reverse-charge-on-a-purchase-invoice"></a><a name="reverse-charge-purchase"></a>Podatek odwrócony w fakturze zakupu
W zakupach w schemacie podatku odwróconego nabywca, który otrzymuje fakturę zawierającą podatek odwrócony, na potrzeby księgowania podatku VAT występuje jako nabywca i sprzedawca.

Podczas księgowania faktury zakupu zawierającej podatek odwrócony są tworzone dwie transakcje podatku. Jedna transakcja ma kierunek podatku **Podatek naliczony**. Druga transakcja ma kierunek podatku **Podatek należny**, a pole wyboru **Opłata zwrotna** jest zaznaczone.

Na zrzucie ekranu poniżej jedna transakcja ma kierunek **Podatek naliczony**, a druga transakcja ma kierunek jest **Podatek należny**. 

![Zaksięgowany podatek.](media/apac-sau-posted-sales-tax.png)

## <a name="enable-reverse-charge-mechanism-for-vatgst-scheme-feature"></a><a name="enable-reverse-charge"></a>Włącz funkcję Mechanizm opłaty zwrotnej dla schematu podatku VAT/GST
W obszarze roboczym **Zarządzanie funkcjami** znajdź funkcję i wybierz opcję **Włącz**.

Po włączeniu tej funkcji karta **Opłata zwrotna** jest dostępna we wszystkich firmach. Włącz funkcję opłaty zwrotnej dla firmy, ustawiając opcję **Włącz opłatę zwrotną** na **Tak**.

Dostępne będą następujące strony i elementy menu związane z konfiguracją funkcji:
 - **Grupy towarów sprzedawanych z opłatą zwrotną** (**Podatek** > **Konfiguracja** > **Podatek** > **Grupy towarów sprzedawanych z opłatą zwrotną**). Więcej informacji zawiera sekcja [Konfigurowanie grup towarów sprzedawanych z opłatą zwrotną](#reverse-charge-item-group).
 - **Reguły opłaty zwrotnej**  (**Podatek** > **Konfiguracja** > **Podatek** > **Reguły opłaty zwrotnej**). Patrz [Konfigurowanie reguł podatku odwróconego](#reverse-charge-rules).
 - **Parametry handlu zagranicznego** (**Podatek** > **Konfiguracja** > **Podatek** > **Handel zagraniczny** > **Parametry handlu zagranicznego**). Patrz [Ustawianie właściwości kraju/regionu](#Set-up-Country/region-properties).

Pole wyboru **Opłata zwrotna** będzie dostępne dla stron **Grupa podatków** i **Zaksięgowany podatek**. Więcej informacji zawierają sekcje, [Konfigurowanie grup podatków i grup podatków dla towarów](#sales-tax-item-sales-tax-groups), [Podatek odwrócony w fakturze sprzedaży](#reverse-charge-sale) i [Podatek odwrócony w fakturze zakupu](#reverse-charge-purchase).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]