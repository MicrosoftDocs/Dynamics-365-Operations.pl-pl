---
title: Omówienie rozliczeń
description: Ten temat zawiera ogólne informacje o procesie rozliczania. Opisano w nim typy transakcji, które można rozliczyć, oraz czas i proces ich rozliczania. Przedstawia on także wyniki procesu rozliczania.
author: kweekley
ms.date: 04/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "14551"
- intro-internal
ms.assetid: 0968fa71-5984-415b-8689-759a0136d5d1
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: a4950c4276fb862bcbf82e489ea3313a92e0515a
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/03/2021
ms.locfileid: "6336076"
---
# <a name="settlement-overview"></a>Omówienie rozliczeń

[!include [banner](../includes/banner.md)]

Ten temat zawiera ogólne informacje o procesie rozliczania. Opisano w nim typy transakcji, które można rozliczyć, oraz czas i proces ich rozliczania. Przedstawia on także wyniki procesu rozliczania.

Podczas rozliczania transakcje w jednym dokumencie są stosowane do transakcji z innego dokumentu w celu zwiększenia lub zmniejszenia salda każdego dokumentu. Na przykład płatność może być zastosowana do faktury. Różne typy transakcji mogą być rozliczane w różnym czasie i za pośrednictwem różnych metod. Proces rozliczania może również spowodować wygenerowanie nowych transakcji.

## <a name="what-transactions-can-be-settled"></a>Jakie transakcje można rozliczyć

W modułach rozrachunków z dostawcami i rozrachunków z odbiorcami mogą występować rozliczenia między wszystkimi typami transakcji, które mają wpływ na salda dostawcy lub salda odbiorcy. Te typy transakcji mogą obejmować faktury, płatności, faktury korygujące i opłaty. Dowolny typ transakcji może zostać rozliczony względem innych typów transakcji. Na przykład można rozliczyć płatność dla faktury, fakturę korygującą dla faktury, fakturę dla innej faktury i płatności dla innej płatności.

Można rozliczyć płatności dla transakcji w tej samej firmie lub w innej firmie. W organizacjach, w których jest używany model płatności scentralizowanych, [płatności scentralizowane](set-up-centralized-payments.md) mogą pomóc uprościć proces płatności.

## <a name="when-to-settle-transactions"></a>Kiedy rozliczać transakcje

Transakcje mogą być rozliczane podczas wprowadzania płatności. Na przykład płacąc dostawcy, zazwyczaj wybierasz faktury do zapłacenia. Wybierając faktury, można je oznaczyć do rozliczenia płatnością. Gdy pracownicy ds. płatności rozrachunków z odbiorcami rejestrują płatności klienta, mogą oznaczyć odpowiednie faktury do rozliczenia na podstawie informacji dołączonych do poszczególnych płatności odbiorcy. Transakcje do rozliczenia można oznaczyć na stronie **Rozliczenia transakcji**. Możesz otworzyć tę stronę z dowolnej niezaksięgowanej faktury lub płatności. Kiedy transakcja jest księgowana, rozliczenie jest również księgowane. 

Transakcje mogą również być rozliczane po zaksięgowaniu. Można wprowadzać i zaksięgować płatność odbiorcy bez rozliczania jej względem wszystkich faktur. Czasami możesz wykonać sprawdzenie, aby mieć pewność, że płatność jest rozliczana względem właściwej faktury, przed zaksięgowaniem rozliczenia. Stronę **Rozliczanie transakcji** można otworzyć ze strony **Wszyscy odbiorcy** lub **Wszyscy dostawcy** lub ze strony **Transakcje** dla dowolnego odbiorcy lub dostawcy.

Można też zarezerwować zaksięgowane przedpłaty za faktury poprzez zaznaczenie płatności dla rozliczeń za zamówienia zakupu lub zamówienia sprzedaży. W takim przypadku płatność będzie nadal miała otwarte saldo, ale nie będzie można jej rozliczyć względem innej faktury. Płatność będzie automatycznie rozliczana względem faktury utworzonej na podstawie zamówienia zakupu lub zamówienia sprzedaży.

## <a name="how-to-settle-transactions"></a>Jak rozliczać transakcje

Transakcje mogą zostać rozliczane ręcznie, automatycznie lub używając jednej z dwóch metod. Wybór metody rozliczania zależy od procesów biznesowych. Na stronach **Parametry rozrachunków z dostawcami** i **Parametry rozrachunków z odbiorcami** można skonfigurować proces rozliczania, tak aby był zgodny z tymi procesami biznesowymi.

