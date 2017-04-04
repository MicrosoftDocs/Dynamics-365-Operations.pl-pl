---
title: "Przegląd rozliczenia"
description: "Ten artykuł zawiera ogólne informacje o procesie rozliczania. Opisano w nim typy transakcji, które można rozliczać, czas i metody rozliczania transakcji oraz wyniki procesu rozliczania."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14551
ms.assetid: 0968fa71-5984-415b-8689-759a0136d5d1
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: adbfa6f99c481129e8cbf4a2dc4b23b4be1e8b34
ms.lasthandoff: 03/31/2017


---

# <a name="settlement-overview"></a>Przegląd rozliczenia

Ten artykuł zawiera ogólne informacje o procesie rozliczania. Opisano w nim typy transakcji, które można rozliczać, czas i metody rozliczania transakcji oraz wyniki procesu rozliczania.

Podczas rozliczania transakcje w jednym dokumencie są stosowane do transakcji z innego dokumentu w celu zwiększenia lub zmniejszenia salda każdego dokumentu. Na przykład płatność może być rozliczana z fakturą. Różnych typów transakcji mogą zostać rozliczone w różnym czasie i za pomocą różnych metod. Rozliczenie może również spowodować wygenerowanie nowych transakcji.

## <a name="what-transactions-can-be-settled"></a>Jakie transakcje można rozliczyć
Rozliczenia w ramach rozrachunków z dostawcami i rozrachunków z odbiorcami mogą występować między wszystkimi typami transakcji, które mają wpływ na salda dostawcy lub salda odbiorcy (np. faktury, płatności, faktury korygujące i opłaty). Dowolny typ transakcji może zostać rozliczony względem innych typów transakcji. Na przykład można rozliczyć płatność dla faktury, fakturę korygującą dla faktury, fakturę dla faktury i płatności dla płatności. Można rozliczyć płatności dla transakcji w tej samej firmie lub w innej firmie. W organizacjach, które używają modelu płatności scentralizowanych [scentralizowane płatności](set-up-centralized-payments.md) może pomóc uprościć proces płatności.

## <a name="when-to-settle-transactions"></a>Kiedy rozliczać transakcje
Transakcje można rozliczyć w momencie wpisu płatności. Na przykład, płacąc odbiorcy zazwyczaj zaznacza się fakturę do zapłacenia. Po wybraniu faktury, możesz oznaczyć je do rozliczenia w zamian za zapłatę. Gdy urzędnicy płatności rozrachunków z odbiorcami zapisywana jest płatność odbiorcy, mogą one znak odpowiednie faktury do rozliczenia, na podstawie informacji dołączonej do odbiorcy płatności. Na stornie **Rozliczenia transakcji** można oznaczyć transakcje do rozliczenia. Tę stronę można otworzyć z dowolnej niezaksięgowanej faktury lub płatności. Kiedy transakcja jest księgowana, rozliczenie jest również księgowane. Transakcje mogą również być rozliczane po zaksięgowaniu. Można wprowadzać i zaksięgować płatność odbiorcy bez rozliczania jej względem wszystkich faktur. Czasami trzeba jednak wykonać sprawdzenie, by mieć pewność, że płatność jest rozliczana względem właściwej faktury. Stronę **Rozliczanie transakcji** można otworzyć ze strony **Wszyscy odbiorcy** lub **Wszyscy dostawcy** lub ze strony **Transakcje** dla dowolnego odbiorcy lub dostawcy. Można też zarezerwować zaksięgowane przedpłaty za faktury poprzez zaznaczenie płatności dla rozliczeń za zamówienia zakupu lub zamówienia sprzedaży. W takim przypadku płatności będzie jeszcze bilans otwarcia, ale nie można rozliczyć faktury innego. Płatność będzie automatycznie rozliczona faktura, utworzony na podstawie zamówienia zakupu lub zamówienia sprzedaży.

## <a name="how-to-settle-transactions"></a>Jak rozliczać transakcje
Transakcje mogą zostać rozliczane ręcznie, automatycznie lub używając jednej z dwóch metod. Wybór metody rozliczenia zależy od procesów biznesowych, które następnie można wdrożyć przez ustawienie rozliczania w Parametrach modułu rozrachunków z dostawcami i Parametrach modułu rozrachunków z odbiorcami. Można utworzyć płatności dostawcy i płatności odbiorcy poleceniem zapłaty za pomocą propozycji płatności, które służą do wyboru faktur do zapłaty. Propozycja płatności jest inicjowane ręcznie, ale następnie Microsoft Dynamics 365 dla operacji automatycznie znaki wybrane faktury do rozliczenia podczas tworzenia płatności. Jeśli płatności zostały utworzone ręcznie, możesz użyć strony **Rozlicz transakcje**, aby wybrać faktury do rozliczenia. Możesz ręcznie wybrać faktury lub skorzystać z opcji **Oznacz według priorytetu**, aby faktury były zaznaczane automatycznie do rozliczenia. Opcja **Oznacz według priorytetu** jest dostępna tylko w przypadku Rozrachunków z odbiorcami. Aby włączyć tę opcję, należy użyć strony **Priorytet rozliczenia** w Parametrach modułu rozrachunków z odbiorcami. Jeśli pracownik zajmujący się płatnościami wprowadza płatność, ale nie rozlicza jej przed zaksięgowaniem, płatność może być rozliczana automatycznie. Można włączyć automatyczne rozliczanie w Parametry modułu rozrachunków z odbiorcami i parametrów rozrachunków z dostawcami. Użycie opcji automatycznego rozliczenia, można użyć kolejność rozliczenia wstępnie zdefiniowane, lub można zdefiniować własne priorytetu rozliczenia w parametrach modułu rozrachunków z odbiorcami. Ta funkcja jest dostępna tylko dla Rozrachunków z odbiorcami.

## <a name="results-of-settlement"></a>Wyniki rozliczania
Gdy transakcje są rozliczane niezapłacone saldo każdej z nich rośnie lub maleje. W typowym scenariuszu, w którym rozliczane są faktury i płatności, stan i saldo każdej transakcji jest aktualizowane zgodnie z następującymi zasadami:

-   Jeśli kwota płatności jest większa niż kwota faktury, saldo faktury jest zmniejszane do 0,00, a faktura jest zamykana. Płatność pozostaje otwarta, a saldo jest równe kwocie, o którą płatność przekracza kwotę faktury.
-   Jeśli kwota płatności jest mniejsza niż kwota faktury, saldo płatności jest zmniejszane do 0,00, a płatność jest zamykana. Faktura pozostaje otwarta, a saldo jest równe kwocie niedopłaty za fakturę.
-   Jeśli kwota płatności jest równa kwocie faktury, płatności i faktury są zamykane, a saldo obydwu wynosi 0,00.

Jeśli [płatności jest mniejsza od kwoty faktury](../accounts-payable/vendor-payments-partial-amount.md) z powodu rabatu gotówkowego, odpisu lub niedopłaty, faktura i płatność nadal mogą zostać zamknięte, w zależności od konfiguracji rozliczania w Parametrach modułu rozrachunków z dostawcami i Parametrach modułu rozrachunków z odbiorcami. Rozliczenie można również generować transakcje. Na przykład rozliczenie faktury i płatności może tworzyć rabat gotówkowy, zrealizowane dodatnie lub ujemne różnice kursowe, wprowadzania korekt podatku, odpisy lub różnice groszowe.


