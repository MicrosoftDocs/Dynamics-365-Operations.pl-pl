---
title: Rozwiązywanie problemów z zamówieniami sprzedaży
description: W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z zamówieniami sprzedaży.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 346ebee598e282abfe01a399793cc259aff3c22d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232237"
---
# <a name="troubleshoot-sales-orders"></a>Rozwiązywanie problemów z zamówieniami sprzedaży

W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z zamówieniami sprzedaży.

## <a name="the-tax-information-isnt-updated-if-i-change-the-location-on-a-sales-order-header"></a>Informacje podatkowe nie są aktualizowane, jeśli zmieniam lokalizację w nagłówku zamówienia sprzedaży.

### <a name="issue-description"></a>Opis problemu

Jeśli oddział, magazyn lub adres dostawy został zmieniony w nagłówku zamówienia sprzedaży lub na poziomie wiersza, informacje o podatku dla tych wierszy nie są automatycznie aktualizowane.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Jest to celowe. Ten problem występuje, ponieważ adres dostawy, oddział i magazyn nie są automatycznie zmieniane na poziomie wiersza. Musisz zaktualizować je ręcznie.

## <a name="if-there-are-two-trade-agreements-for-the-same-period-or-overlapping-periods-the-same-agreement-line-is-always-selected"></a>Jeśli istnieją dwie umowy handlowe dla tego samego okresu lub okresów pokrywających się, zawsze jest wybierany ten sam wiersz umowy.

### <a name="issue-description"></a>Opis problemu

Jeśli dwie umowy handlowe są zdefiniowane dla tego samego okresu lub nakładających się okresów, ta sama umowa handlowa wydaje się być wybierana za każdym razem, gdy tworzysz wiersze zamówienia sprzedaży, które zawierają te towary.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Jeśli istnieje więcej niż jedna umowa handlowa dla danego dnia, zawsze jest wybierana umowa handlowa o najniższej cenie. Aby uzyskać więcej informacji, pobierz następujący oficjalny dokument: [Umowy handlowe w Microsoft Dynamics AX 2012](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).

## <a name="can-i-link-a-purchase-order-to-a-sales-order-to-fulfill-demand"></a>Czy można połączyć zamówienie zakupu z zamówieniem sprzedaży, aby zrealizować zapotrzebowanie?

Można utworzyć zamówienia zakupu na podstawie zamówienia sprzedaży. Aby uzyskać więcej informacji, zobacz [Tworzenie zamówienia zakupu na podstawie zamówienia sprzedaży](tasks/create-purchase-order-sales-order.md).

## <a name="i-cant-cancel-or-delete-a-return-order-or-a-sales-order"></a>Nie można anulować lub usunąć zamówienia zwrotu lub zamówienia sprzedaży.

Można anulować tylko zamówienia sprzedaży i zamówienia zwrotu, które są w stanie *Utworzone*. Aby uzyskać więcej informacji, zobacz [Anulowanie zamówienia zwrotu](../service-management/cancel-return-order.md).

## <a name="when-i-try-to-cancel-a-sales-order-i-receive-a-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations-error"></a>Kiedy próbuję anulować zamówienie sprzedaży, pojawia się błąd „Nie można usunąć rezerwacji, ponieważ utworzono pracę, która opiera się na rezerwacjach”.

Kod błędu: WAX4661

Jeśli praca jest skojarzona z zamówieniem sprzedaży, nie można anulować zamówienia sprzedaży, dopóki praca nie zostanie anulowana i wycofana. To wymaganie ma zastosowanie nawet wtedy, gdy praca skojarzona z zamówieniem sprzedaży jest zamknięta.

Aby naprawić ten problem, należy wykonać następujące czynności.

1. Anuluj pracę i umieść zapasy z powrotem w żądanej lokalizacji. Umożliwia przejście do odpowiedniego ładunku zamówienia sprzedaży i wybranie opcji **Zmniejsz ilość pobraną** w wierszu ładunku lub **Cofnij pracę** w okienku akcji.

    Obecnie praca ma stan *Anulowane*, a nowe prace przesunięcia zapasów są automatycznie tworzone i przetwarzane w celu przeniesienia zapasów z powrotem do lokalizacji, która została opisana w momencie wycofania.

