---
title: "Synchronizowanie nagłówków i wierszy faktur sprzedaży w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales"
description: "Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania nagłówków i wierszy faktur sprzedaży między programem Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition a programem Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
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
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 22ab02555dcac850b18aac9564af41d6c627eade
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-invoice-headers-and-lines-from-finance-and-operations-to-sales"></a>Synchronizowanie nagłówków i wierszy faktur sprzedaży w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales

[!include[banner](../includes/banner.md)]

Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania nagłówków i wierszy faktur sprzedaży między programem Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition a programem Microsoft Dynamics 365 for Sales. 

## <a name="templates-and-tasks"></a>Szablony i zadania

Następujące szablony i podstawowe zadania są używane do synchronizowania nagłówków i wierszy faktur sprzedaży z programu Finance i Operations do programu Sales:

- **Nazwa szablonu w integracji danych** 

     - Faktury sprzedaży (z Fin and Ops do Sales)

- **Nazwy zadań w projekcie integracji danych**

    - SalesInvoiceHeader
    - SalesInvoiceLine

Zadania synchronizacji wymagane przed synchronizacją nagłówka faktury sprzedaży i wierszy:
-   Produkty (z Fin and Ops do Sales)
-   Konta (Sales do Fin and Ops) (jeśli są używane)
-   Kontakty (Sales do Fin and Ops) (jeśli są używane)
-   Nagłówek i wiersze zamówienia sprzedaży (Fin and Ops do Sales)

## <a name="entity-set"></a>Zestaw jednostek

| Finance and Operations                               | Usługa Common Data Service (CDS)              | Sprzedaż          |
|------------------------------------------------------|------------------|----------------|
| Nagłówki faktur sprzedaży odbiorcy obsługiwanego zewnętrznie | SalesInvoice     | Faktury       |
| Wiersze faktur sprzedaży odbiorcy obsługiwanego zewnętrznie   | SalesInvoiceLine | InvoiceDetails |

## <a name="entity-flow"></a>Przepływ jednostek

Faktury sprzedaży są tworzone w programie Finance and Operations i synchronizowane z programem Sales.

> [!NOTE]
> Podatek dotyczący opłat w **nagłówku faktury sprzedaży** nie jest aktualnie uwzględniony w synchronizacji między rozwiązaniem Finance and Operations a programem Sales. Jest to spowodowane tym, że program Sales nie obsługuje informacji podatkowych na poziomie nagłówka. Uwzględniony jest podatek dotyczący opłat na poziomie wiersza.

## <a name="prospect-to-cash-solution-for-sales"></a>Rozwiązanie Prospekt na gotówkę dla aplikacji Sales

-  **Pole numeru faktury** jest dodawane do jednostki **Faktura** i wyświetlane na stronie.
 
-  Przycisk **Utwórz fakturę** na stronie **Zamówienie sprzedaży** jest ukryty, ponieważ faktury zostaną utworzone w rozwiązaniu Finance and Operations i zsynchronizowane z programem Sales. Strony **Faktura** nie można edytować, ponieważ faktury zostaną zsynchronizowane z rozwiązania Finance and Operations.
 
-  **Stan zamówienia sprzedaży** automatycznie zmienia się na **Zafakturowano**, po zsynchronizowaniu powiązanej faktury z rozwiązania Finance and Operations do programu Sales. Ponadto właściciel zamówienia sprzedaży, u którego utworzono fakturę jest przypisywany jako właściciel faktury. Umożliwia to właścicielowi zamówienia sprzedaży wyświetlenie faktury.
 
## <a name="preconditions-and-mapping-setup"></a>Warunki wstępne i ustawienia mapowania

Przed zsynchronizowaniem faktur sprzedaży należy zaktualizować w systemach następujące ustawienie:

### <a name="setup-in-sales"></a>Konfiguracja w programie Sales

- W obszarze **Ustawienia** > **Administracja** > **Ustawienia systemu** > **Sprzedaż** sprawdź, czy opcja **Użyj systemowego obliczania cen###** jest ustawiona na **Tak**. 

- W obszarze **Ustawienia** > **Administracja** > **Ustawienia systemu** > **Sprzedaż** sprawdź, czy opcja **Metoda kalkulacji rabatów** jest ustawiona na **Pozycja w wierszu**. 

