---
title: "Synchronizowanie nagłówków i wierszy zamówień sprzedaży w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales"
description: "Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania nagłówków i wierszy zamówień sprzedaży między programem Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition a programem Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c7b2ff6430e99661ee284f65089086df9fa5a1ad
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-order-headers-and-lines-from-finance-and-operations-to-sales"></a>Synchronizowanie nagłówków i wierszy zamówień sprzedaży w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales

[!include[banner](../includes/banner.md)]

Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania nagłówków i wierszy zamówień sprzedaży między programem Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition a programem Microsoft Dynamics 365 for Sales. 

## <a name="template-and-tasks"></a>Szablon i zadania

Następujące szablony i podstawowe zadania są używane do synchronizowania nagłówków i wierszy zamówień sprzedaży z programu Finance i Operations do programu Sales:

- **Nazwa szablonu w integracji danych** 

    - Zamówienia sprzedaży (z Fin and Ops do Sales)
    
- **Nazwy zadań w projekcie integracji danych**

    - OrderHeader
    - OrderLine

Zadania synchronizacji wymagane przed synchronizacją nagłówka faktury sprzedaży i wierszy:

- Produkty (z Fin and Ops do Sales)
- Konta (Sales do Fin and Ops) (jeśli są używane)
- Kontakty z odbiorcami (z Sales do Fin and Ops) (jeśli używane)

## <a name="entity-set"></a>Zestaw jednostek

| Finance and Operations |    Usługa Common Data Service (CDS)         |     Sprzedaż      |
|------------------------|----------------|----------------|
| Nagłówki zamówień sprzedaży CDS| SalesOrder     | SalesOrders |
| Wiersze zamówienia sprzedaży CDS  | SalesOrderLine | SalesOrderDetails|

## <a name="entity-flow"></a>Przepływ jednostek

Zamówienia sprzedaży są tworzone w programie Finance and Operations i synchronizowane z programem Sales.

Filtry w szablonie zapewniają, że w synchronizacji uwzględniane są tylko odpowiednie zamówienia sprzedaży:

- W synchronizacji zostanie uwzględniony klient zamawiający i fakturujący z programu Sales. W rozwiązaniu Finance and Operations pola **OrderingCustomerIsExternallyMaintained** i **InvoiceCustomerIsExternallyMaintained** służą do śledzenia synchronizacji w jednostkach danych.

- **Zamówienie sprzedaży** w rozwiązaniu Finance and Operations musi zostać potwierdzone. Z programem Sales są synchronizowane tylko potwierdzone zamówienia sprzedaży lub zamówienia sprzedaży o wyższym statusie przetwarzania, na przykład, Wysłano lub Zafakturowano.

- Po utworzeniu lub zmodyfikowaniu zamówienia sprzedaży należy wykonać zadanie wsadowe **Obliczanie sum sprzedaży** w rozwiązaniu Finance and Operations. Z usługą CDS i programem Sales zostaną zsynchronizowane tylko zamówienia sprzedaży z obliczonymi sumami sprzedaży.

> [!NOTE]
> Podatek dotyczący opłat w **nagłówku zamówienia sprzedaży** nie jest aktualnie uwzględniony w synchronizacji między rozwiązaniem Finance and Operations a programem Sales. Jest to spowodowane tym, że program Sales nie obsługuje informacji podatkowych na poziomie nagłówka. Uwzględniony jest podatek dotyczący opłat na poziomie wiersza.

## <a name="prospect-to-cash-solution-for-sales"></a>Rozwiązanie Prospekt na gotówkę dla aplikacji Sales

Nowe pola dodane do jednostki **Zamówienie** i wyświetlane na stronie:

- **Jest obsługiwane zewnętrznie**— ustaw na **Tak**, gdy zamówienie pochodzi z programu Finance and Operations.

- **Stan przetwarzania** — służy do wyświetlania stanu przetwarzania zamówienia w rozwiązaniu Finance and Operations. Dostępne wartości:

    - Aktywne
    - Potwierdzone
    - Dokument dostawy
    - Zafakturowano
    - Pobrane
    - Częściowo pobrane
    - Częściowo zapakowano
    - Wysłano
    - Częściowo wysłane
    - Częściowo zafakturowane
    - Anulowane

