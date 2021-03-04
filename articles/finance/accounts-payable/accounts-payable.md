---
title: Rozrachunki z dostawcami — strona główna
description: Ten temat zawiera omówienie modułu Rozrachunki z dostawcami.
author: ShylaThompson
manager: AnnBe
ms.date: 02/15/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace
audience: Application User
ms.reviewer: roschlom
ms.custom: 21901
ms.assetid: 1e4c2ac4-077b-4678-8733-5cec8f6ff659
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: a0195c6776b5065d98b6b1d4d9795248c6bf4c74
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972162"
---
# <a name="accounts-payable-home-page"></a>Rozrachunki z dostawcami — strona główna

[!include [banner](../includes/banner.md)]

Ten temat zawiera omówienie modułu Rozrachunki z dostawcami. 

Faktury od dostawców można wprowadzać ręcznie, ale można też przyjmować je elektronicznie za pośrednictwem jednostek danych. Wprowadzone lub otrzymane faktury można przeglądać i zatwierdzać za pomocą arkusza zatwierdzania faktur lub strony **Faktura od dostawcy**. Aby zautomatyzować proces przeglądu w celu automatycznego zatwierdzania faktur spełniających określone kryteria i oznaczania pozostałych faktur jako przeznaczonych do przeglądu przez autoryzowanego użytkownika, można używać funkcji uzgadniania faktur, zasad faktur od dostawców oraz przepływu pracy.

**Procesy biznesowe**

[![Diagram procesów biznesowych](./media/AP-process.PNG)](./media/AP-process.PNG)

## <a name="set-up-accounts-payable"></a>Ustawienia modułu Rozrachunki z dostawcami

Możesz konfigurować grupy dostawców, dostawców, profile księgowania, różne opcje płatności i parametry odnoszące się do dostawców, opłat, dostaw i miejsc docelowych, skryptów dłużnych i inne rodzaje informacji dotyczących modułu Rozrachunki z dostawcami. 

[Omówienie konfiguracji modułu Rozrachunki z dostawcami](accounts-payable-overview.md)

[Zasady podziału księgowań i zapisy w arkuszu księgi podrzędnej dla faktur od dostawcy](accounting-distributions-subledger-journal-entries-vendor-invoices.md) 

[Przeszacowanie w walucie obcej dla rozrachunków z odbiorcami i rozrachunków z dostawcami](../cash-bank-management/foreign-currency-revaluation-accounts-payable-accounts-receivable.md)

## <a name="configure-vendor-invoices"></a>Konfigurowanie faktur dostawcy

Moduł Rozrachunki z dostawcami służy do śledzenia faktur i wydatków wychodzących odnośnie do dostawców.

[Omówienie uzgadniania faktur rozrachunków z dostawcami](accounts-payable-invoice-matching.md)

[Profile księgowania dostawców](vendor-posting-profiles.md)

[Konfigurowanie sprawdzania uzgadniania faktur rozrachunków z dostawcami](tasks/set-up-accounts-payable-invoice-matching-validation.md)

[Trzyelementowe zasady uzgadniania](three-way-matching-policies.md)

[Uzgadnianie faktur i międzyfirmowe zamówienia zakupu](invoice-matching-intercompany-purchase-orders.md)

[Omówienie usuwania rozbieżności podczas dopasowywania sum faktur](resolve-invoice-totals-invoice-matching-discrepancies.md)

[Domyślne konta przeciwstawne dla arkuszy faktur od dostawców i arkuszy zatwierdzania faktur](default-offset-accounts-vendor-invoice-journals.md)

[Zatwierdzanie faktur na urządzeniach przenośnych](mobile-invoice-approvals.md)

[Obszar roboczy fakturowania w portalu współpracy z dostawcami](vendor-portal-invoicing-workspace.md)

[Automatyzacja obsługi faktur od dostawców](vendor-invoice-automation.md)

## <a name="configure-vendor-payments"></a>Konfigurowanie płatności dostawcy 

Możesz przypisać typ płatności zdefiniowany w systemie, np. czek, płatność elektroniczna lub skrypt dłużny, do dowolnej metody płatności zdefiniowanej przez użytkownika. Typy płatności są opcjonalne, ale ułatwiają sprawdzanie poprawności płatności i pozwalają szybko wybrać najlepszą metodą płatności. 