### <a name="setup-in-the-data-integration-project"></a>Konfiguracja w projekcie integracji danych

#### <a name="salesinvoiceheader-task"></a>Zadanie SalesInvoiceHeader

- Zaktualizuj mapowanie dla **Identyfikator organizacji CDS** w **Źródło** > **CDS**. 

    -  Domyślna wartość szablonu dla **SalesOrder_Organization_OrganizationId** to ORG001.
    -  Domyślna wartość szablonu **Account_Organization_OrganizationId** to ORG001.
    -  Domyślna wartość szablonu **Organization_OrganizationId** to ORG001.

- Upewnij się, że wymagane mapowanie istnieje w **Źródło** > **CDS dla InvoiceCountryRegionId** na **BillingAddress_Country**.

    -  Wartość szablonu to **ValueMap** ze zmapowaną liczbą kraju.

- **Cennik** jest wymagany do utworzenia faktur w programie Sales. Zaktualizuj parametr **ValueMap** w **CDS** > **Przeznaczenie dla pricelevelid.name [nazwa cennika]** na **Cennik** używany w programie Sales według waluty. Można użyć domyślnego **cennika** dla pojedynczej waluty lub użyć parametru **ValueMap**, jeżeli **cenniki** są dostępne w kilku walutach.

    -  Wartość szablonu dla **pricelevelid.name [nazwa cennika]** to **ValueMap** na podstawie opcji **Waluta**.
    -  usd: CRM Service USA (przykład). 

#### <a name="salesinvoiceline-task"></a>Zadanie SalesInvoiceLine

- Upewnij się, że wymagane mapowanie istnieje w **Źródło** > **CDS dla jednostki miary**.

- Sprawdź, czy wymagany parametr **ValueMap** dla **SalesUnitSymbol** w rozwiązaniu Finance and Operations istnieje w **Źródło** > **Mapowanie CDS**. 
    
    - Wartość szablonu z **ValueMap**jest zdefiniowana dla **SalesUnitSymbol do Quantity_UOM**.
    
-  Zaktualizuj mapowanie dla **Identyfikator organizacji CDS w Źródło** > **CDS**. 

    -  Domyślna wartość szablonu dla **SalesInvoicer_Organization_OrganizationId** to ORG001.
    -  Domyślna wartość szablonu **Product_Organization_OrganizationId** to ORG001.
 
## <a name="template-mapping-in-data-integrator"></a>Mapowanie szablonu w integratorze danych

> [!NOTE]
> Opcje **Warunki płatności**, **Warunki frachtu**, **Warunki dostawy**, **Metoda wysyłki** i **Metoda dostawy** nie wchodzą w skład zbioru domyślnych mapowań. Mapowanie tych pól wymaga skonfigurowania mapowania wartości, które jest specyficzne dla danych w organizacjach, między którymi synchronizowana jest jednostka.

Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych.

![Mapowanie szablonu w integratorze danych](./media/sales-invoice-template-mapping-data-integrator-1.png)

![Mapowanie szablonu w integratorze danych](./media/sales-invoice-template-mapping-data-integrator-2.png)

![Mapowanie szablonu w integratorze danych](./media/sales-invoice-template-mapping-data-integrator-3.png)

![Mapowanie szablonu w integratorze danych](./media/sales-invoice-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a>Powiązane tematy

[Synchronizowanie produktów w rozwiązaniu Finance and Operations do produktów w rozwiązaniu Sales](products-template-mapping.md)

[Synchronizowanie kont w rozwiązaniu Sales do odbiorców w rozwiązaniu Finance and Operations](accounts-template-mapping.md)

[Synchronizowanie kontaktów w rozwiązaniu Sales do kontaktów lub odbiorców w rozwiązaniu Finance and Operations](contacts-template-mapping.md)

[Synchronizowanie nagłówków i wierszy ofert sprzedaży w rozwiązaniu Sales do elementów w rozwiązaniu Finance and Operations](sales-quotation-template-mapping.md)

[Synchronizowanie nagłówków i wierszy zamówień sprzedaży w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales](sales-order-template-mapping.md)


