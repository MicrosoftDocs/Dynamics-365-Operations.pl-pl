---
title: "Przegląd rozliczenia"
description: "Ten artykuł zawiera ogólne informacje o procesie rozliczania. Opisano w nim typy transakcji, które można rozliczać, czas i metody rozliczania transakcji oraz wyniki procesu rozliczania."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14551
ms.assetid: 0968fa71-5984-415b-8689-759a0136d5d1
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 298ac47e2253f8add1aa3938dda15afe186afbeb
ms.openlocfilehash: ab12ef4127daf57fb0816ae1585876b50d1e81ed
ms.contentlocale: pl-pl
ms.lasthandoff: 06/20/2017


---

# Przegląd rozliczenia
<a id="settlement-overview" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera ogólne informacje o procesie rozliczania. Opisano w nim typy transakcji, które można rozliczać, czas i metody rozliczania transakcji oraz wyniki procesu rozliczania.

Podczas rozliczania transakcje w jednym dokumencie są stosowane do transakcji z innego dokumentu w celu zwiększenia lub zmniejszenia salda każdego dokumentu. Na przykład płatność może być zastosowana do faktury. Różne typy transakcji mogą być rozliczane w różnym czasie i różnymi metodami. Rozliczenie może również spowodować wygenerowanie nowych transakcji.

## Jakie transakcje można rozliczyć
<a id="what-transactions-can-be-settled" class="xliff"></a>
Rozliczenia w ramach rozrachunków z dostawcami i rozrachunków z odbiorcami mogą występować między wszystkimi typami transakcji, które mają wpływ na salda dostawcy lub salda odbiorcy (np. faktury, płatności, faktury korygujące i opłaty). Dowolny typ transakcji może zostać rozliczony względem innych typów transakcji. Na przykład można rozliczyć płatność dla faktury, fakturę korygującą dla faktury, fakturę dla faktury i płatności dla płatności. Można rozliczyć płatności dla transakcji w tej samej firmie lub w innej firmie. W organizacjach, w których jest używany model płatności scentralizowanych, [płatności scentralizowane](set-up-centralized-payments.md) mogą pomóc uprościć proces płatności.

## Kiedy rozliczać transakcje
<a id="when-to-settle-transactions" class="xliff"></a>
Transakcje można rozliczyć w momencie wpisu płatności. Na przykład, płacąc odbiorcy zazwyczaj zaznacza się fakturę do zapłacenia. Wybierając faktury, można je oznaczyć do rozliczenia płatnością. Gdy pracownicy ds. płatności rozrachunków z odbiorcami rejestrują płatność odbiorcy, mogą oznaczyć odpowiednie faktury do rozliczenia na podstawie informacji dołączonej do płatności odbiorcy. Na stornie **Rozliczenia transakcji** można oznaczyć transakcje do rozliczenia. Tę stronę można otworzyć z dowolnej niezaksięgowanej faktury lub płatności. Kiedy transakcja jest księgowana, rozliczenie jest również księgowane. Transakcje mogą również być rozliczane po zaksięgowaniu. Można wprowadzać i zaksięgować płatność odbiorcy bez rozliczania jej względem wszystkich faktur. Czasami trzeba jednak wykonać sprawdzenie, by mieć pewność, że płatność jest rozliczana względem właściwej faktury. Stronę **Rozliczanie transakcji** można otworzyć ze strony **Wszyscy odbiorcy** lub **Wszyscy dostawcy** lub ze strony **Transakcje** dla dowolnego odbiorcy lub dostawcy. Można też zarezerwować zaksięgowane przedpłaty za faktury poprzez zaznaczenie płatności dla rozliczeń za zamówienia zakupu lub zamówienia sprzedaży. W takim przypadku płatność będzie nadal miała otwarte saldo, ale nie będzie można jej rozliczyć względem innej faktury. Płatność będzie automatycznie rozliczana względem faktury utworzonej na podstawie zamówienia zakupu lub zamówienia sprzedaży.

## Jak rozliczać transakcje
<a id="how-to-settle-transactions" class="xliff"></a>
Transakcje mogą zostać rozliczane ręcznie, automatycznie lub używając jednej z dwóch metod. Wybór metody rozliczenia zależy od procesów biznesowych, które następnie można wdrożyć przez ustawienie rozliczania w Parametrach modułu rozrachunków z dostawcami i Parametrach modułu rozrachunków z odbiorcami. Można utworzyć płatności dostawcy i płatności odbiorcy poleceniem zapłaty za pomocą propozycji płatności, które służą do wyboru faktur do zapłaty. Propozycja płatności jest inicjowana ręcznie, a następnie program Microsoft Dynamics 365 for Finance and Operations automatycznie oznacza wybrane faktury do rozliczenia podczas tworzenia płatności. Jeśli płatności zostały utworzone ręcznie, możesz użyć strony **Rozlicz transakcje**, aby wybrać faktury do rozliczenia. Możesz ręcznie wybrać faktury lub skorzystać z opcji **Oznacz według priorytetu**, aby faktury były zaznaczane automatycznie do rozliczenia. Opcja **Oznacz według priorytetu** jest dostępna tylko w przypadku Rozrachunków z odbiorcami. Aby włączyć tę opcję, należy użyć strony **Priorytet rozliczenia** w Parametrach modułu rozrachunków z odbiorcami. Jeśli pracownik zajmujący się płatnościami wprowadza płatność, ale nie rozlicza jej przed zaksięgowaniem, płatność może być rozliczana automatycznie. Można włączyć automatyczne rozliczanie w Parametrach modułu rozrachunków z odbiorcami i Parametrach modułu rozrachunków z dostawcami. W przypadku zastosowania opcji automatycznego rozliczenia można użyć wstępnie zdefiniowanej kolejności rozliczania lub można zdefiniować własną kolejność w oknie Parametry modułu rozrachunków z odbiorcami. Ta funkcja jest dostępna tylko dla Rozrachunków z odbiorcami.

## Wyniki rozliczania
<a id="results-of-settlement" class="xliff"></a>
Gdy transakcje są rozliczane niezapłacone saldo każdej z nich rośnie lub maleje. W typowym scenariuszu, w którym rozliczane są faktury i płatności, stan i saldo każdej transakcji jest aktualizowane zgodnie z następującymi zasadami:

-   Jeśli kwota płatności jest większa niż kwota faktury, saldo faktury jest zmniejszane do 0,00, a faktura jest zamykana. Płatność pozostaje otwarta, a saldo jest równe kwocie, o którą płatność przekracza kwotę faktury.
-   Jeśli kwota płatności jest mniejsza niż kwota faktury, saldo płatności jest zmniejszane do 0,00, a płatność jest zamykana. Faktura pozostaje otwarta, a saldo jest równe kwocie niedopłaty za fakturę.
-   Jeśli kwota płatności jest równa kwocie faktury, płatności i faktury są zamykane, a saldo obydwu wynosi 0,00.

Jeśli [płatności jest mniejsza od kwoty faktury](../accounts-payable/vendor-payments-partial-amount.md) z powodu rabatu gotówkowego, odpisu lub niedopłaty, faktura i płatność nadal mogą zostać zamknięte, w zależności od konfiguracji rozliczania w Parametrach modułu rozrachunków z dostawcami i Parametrach modułu rozrachunków z odbiorcami. Rozliczenie można również generować transakcje. Na przykład rozliczenie faktury i płatności może tworzyć rabat gotówkowy, zrealizowane dodatnie lub ujemne różnice kursowe, wprowadzania korekt podatku, odpisy lub różnice groszowe.