Można utworzyć płatności dostawcy i płatności odbiorcy poleceniem zapłaty za pomocą propozycji płatności. Propozycja płatności jest używana do wybierania faktur do zapłacenia. Propozycja płatności jest uruchamiana ręcznie, a następnie system automatycznie oznacza wybrane faktury do rozliczenia podczas tworzenia płatności.

Jeśli płatności zostały utworzone ręcznie, możesz użyć strony **Rozlicz transakcje**, aby wybrać faktury do rozliczenia. Możesz ręcznie wybrać faktury lub skorzystać z opcji **Oznacz według priorytetu**, aby faktury były zaznaczane automatycznie do rozliczenia. Opcja **Oznacz według priorytetu** jest dostępna tylko w przypadku Rozrachunków z odbiorcami. Tę opcję można włączyć na karcie **Priorytet rozliczenia** na stronie **Parametry rozrachunków z odbiorcami**.

Jeśli pracownik zajmujący się płatnościami wprowadza płatność, ale nie rozlicza jej przed zaksięgowaniem, płatność może być rozliczana automatycznie. Można włączyć automatyczne rozliczanie na stronach **Parametry rozrachunków z odbiorcami** i **Parametry rozrachunków z dostawcami**. Rozliczenie automatyczne polega na rozliczaniu transakcji tylko w tej samej firmie. Nie obejmuje ono rozliczania transakcji między wieloma firmami.

W przypadku zastosowania opcji automatycznego rozliczenia można użyć wstępnie zdefiniowanego priorytetu rozliczania lub można zdefiniować własny priorytet rozliczenia w oknie **Parametry rozrachunków z odbiorcami**. Ta funkcja jest dostępna tylko dla Rozrachunków z odbiorcami.

## <a name="results-of-settlement"></a>Wyniki rozliczania

Gdy transakcje są rozliczane niezapłacone saldo każdej z nich rośnie lub maleje. Przeważnie gdy rozliczane są faktury i płatności, stan i saldo każdej transakcji jest aktualizowane zgodnie z następującymi zasadami:

- Jeśli kwota płatności jest większa niż kwota faktury, saldo faktury jest zmniejszane do 0,00, a faktura jest zamykana. Płatność pozostaje otwarta, a saldo jest różnicą między kwotą płatności i kwotą faktury.
- Jeśli kwota płatności jest mniejsza niż kwota faktury, saldo płatności jest zmniejszane do 0,00, a płatność jest zamykana. Faktura pozostaje otwarta, a saldo jest różnicą między kwotą faktury i kwotą płatności.
- Jeśli kwota płatności jest równa kwocie faktury, płatności i faktury są zamykane, a saldo obydwu jest redukowane do 0,00.

Jeśli [kwota płatności jest mniejsza od kwoty faktury](../accounts-payable/vendor-payments-partial-amount.md) z powodu rabatu gotówkowego, odpisu lub niedopłaty, faktura i płatność nadal mogą zostać zamknięte, w zależności od konfiguracji rozliczeń na stronach **Parametry rozrachunków z dostawcami** i **Parametry rozrachunków z odbiorcami**.

Rozliczenia mogą również generować transakcje. Na przykład rozliczenie faktury i płatności może tworzyć rabat gotówkowy, zrealizowane dodatnie lub ujemne różnice kursowe, wprowadzania korekt podatku, odpisy lub różnice groszowe.

## <a name="identifying-marked-transactions-during-settlement"></a>Identyfikowanie oznaczonych transakcji podczas rozliczania

Podczas próby rozliczenia transakcji można zauważyć symbol wskazujący, że transakcja została oznaczona w innej lokalizacji. W takim przypadku można wybrać transakcję na stronie **rozliczania transakcji**, a następnie wybrać pozycję **Zapytanie \> Rozliczenie w oknie rozliczania**. Widok dla tego zapytania zawiera arkusze, zamówienia sprzedaży, faktury, propozycje płatności i lokalizacje odbiorców, które mogą blokować możliwość rozliczenia transakcji. Aby rozwiązać ten problem, można wybrać link umożliwiający bezpośrednie przejście z zapytania do zablokowanej lokalizacji. Następnie można zaktualizować dokument, używając korekt, które są wymagane do jego rozliczenia. Można również skorzystać ze wskaźnika **Oznaczone**, aby zidentyfikować inne dokumenty znajdujące się w tej samej lokalizacji blokowania.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Rozlicz resztę](settle-remainder.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]