2. Usuń ładunek. Wysyłka jest również usuwana.
3. Teraz powinno być możliwe przejście do tego zamówienia sprzedaży i anulowanie go.

## <a name="i-cant-cancel-an-intercompany-purchase-order-that-is-linked-to-a-sales-order"></a>Nie mogę anulować międzyfirmowego zamówienia zakupu połączonego z zamówieniem sprzedaży.

### <a name="issue-description"></a>Opis problemu

Przy próbie anulowania międzyfirmowego zamówienia zakupu połączonego z zamówieniem sprzedaży może pojawić się następujący komunikat o błędzie: „Nie można zmniejszyć ilości, ponieważ pozostała ilość aktualizacji zmienia się”.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Ten błąd został rozwiązany w wersji 10.0.13 Microsoft Dynamics 365 Supply Chain Management. W tej wersji systemu i nowszych wersjach można teraz anulować międzyfirmowe zamówienie zakupu połączone z zamówieniem sprzedaży.

## <a name="can-i-restore-an-invoiced-sales-order-that-was-deleted"></a>Czy można przywrócić zafakturowane zamówienie sprzedaży, które zostało usunięte?

### <a name="issue-description"></a>Opis problemu

Zafakturowane zamówienie sprzedaży zostało usunięte przez pomyłkę i ma zostać przywrócone lub wyświetlone jego szczegóły.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Jeśli usunięte zamówienie sprzedaży zostało już zafakturowane, przejdź do **Konto odbiorcy \> Transakcje \> Dokument oryginalny \> Wyświetl szczegóły**. Znajdź szukaną fakturę i wybierz ją, aby wyświetlić jej szczegóły. Szczegóły zawierają odwołanie do zamówienia sprzedaży. Należy również uzyskać dostęp do szczegółów zamówienia sprzedaży z tej strony.

## <a name="the-deadline-of-a-sales-order-header-cant-be-found-in-the-salesorderheaderv2entity-data-entity"></a>Nie można odnaleźć terminu ostatecznego nagłówka zamówienia sprzedaży w jednostce danych SalesOrderHeaderV2Entity.

Pole terminu ostatecznego nie istnieje w jednostce *SalesOrderHeaderV2Entity*.

## <a name="i-must-delete-orphaned-sales-order-records"></a>Należy usunąć oddzielone rekordy zamówienia sprzedaży.

Aby oczyścić rekordy oddzielonych rekordów zamówienia sprzedaży, należy uruchomić zadanie okresowe *Usuwanie zamówień sprzedaży*, przechodząc do jednej z następujących lokalizacji:

- Sprzedaż i marketing \> Zadania okresowe \> Oczyszczanie \> Usuwanie zamówień zakupu
- Handel detaliczny i inny \> Retail i Commerce — składniki IT \> Wyczyść \> Usuwanie zamówień zakupu

## <a name="is-there-a-way-to-calculate-commissions-on-invoices-that-have-already-been-posted"></a>Czy istnieje sposób obliczania prowizji dla faktur, które zostały już zaksięgowane?

Supply Chain Management nie obsługuje obecnie obliczania prowizji za zaksięgowane faktury.

## <a name="a-bundle-item-isnt-supported-in-an-intercompany-process"></a>Element pakietu nie jest obsługiwany w procesie międzyfirmowym.

Pozycja pakietu jest niedostępna dla zamówienia zakupu, ponieważ w przypadku zbadania wierszy zamówienia sprzedaży dla towaru pakietu można zauważyć, że ilość wynosi *0* (zero), a stan jest *Anulowany*. Jest to celowe. Zamówienie sprzedaży kupuje tylko składniki towaru pakietu. Nie powoduje to nabycia samego towaru w pakiecie.

Jeśli trzeba kupić pakiet, należy rozważyć, czy należy go oznaczyć jako element pakietu, ponieważ jest on przeznaczony do scenariuszy rozpoznawania przychodów. Aby uzyskać więcej informacji o elementach pakietów, zobacz temat [Pakiety](../../finance/accounts-receivable/revenue-recognition-setup.md#bundles).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]