[Obszar roboczy płatności dla dostawców](vendor-payments-workspace.md)

[Definiowanie opłat od płatności dostawcy](tasks/define-vendor-payment-fees.md)

[Definiowanie warunków płatności dostawcy](tasks/define-vendor-payment-terms.md)

[Omówienie płatności dodatnich](positive-pay-overview.md)

[Konfigurowanie i generowanie plików płatności dodatnich](set-up-generate-positive-pay-files.md)

[Tworzenie płatności od dostawców za pomocą propozycji płatności](create-vendor-payments-payment-proposal.md)

[Częściowe płatności dla dostawcy](vendor-payments-partial-amount.md)

[Podjęcie rabatu większego niż obliczony dla płatności dla dostawcy](take-discount-more-calculated-discount-vendor-payment.md)

[Podjęcie rabatu gotówkowego poza okresem rabatu gotówkowego](take-cash-discount-outside-cash-discount-timeframe.md)

[Raportowanie elektroniczne przykładowych czeków od dostawców](electronic-reporting-sample-vendor-checks.md)

[Cofanie płatności dla dostawcy](reverse-vendor-payment.md)

[Faktury zaliczkowe a zaliczki](prepayments-invoices-vs-prepayments.md)

[Scentralizowane płatności na potrzeby rozrachunków z dostawcami](centralized-payments-accounts-payable.md)

## <a name="settlements"></a>Rozliczenia

Poniższe tematy zawierają informacje dotyczące rozliczeń. Rozliczenie to proces regulowania płatności na podstawie faktur. 

[Konfigurowanie rozliczenia](../cash-bank-management/configure-settlement.md)

[Rozliczanie częściowej płatności dla dostawcy przed datą rabatu z ostateczną płatnością po dacie rabatu](settle-partial-vendor-payment-before-discount-or-final-payment-after.md)

[Rozliczanie częściowej płatności dla dostawcy, do której zastosowano rabaty na fakturach korygujących dostawcy](settle-partial-vendor-payment-discounts-vendor-credit-notes.md)

[Rozliczanie częściowej płatności dla dostawcy, która ma wiele okresów rabatu](settle-partial-vendor-payment-multiple-discount-periods.md)

[Rozliczanie częściowej płatności dla dostawcy oraz płatności ostatecznej w całości przed datą rabatu](settle-partial-vendor-payment-or-final-payment-before-discount.md)

[Jeden załącznik z wieloma rekordami odbiorców lub dostawców](single-voucher-multiple-customer-vendor-records.md)



### <a name="additional-resources"></a>Dodatkowe zasoby

#### <a name="whats-new-and-in-development"></a>Nowe i opracowywane funkcje

Przejdź do [Planów wydań Microsoft Dynamics 365](https://go.microsoft.com/fwlink/?linkid=2010158), aby zobaczyć, jakie nowe funkcje są planowane. 

#### <a name="blogs"></a>Blogi

Opinie, wiadomości i inne informacje dotyczące Rozrachunków z dostawcami i innych rozwiązań możesz znaleźć w blogu usługi [Microsoft Dynamics 365](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise) oraz blogu rozwiązania Financials usługi [Microsoft Dynamics 365 Finance](https://community.dynamics.com/365/financeandoperations/b/financials).

[Blog społeczności partnerów Microsoft Dynamics Operations](https://community.dynamics.com/partner/b/operationspartnercommunityblog) zapewnia Microsoft Dynamics, jeden zasób, w którym mogą dowiedzieć się, co nowego, poza tym zyskuje na popularności w systemie Dynamics 365.

#### <a name="community-blogs"></a>Blogi społeczności

[Jak zarządzać zobowiązaniami w Dynamics 365 Finance](https://financefunction.tech/2019/02/15/how-to-manage-payables-in-dynamics-365-for-finance-and-operations)

#### <a name="task-guides"></a>Przewodniki zadania
Przewodniki zadania to pomocna funkcja dostępna w aplikacji. Aby uzyskać dostęp do przewodników zadania, kliknij przycisk Pomoc na dowolnej stronie.

#### <a name="videos"></a>Filmy

Obejrzyj filmy instruktażowe w [kanale YouTube rozwiązania Microsoft Dynamics 365](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).




