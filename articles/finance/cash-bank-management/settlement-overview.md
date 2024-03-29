---
title: Przegląd rozliczenia
description: Ten artykuł zawiera ogólne informacje o procesie rozliczania. Opisano w nim typy transakcji, które można rozliczyć, oraz czas i proces ich rozliczania. Przedstawia on także wyniki procesu rozliczania.
author: angelad116
ms.date: 07/30/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: kfend
ms.custom:
- "14551"
- intro-internal
ms.assetid: 0968fa71-5984-415b-8689-759a0136d5d1
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 343802b409363f2698f857f3fc0e2682b48fec92
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151231"
---
# <a name="settlement-overview"></a>Omówienie rozliczeń

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


Ten artykuł zawiera ogólne informacje o procesie rozliczania. Opisano w nim typy transakcji, które można rozliczyć, oraz czas i proces ich rozliczania. Przedstawia on także wyniki procesu rozliczania.

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

## <a name="resolve-issues-with-transactions-that-cant-be-settled"></a>Rozwiązywanie problemów z transakcjami, których nie można rozliczyć

Czasami nie można rozliczyć transakcji, ponieważ w danej chwili dokument jest przetwarzany przez inne działanie. W przypadku próby rozliczenia transakcji wystąpi błąd, ponieważ te transakcje są używane. Aby rozwiązać ten problem, można użyć strony **Szczegóły zaznaczonych transakcji**, aby znaleźć transakcje zaznaczone do rozliczenia i zidentyfikować inne procesy, które wykonują na nich działania.

Transakcje są oznaczane do rozliczenia albo podczas opłacania faktur dostawcy, albo gdy odbiorcy płacą otwarte faktury. Czasami faktury te mogą być już zaznaczone do rozliczenia. W związku z tym użytkownicy nie mogą ich wybrać do płatności. Faktury mogą być oznaczone przez inny arkusz płatności odbiorcy, zamówienie sprzedaży, arkusz płatności dostawcy lub zamówienie zakupu w bieżącej firmie lub innej firmie.

Jeśli transakcja jest zablokowana do rozliczenia podczas wprowadzania płatności odbiorcy, otwórz stronę **Szczegóły transakcji oznaczonych dla odbiorcy** (**Rozrachunki z odbiorcami \> Zadania okresowe \> Szczegóły zaznaczonej transakcji odbiorcy**). Aby szybko określić miejsce zablokowania transakcji, można ustawić dowolny z następujących parametrów wyboru: **Konto odbiorcy**, **Załącznik**, **Data** lub **Faktura**. Jeśli nie zostaną ustawione żadne parametry wyboru, system będzie wyświetlał wszystkie dokumenty zablokowane dla bieżącej firmy lub innej wybranej firmy. Po zidentyfikowaniu transakcji zablokowanej do rozliczenia można ją zaznaczyć, a następnie wybrać opcję **Odznacz zaznaczone transakcje**. Wybrana transakcja jest następnie usuwana z każdego arkusza, który zawiera tę transakcję. Jednak dokument nie jest usuwany z innej lokalizacji. Z tego arkusza są usuwane tylko informacje o oznaczaniach.

Jeśli transakcja jest zablokowana do rozliczenia podczas wprowadzania płatności dostawcy, otwórz stronę **Szczegóły transakcji oznaczonych dla dostawcy** (**Rozrachunki z dostawcami \> Zadania okresowe \> Szczegóły zaznaczonej transakcji dostawcy**). Aby szybko określić miejsce zablokowania transakcji, można ustawić dowolny z następujących parametrów wyboru: **Konto dostawcy**, **Załącznik**, **Data** lub **Faktura**. Jeśli nie zostaną ustawione żadne parametry wyboru, system będzie wyświetlał wszystkie dokumenty zablokowane dla bieżącej firmy lub innej wybranej firmy. Po zidentyfikowaniu transakcji można ją zaznaczyć, a następnie wybrać opcję **Odznacz zaznaczone transakcje**, aby rozwiązać problem blokujący. Wybrana transakcja jest następnie usuwana z każdego innego arkusza, w którym jest wybrana. Jednak dokument nie jest usuwany z innej lokalizacji. Z tego arkusza są usuwane tylko informacje o oznaczaniach.

Aby zidentyfikować wszystkie zablokowane dokumenty, otwórz stronę **Szczegóły wszystkich transakcji oznaczonych** (**Rozrachunki z odbiorcami \> Zadania okresowe \> Szczegóły wszystkich zaznaczonych transakcji** lub **Rozrachunki z dostawcami \> Zadania okresowe \> Szczegóły wszystkich zaznaczonych transakcji**). Aby szybko określić miejsce zablokowania transakcji, można ustawić dowolny z następujących parametrów wyboru: **Konto odbiorcy**, **Konto dostawcy**, **Załącznik**, **Data** lub **Faktura**. Jeśli nie zostaną ustawione żadne parametry wyboru, system będzie wyświetlał wszystkie dokumenty zablokowane dla bieżącej firmy lub innej wybranej firmy. Po zidentyfikowaniu transakcji można ją zaznaczyć, a następnie wybrać opcję **Odznacz zaznaczone transakcje**, aby rozwiązać problem blokujący. Wybrana transakcja jest następnie usuwana z każdego innego arkusza, w którym jest wybrana. Jednak dokument nie jest usuwany z innej lokalizacji. Z tego arkusza są usuwane tylko informacje o oznaczaniach.

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z obszaru roboczego **Zarządzanie funkcjami**, aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. Ta funkcja jest wymieniona w następujący sposób:

- **Moduł:** zarządzanie gotówką i bankami
- **Nazwa funkcji:** formularz szczegółów zaznaczonej transakcji

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Rozlicz resztę](settle-remainder.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