Ustawienie **Zawiera tylko zewnętrznie obsługiwane produkty** jest używane w innych scenariuszach dotyczących zamówienia sprzedaży (od synchronizacji rozwiązania Sales to Finance z programem Operation) do spójnego śledzenia, czy zamówienie sprzedaży składa się całkowicie z **produktów obsługiwanych zewnętrznie**; w takim przypadku produkty są obsługiwane w rozwiązaniu Finance and Operations. Zapewnia to brak możliwości synchronizacji wierszy zamówienia sprzedaży z produktami nieznanymi w rozwiązaniu Finance and Operations.
 
Przyciski **Utwórz fakturę**, **Anuluj zamówienie**, **Oblicz ponownie**, **Pobierz produkty** i **Wyszukaj adres** na stronie **Zamówienie sprzedaży** są ukryte dla zamówień obsługiwanych zewnętrznie, ponieważ faktury zostaną utworzone w rozwiązaniu Finance and Operations i zsynchronizowane z programem Sales. Strony zamówienia nie można edytować, ponieważ informacje o zamówieniu sprzedaży zostaną zsynchronizowane z rozwiązania Finance and Operations.
 
Opcja **Stan zamówienia sprzedaży** pozostanie aktywna, aby zapewnić przepływ zmian z rozwiązania Finance and Operations do **zamówienia sprzedaży** w programie Sales. Można to kontrolować, ustawiając domyślny **Kod stanu [Stan]** na **Aktywny** w projekcie integracji danych.

## <a name="preconditions-and-mapping-setup"></a>Warunki wstępne i ustawienia mapowania 

Przed zsynchronizowaniem zamówień sprzedaży należy zaktualizować w systemach następujące ustawienie:

### <a name="setup-in-sales"></a>Konfiguracja w programie Sales

- Zapewnij uprawienia dla zespołu (za pomocą opcji **Ustawione połączenie** programu Sales ), do którego przypisany jest użytkownik. Jeżeli korzystasz z danych demonstracyjnych, zwykle użytkownik, ale nie zespół ma dostęp w trybie administratora. W przeciwnym wypadku zostanie wyświetlony komunikat o błędzie z informacją o braku zespołu sprzedającego przy uruchomieniu projektu z integratora danych. 

    - W obszarze **Ustawienia** > **Zabezpieczenia** > **Zespoły** wybierz odpowiedni zespół, kliknij opcję **Zarządzaj rolami** i wybierz rolę o odpowiednich uprawnieniach, np. Administrator systemu.

- W obszarze **Ustawienia** > **Administracja** > **Ustawienia systemu** > **Sprzedaż** sprawdź, czy opcja **Użyj systemowego obliczania cen###** jest ustawiona na **Tak**. 

- W obszarze **Ustawienia** > **Administracja** > **Ustawienia systemu** > **Sprzedaż** sprawdź, czy opcja **Metoda kalkulacji rabatów** jest ustawiona na **Pozycja w wierszu**. 

### <a name="setup-in-finance-and-operations"></a>Konfiguracja w programie Finance and Operations

Ustaw opcje **Sprzedaż i marketing** > **Zadania okresowe** > **Obliczanie sum sprzedaży**, aby uruchomić jako zadanie wsadowe z opcją **Oblicz sumy dla zamówień sprzedaży** ustawioną na **Tak**. Jest to ważne, ponieważ z usługą CDS i programem Sales zostaną zsynchronizowane tylko zamówienia sprzedaży z obliczonymi sumami sprzedaży. Częstotliwość zadania wsadowego powinna być zgodna z częstotliwością synchronizacji zamówienia sprzedaży.

### <a name="setup-in-the-data-integration-project"></a>Konfiguracja w projekcie integracji danych

#### <a name="salesheader-task"></a>Zadanie SalesHeader

