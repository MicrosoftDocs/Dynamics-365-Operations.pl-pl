---
title: Synchronizowanie nagłówków faktur i wierszy zamówień sprzedaży w rozwiązaniu Supply Chain Management bezpośrednio z elementami w rozwiązaniu Sales
description: Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania nagłówków i wierszy faktur sprzedaży bezpośrednio między Dynamics 365 Supply Chain Management a Dynamics 365 Sales.
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: fa2772db63332319c399999bd5f747b2ac729d9e
ms.sourcegitcommit: 0099fb24f5f40ff442020b488ef4171836c35c48
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2019
ms.locfileid: "2653282"
---
# <a name="synchronize-sales-invoice-headers-and-lines-directly-from-finance-and-operations-to-sales"></a>Synchronizowanie nagłówków i wierszy faktur sprzedaży w rozwiązaniu Finance and Operations bezpośrednio z elementami w rozwiązaniu Sales

[!include [banner](../includes/banner.md)]

Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania nagłówków i wierszy faktur sprzedaży bezpośrednio między Dynamics 365 Supply Chain Management a Dynamics 365 Sales.

## <a name="data-flow-in-prospect-to-cash"></a>Przepływ danych w rozwiązaniu Prospekt na gotówkę

Rozwiązanie Prospekt na gotówkę korzysta z funkcji Integracji danych do synchronizacji danych między wystąpieniami Supply Chain Management a Sales. Szablony Prospekt na gotówkę, które są dostępne w funkcji integracji danych umożliwiają przepływ danych o kontach, kontaktach, produktach, ofertach sprzedaży, zamówieniach sprzedaży i fakturach sprzedaży między usługą Supply Chain Management a Sales. Poniższa ilustracja przedstawia sposób synchronizacji danych między usługą Supply Chain Management a Sales.

