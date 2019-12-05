---
title: Synchronizowanie kont klientów bezpośrednio z rozwiązania Sales do odbiorców w Supply Chain Management
description: Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania kont z Dynamics 365 Sales do Supply Chain Management.
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2018
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
ms.openlocfilehash: ebca416e94f44d0448a4f4d0be08f13e30e749e9
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2019
ms.locfileid: "2813231"
---
# <a name="synchronize-accounts-directly-from-sales-to-customers-in-supply-chain-management"></a>Synchronizowanie kont klientów bezpośrednio z rozwiązania Sales do odbiorców w Supply Chain Management

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Zanim zaczniesz używać rozwiązania Prospekt na gotówkę, zapoznaj się z tematem [Integrowanie danych na platformie Common Data Service for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).

Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania kont bezpośrednio z Dynamics 365 Sales do Dynamics 365 Supply Chain Management.

## <a name="data-flow-in-prospect-to-cash"></a>Przepływ danych w rozwiązaniu Prospekt na gotówkę

Rozwiązanie Prospekt na gotówkę korzysta z funkcji Integracji danych do synchronizacji danych między wystąpieniami Supply Chain Management a Sales.  Szablony Prospekt na gotówkę, które są dostępne w funkcji integracji danych umożliwiają przepływ danych o kontach, kontaktach, produktach, ofertach sprzedaży, zamówieniach sprzedaży i fakturach sprzedaży między usługą Supply Chain Management a Sales. Poniższa ilustracja przedstawia sposób synchronizacji danych między usługą Supply Chain Management a Sales.

[![Przepływ danych w rozwiązaniu Prospekt na gotówkę](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Szablony i zadania

Aby wyświetlić dostępne szablony, otwórz [Centrum administracyjne usługi Power Apps](https://preview.admin.powerapps.com/dataintegration). Wybierz opcję **Projekty**, a następnie w prawym górnym rogu wybierz opcję **Nowy projekt**, aby wybrać szablony publiczne.

Następujący szablon i podstawowe zadanie są używane do synchronizowania kont klientów z usługi Sales do Supply Chain Management:

- **Nazwa szablonu w integracji danych:** Konta (Sales do Fin and Ops) — bezpośrednie
- **Nazwa zadania w projekcie:** Konta - odbiorcy

Przed zsynchronizowaniem konta/odbiorcy nie jest wymagane wykonanie zadań synchronizacji.

## <a name="entity-set"></a>Zestaw jednostek

| Sprzedaż    | Zarządzanie łańcuchem dostaw |
|----------|------------------------|
| Konta | Odbiorcy V2           |

## <a name="entity-flow"></a>Przepływ jednostek

Konta klientów są zarządzane w usłudze Sales i synchronizowane z usługą Supply Chain Management jako odbiorcy. Właściwość **Obsługiwane zewnętrznie** u tych odbiorców ma ustawioną wartość **Tak**, aby śledzić odbiorców pochodzących z aplikacji Sales. Podczas fakturowania ta informacja jest używana do filtrowania faktur synchronizowanych z aplikacją Sales.

## <a name="prospect-to-cash-solution-for-sales"></a>Rozwiązanie Prospekt na gotówkę dla aplikacji Sales

Pole **Numeru konta** jest dostępne na stronie **Konto**. Jego wartość pełni rolę naturalnego i unikatowego klucza wspierającego integrację. Funkcja klucza naturalnego w rozwiązaniu zarządzania relacjami z klientami (CRM) może mieć wpływ na klientów, którzy już korzystają z pola **Numeru konta**, ale którzy nie używają unikatowych wartości **Numer konta** dla każdego poszczególnych kont klientów. Obecnie rozwiązanie integracji nie obsługuje takiego przypadku.

Podczas tworzenia nowego konta klienta jeśli wartość **Numer konta** jeszcze nie istnieje, jest generowana automatycznie przy użyciu numeracji. Wartość składa się z przedrostka **ACC**, następnie rosnącej liczby kolejnej, a na końcu sześcioznakowego przyrostka. Oto przykład: **ACC-01000-BVRCPS**

Gdy rozwiązanie integracji jest stosowane do aplikacji Sales, skrypt uaktualniania ustawia pole **Numer konta** dla istniejących kont klientów w aplikacji Sales. Jeśli nie ma wartości **Numer konta**, jest używana numeracja podana wcześniej.

## <a name="preconditions-and-mapping-setup"></a>Warunki wstępne i ustawienia mapowania

- Mapowanie pola **CustomerGroupId** musi zostać zaktualizowane o prawidłową wartość w usłudze Supply Chain Management. Można określić wartość domyślną albo ustawiać wartość przy użyciu mapy wartości.

    Wartość domyślna w szablonie to **10**.

- Dodając następujące mapowania, można ograniczyć liczbę koniecznych ręcznych aktualizacji wymaganych w usłudze Supply Chain Management. Można używać wartości domyślnej lub mapy wartości na przykład z ustawienia **Kraj/region** lub **Miejscowość**.

    - **SiteId** — Witryna jest konieczna do generowania ofert i wierszy zamówień sprzedaży w usłudze Supply Chain Management. Domyślny oddział może być pobierany z produktu albo od odbiorcy z nagłówka zamówienia.

        Wartość domyślna w szablonie to **1**.

    - **WarehouseId** — Magazyn jest konieczny do przetwarzania ofert i wierszy zamówień sprzedaży w usłudze Supply Chain Management. Domyślny magazyn może być pobierany z produktu albo od odbiorcy z nagłówka zamówienia w usłudze Supply Chain Management.

        Wartość domyślna w szablonie to **13**.

    - **LanguageId** — Język jest konieczny do generowania ofert i wierszy zamówień sprzedaży w usłudze Supply Chain Management. Domyślnie jest używany język z nagłówka zamówienia od odbiorcy.

        Domyślna wartość pola w szablonie to **en-us**.

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

> [!NOTE]
> Pola **Warunki płatności**, **Warunki frachtu**, **Warunki dostawy**, **Metoda wysyłki** i **Metoda dostawy** nie wchodzą w skład zbioru domyślnych mapowań. Aby zamapować te pola, należy skonfigurować mapowanie wartości specyficzne dla danych w organizacjach, między którymi jest synchronizowana jednostka.

Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych. 

> [!NOTE]
> Mapowanie pokazuje, które informacje z pól zostaną zsynchronizowane z rozwiązania Sales do rozwiązania Supply Chain Management.

![Mapowanie szablonu w integracji danych](./media/accounts-direct-template-mapping-data-integrator-1.png)

## <a name="related-topics"></a>Powiązane tematy


[Od prospekta do gotówki](prospect-to-cash.md)

[Synchronizowanie kont klientów bezpośrednio z rozwiązania Sales do odbiorców w Supply Chain Management](accounts-template-mapping-direct.md)

[Synchronizowanie kontaktów w rozwiązaniu Sales bezpośrednio z kontaktami lub odbiorcami w rozwiązaniu Supply Chain Management](contacts-template-mapping-direct.md)

[Synchronizowanie zamówień sprzedaży w rozwiązaniu Sales bezpośrednio z elementami w rozwiązaniu Supply Chain Management](sales-order-template-mapping-direct-two-ways.md)

[Synchronizowanie nagłówków faktur i wierszy zamówień sprzedaży w rozwiązaniu Supply Chain Management bezpośrednio z elementami w rozwiązaniu Sales](sales-invoice-template-mapping-direct.md)