- Zaktualizuj mapowanie dla **Identyfikator organizacji CDS w Źródło** > **CDS**.

    - Domyślna wartość szablonu **Account_Organization_OrganizationId** to ORG001.
    - Szablon domyślny dla **InvoiceAccount_Organization_OrganizationId** to ORG001.
    - Domyślna wartość szablonu **Organization_OrganizationId** to ORG001.

- Upewnij się, że wymagane mapowanie istnieje w opcji **Źródło** > **CDS dla parametru InvoiceCountryRegionId na BillingAddress_Country** i dla **DeliveryCountryRegionId na DeliveryAddress_Country**.

    - Wartość szablonu to **ValueMap** ze zmapowaną liczbą kraju.

- **Cennik** jest wymagany do utworzenia zamówień w programie Sales. Zaktualizuj parametr **ValueMap** w **CDS** > **Przeznaczenie** dla **pricelevelid.name [nazwa cennika]** na **cennik** używany w programie Sales według waluty. Można użyć domyślnego **cennika** dla pojedynczej waluty lub użyć parametru **ValueMap**, jeżeli **cenniki** są dostępne w kilku walutach.
    
    - Wartość szablonu domyślnego dla parametru **pricelevelid.name [nazwa cennika]** to CRM Service USA (przykład). 

#### <a name="salesline-task"></a>Zadanie SalesLine

- Zaktualizuj mapowanie dla **Identyfikator organizacji CDS w Źródło** > **CDS**. 
    
    - Domyślna wartość szablonu dla **SalesOrder_Organization_OrganizationId** to ORG001.
    - Domyślna wartość szablonu **Product_Organization_OrganizationId** to ORG001.

- Upewnij się, że wymagane mapowanie istnieje w **Źródło** > **CDS** dla parametru **DeliveryCountryRegionId** na **DeliveryAddress_Country**.

    - Wartość szablonu to **ValueMap** ze zmapowaną liczbą kraju.
    
- Sprawdź, czy wymagany parametr **ValueMap** dla **SalesUnitSymbol** w rozwiązaniu Finance and Operations istnieje w **Źródło** > **Mapowanie CDS**.

    - Wartość szablonu z **ValueMap**jest zdefiniowana dla **SalesUnitSymbol do Quantity_UOM**.

## <a name="template-mapping-in-data-integrator"></a>Mapowanie szablonu w integratorze danych

> [!NOTE]
> Pola **Warunki płatności**, **Warunki frachtu**, **Warunki dostawy**, **Metoda wysyłki** i **Metoda dostawy** nie wchodzą w skład zbioru domyślnych mapowań. Aby zamapować te pola, należy skonfigurować mapowanie wartości specyficzne dla danych w organizacjach, między którymi jest synchronizowana jednostka.

Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych.

### <a name="orderheader"></a>OrderHeader

![Mapowanie szablonu w integratorze danych](./media/sales-order-template-mapping-data-integrator-1.png)

![Mapowanie szablonu w integratorze danych](./media/sales-order-template-mapping-data-integrator-2.png)

### <a name="orderline"></a>OrderLine

![Mapowanie szablonu w integratorze danych](./media/sales-order-template-mapping-data-integrator-3.png)

![Mapowanie szablonu w integratorze danych](./media/sales-order-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a>Powiązane tematy

[Synchronizowanie produktów w rozwiązaniu Finance and Operations do produktów w rozwiązaniu Sales](products-template-mapping.md)

[Synchronizowanie kont w rozwiązaniu Sales do odbiorców w rozwiązaniu Finance and Operations](accounts-template-mapping.md)

[Synchronizowanie kontaktów w rozwiązaniu Sales do kontaktów lub odbiorców w rozwiązaniu Finance and Operations](contacts-template-mapping.md)

[Synchronizowanie nagłówków i wierszy ofert sprzedaży w rozwiązaniu Sales do elementów w rozwiązaniu Finance and Operations](sales-quotation-template-mapping.md)

[Synchronizowanie nagłówków i wierszy faktur sprzedaży w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales](sales-invoice-template-mapping.md)