[![Przepływ danych w rozwiązaniu Prospekt na gotówkę](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Szablony i zadania

Aby wyświetlić dostępne szablony, otwórz [Centrum administracyjne usługi PowerApps](https://preview.admin.powerapps.com/dataintegration). Wybierz opcję **Projekty**, a następnie w prawym górnym rogu wybierz opcję **Nowy projekt**, aby wybrać szablony publiczne.

Następujący szablon i podstawowe zadania są używane do synchronizowania nagłówków i wierszy faktur sprzedaży bezpośrednio z Supply Chain Management do Sales:

- **Nazwa szablonu w integracji danych:** Faktury sprzedaży (Fin and Ops do Sales) — bezpośrednie
- **Nazwy zadań w projekcie integracji danych:**

    - SalesInvoiceHeader
    - SalesInvoiceLine

Następujące zadania synchronizacji są wymagane, zanim będzie można zsynchronizować nagłówki i wiersze faktur sprzedaży:

- Produkty (Supply Chain Management do Sales) — bezpośrednie
- Konta (Sales do Supply Chain Management) — bezpośrednie (jeśli używane)
- Kontakty (Sales do Supply Chain Management) — bezpośrednie (jeśli używane)
- Nagłówek zamówienia sprzedaży i wiersze (Supply Chain Management do Sales) - bezpośrednio

## <a name="entity-set"></a>Zestaw jednostek

| Zarządzanie łańcuchem dostaw                              | Sprzedaż          |
|------------------------------------------------------|----------------|
| Nagłówki faktur sprzedaży odbiorcy obsługiwanego zewnętrznie | Faktury       |
| Wiersze faktur sprzedaży odbiorcy obsługiwanego zewnętrznie   | InvoiceDetails |

## <a name="entity-flow"></a>Przepływ jednostek

Faktury sprzedaży są tworzone w Supply Chain Management i synchronizowane z programem Sales.

> [!NOTE]
> Aktualnie podatek dotyczący opłat w nagłówku faktury sprzedaży nie jest uwzględniony w synchronizacji między rozwiązaniem Supply Chain Managements a programem Sales. Program Sales nie obsługuje informacji podatkowych na poziomie nagłówka. Jednakże podatek dotyczący opłat na poziomie wiersza jest uwzględniony w synchronizacji.

## <a name="prospect-to-cash-solution-for-sales"></a>Rozwiązanie Prospekt na gotówkę dla aplikacji Sales

- Pole **Numer faktury** zostało dodane do jednostki **Faktura** i jest wyświetlane na stronie.
- Przycisk **Utwórz fakturę** na stronie **Zamówienie sprzedaży** jest ukryty, ponieważ faktury zostaną utworzone w rozwiązaniu Supply Chain Management i zsynchronizowane z programem Sales. Strony **Faktura** nie można edytować, ponieważ faktury zostaną zsynchronizowane z rozwiązania Supply Chain Management.
- Wartość **Stan zamówienia sprzedaży** automatycznie zmienia się na **Zafakturowano** po zsynchronizowaniu powiązanej faktury z rozwiązania Supply Chain Management do programu Sales. Ponadto właściciel zamówienia sprzedaży, u którego utworzono fakturę jest przypisywany jako właściciel faktury. Dlatego właściciel zamówienia sprzedaży może wyświetlić fakturę.

## <a name="preconditions-and-mapping-setup"></a>Warunki wstępne i ustawienia mapowania

Przed zsynchronizowaniem faktur sprzedaży należy zaktualizować poniższe ustawienia w systemach.

### <a name="setup-in-sales"></a>Konfiguracja w programie Sales

Przejdź do okna **Ustawienia** > **Administracja** > **Ustawienia systemu** > **Sprzedaż** i sprawdź, czy używane są następujące ustawienia:

- Opcja **Użyj systemowego obliczania cen** jest ustawiona na **Tak**.
- Pole **Metoda kalkulacji rabatów** jest ustawione na **Pozycja w wierszu**.

### <a name="setup-in-the-data-integration-project"></a>Konfiguracja w projekcie integracji danych

#### <a name="salesinvoiceheader-task"></a>Zadanie SalesInvoiceHeader

- Sprawdź, czy istnieje wymagane mapowanie dla **InvoiceCountryRegionId** na **BillingAddress\_Country**.

    Wartość szablonu to mapa wartości, w które zmapowanych jest kilka krajów lub regionów.

- Cennik jest wymagany do utworzenia faktur w rozwiązaniu Sales. Zaktualizuj mapę wartości dla parametru **pricelevelid.name \[Nazwa cennika\]** na cennik używany w programie Sales według waluty. Dla jednej waluty można użyć cennika domyślnego. Ponadto, jeżeli masz cenniki w kilku walutach, możesz użyć mapy wartości.

    Wartość szablonu pola **pricelevelid.name \[Nazwa cennika\]** to mapa wartości oparta na walucie z USD = CRM Service USA (przykład).  
    
#### <a name="salesinvoiceline-task"></a>Zadanie SalesInvoiceLine

- Sprawdź, czy istnieje wymagane mapowanie dla opcji **Jednostka miary**.
- Upewnij się, że w rozwiązaniu Supply Chain Management istnieje wymagana mapa wartości dla pola **SalesUnitSymbol**.

    Wartość szablonu zawierająca mapę wartości jest zdefiniowana dla parametru **SalesUnitSymbol** na **Ilość\_Jednostka miary**.

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

> [!NOTE]
> Pola **Warunki płatności**, **Warunki frachtu**, **Warunki dostawy**, **Metoda wysyłki** i **Metoda dostawy** nie wchodzą w skład zbioru domyślnych mapowań. Aby zamapować te pola, należy skonfigurować mapowanie wartości specyficzne dla danych w organizacjach, między którymi jest synchronizowana jednostka.

Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych. 

> [!NOTE]
> Mapowanie pokazuje, które informacje z pól zostaną zsynchronizowane z rozwiązania Sales do rozwiązania Supply Chain Management.

### <a name="salesinvoiceheader"></a>SalesInvoiceHeader

![Mapowanie szablonu w integracji danych](./media/sales-invoice-direct-template-mapping-data-integrator-1.png)

### <a name="salesinvoiceline"></a>SalesInvoiceLine

![Mapowanie szablonu w integracji danych](./media/sales-invoice-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a>Powiązane tematy

[Od prospekta do gotówki](prospect-to-cash.md)

[Synchronizowanie kont klientów bezpośrednio z rozwiązania Sales do odbiorców w Supply Chain Management](accounts-template-mapping-direct.md)

[Synchronizowanie produktów bezpośrednio z rozwiązania Supply Chain Management do produktów w rozwiązaniu Sales](products-template-mapping-direct.md)

[Synchronizowanie kontaktów w rozwiązaniu Sales bezpośrednio z kontaktami lub odbiorcami w rozwiązaniu Supply Chain Management](contacts-template-mapping-direct.md)

[Synchronizowanie nagłówków i wierszy zamówień sprzedaży w rozwiązaniu Supply Chain Management bezpośrednio z elementami w rozwiązaniu Sales](sales-order-template-mapping-direct-two-ways.md)
