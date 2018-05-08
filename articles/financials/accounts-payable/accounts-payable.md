---
title: "Rozrachunki z dostawcami — strona główna"
description: "Ten temat zawiera omówienie modułu Rozrachunki z dostawcami."
author: twheeloc
manager: AnnBe
ms.date: 08/18/2017
ms.topic: index-page
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendInvoiceWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 21901
ms.assetid: 1e4c2ac4-077b-4678-8733-5cec8f6ff659
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 7bc09cbd108949b37ea1b2207fc3e0c6961abf4b
ms.contentlocale: pl-pl
ms.lasthandoff: 02/07/2018

---

# <a name="accounts-payable-home-page"></a>Rozrachunki z dostawcami — strona główna

[!include [banner](../includes/banner.md)]

Ten temat zawiera omówienie modułu Rozrachunki z dostawcami. 

Faktury od dostawców można wprowadzać ręcznie, ale można też przyjmować je elektronicznie za pośrednictwem jednostek danych. Wprowadzone lub otrzymane faktury można przeglądać i zatwierdzać za pomocą arkusza zatwierdzania faktur lub strony **Faktura od dostawcy**. Aby zautomatyzować proces przeglądu w celu automatycznego zatwierdzania faktur spełniających określone kryteria i oznaczania pozostałych faktur jako przeznaczonych do przeglądu przez autoryzowanego użytkownika, można używać funkcji uzgadniania faktur, zasad faktur od dostawców oraz przepływu pracy.

**Procesy biznesowe**

[![Proces biznesowy](./media/AP-process.PNG)](./media/AP-process.PNG)

## <a name="set-up-accounts-payable"></a>Ustawienia modułu Rozrachunki z dostawcami

Możesz konfigurować grupy dostawców, dostawców, profile księgowania, różne opcje płatności i parametry odnoszące się do dostawców, opłat, dostaw i miejsc docelowych, skryptów dłużnych i inne rodzaje informacji dotyczących modułu Rozrachunki z dostawcami. 

[Konfigurowanie modułu Rozrachunki z dostawcami](accounts-payable-overview.md)

[Zasady podziału księgowań i zapisy w arkuszu księgi podrzędnej dla faktur od dostawcy](accounting-distributions-subledger-journal-entries-vendor-invoices.md) 

[Przeszacowanie w walucie obcej dla rozrachunków z odbiorcami i rozrachunków z dostawcami](../cash-bank-management/foreign-currency-revaluation-accounts-payable-accounts-receivable.md)

## <a name="configure-vendor-invoices"></a>Konfigurowanie faktur dostawcy

Moduł rozrachunków z dostawcami służy do śledzenia faktur i wydatków wychodzących odnośnie do dostawców.

[Uzgadnianie faktur rozrachunków z dostawcami](accounts-payable-invoice-matching.md)

[Profile księgowania dostawców](vendor-posting-profiles.md)

[Konfigurowanie sprawdzania uzgadniania faktur rozrachunków z dostawcami](tasks/set-up-accounts-payable-invoice-matching-validation.md)

[Trzyelementowe zasady uzgadniania](three-way-matching-policies.md)

[Uzgadnianie faktur i międzyfirmowe zamówienia zakupu](invoice-matching-intercompany-purchase-orders.md)

[Usuwanie rozbieżności podczas uzgadniania sum faktur](resolve-invoice-totals-invoice-matching-discrepancies.md)

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

[Raportowanie elektroniczne czeków od dostawców](electronic-reporting-sample-vendor-checks.md)

[Cofanie płatności dla dostawcy](reverse-vendor-payment.md)

[Omówienie przedpłat i faktur zaliczkowych](prepayments-invoices-vs-prepayments.md)

[Scentralizowane płatności na potrzeby modułu Rozrachunki z dostawcami](centralized-payments-accounts-payable.md)

## <a name="settlements"></a>Rozliczenia

Poniższe tematy zawierają informacje dotyczące rozliczeń. Rozliczenie to proces regulowania płatności na podstawie faktur. 

[Konfigurowanie rozliczenia](../cash-bank-management/configure-settlement.md)

[Rozliczanie częściowej płatności dla dostawcy przed datą rabatu](settle-partial-vendor-payment-before-discount-or-final-payment-after.md)

[Rozliczanie częściowej płatności dla dostawcy, do której zastosowano rabaty na fakturach korygujących dostawcy](settle-partial-vendor-payment-discounts-vendor-credit-notes.md)

[Rozliczanie częściowej płatności dla dostawcy, która ma wiele okresów rabatu](settle-partial-vendor-payment-multiple-discount-periods.md)

[Rozliczanie częściowej lub ostatecznej płatności dla dostawcy przed rabatem](settle-partial-vendor-payment-or-final-payment-before-discount.md)

[Jeden załącznik z wieloma rekordami odbiorców lub dostawców](single-voucher-multiple-customer-vendor-records.md)



### <a name="additional-resources"></a>Dodatkowe zasoby

#### <a name="whats-new-and-in-development"></a>Nowe i opracowywane funkcje

Przejdź na stronę [Plan rozwoju usługi Microsoft Dynamics 365](https://roadmap.dynamics.com/), aby zobaczyć, jakie nowe funkcje zostały wydane, a jakie są jeszcze opracowywane. 

#### <a name="blogs"></a>Blogi

Opinie, wiadomości i inne informacje dotyczące modułu Rozrachunki z dostawcami możesz znaleźć w [blogu usługi Microsoft Dynamics 365](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise).

Wiele wpisów dotyczących modułu Rozrachunki z dostawcami jest dostępnych w [blogu zespołu produktu Microsoft Dynamics AX](https://blogs.msdn.microsoft.com/dax/). Mimo że część z tych wpisów została napisana dla poprzedniej wersji modułu Rozrachunki z dostawcami, to w obecnej wersji są również używane te same pojęcia i podobne procedury.

Blog [społeczności partnerów zajmujących się oprogramowaniem Microsoft Dynamics Operations](https://community.dynamics.com/partner/b/operationspartnercommunityblog) stanowi doskonały zasób dla partnerów zajmujących się oprogramowaniem Microsoft Dynamics, który zawiera informacje o nowościach i popularnych rozwiązaniach działu MBS Operations.

#### <a name="task-guides"></a>Przewodniki zadań
Dodatkowa pomoc jest dostępna w formie przewodników po zadaniach wewnątrz rozwiązania Finance and Operations. Aby uzyskać dostęp do przewodników po zadaniach, kliknij przycisk Pomoc na dowolnej stronie.

#### <a name="videos"></a>Filmy

Obejrzyj filmy instruktażowe w [kanale YouTube rozwiązania Microsoft Dynamics 365](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).





