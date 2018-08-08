---
title: "Synchronizowanie kont bezpośrednio w rozwiązaniu Sales do odbiorców w rozwiązaniu Finance and Operations"
description: "Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania kont klientów między programem Microsoft Dynamics 365 for Sales a programem Microsoft Dynamics 365 for Finance and Operations."
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: fb694db32638756328623c186594cf5ba2e7d6b8
ms.contentlocale: pl-pl
ms.lasthandoff: 03/26/2018

---

# <a name="synchronize-accounts-directly-from-sales-to-customers-in-finance-and-operations"></a>Synchronizowanie kont w rozwiązaniu Sales bezpośrednio z odbiorcami w rozwiązaniu Finance and Operations

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Zanim zaczniesz używać rozwiązania Prospekt na gotówkę, zapoznaj się z tematem [Integracja danych w usłudze Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).

Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania kont klientów bezpośrednio między programem Microsoft Dynamics 365 for Sales a programem Microsoft Dynamics 365 for Finance and Operations.

## <a name="data-flow-in-prospect-to-cash"></a>Przepływ danych w rozwiązaniu Prospekt na gotówkę

Rozwiązanie Prospekt na gotówkę korzysta z funkcji Integracja danych do synchronizacji danych między wystąpieniami programu Finance and Operations a programem Sales.  Szablony Prospekt na gotówkę, które są dostępne w funkcji integracji danych umożliwiają przepływ danych o kontach, kontaktach, produktach, ofertach sprzedaży, zamówieniach sprzedaży i fakturach sprzedaży między programami Finance and Operations a Sales. Poniższa ilustracja przedstawia sposób synchronizacji danych między programami Finance and Operations a Sales.

[![Przepływ danych w rozwiązaniu Prospekt na gotówkę](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Szablony i zadania

Aby wyświetlić dostępne szablony, otwórz [Centrum administracyjne usługi PowerApps](https://preview.admin.powerapps.com/dataintegration). Wybierz opcję **Projekty**, a następnie w prawym górnym rogu wybierz opcję **Nowy projekt**, aby wybrać szablony publiczne.

Następujący szablon i podstawowe zadanie są używane do synchronizowania kont klientów z programu Sales do programu Finance and Operations:

- **Nazwa szablonu w integracji danych:** Konta (Sales do Fin and Ops) — bezpośrednie
- **Nazwa zadania w projekcie:** Konta - odbiorcy

Przed zsynchronizowaniem konta/odbiorcy nie jest wymagane wykonanie zadań synchronizacji.

## <a name="entity-set"></a>Zestaw jednostek

| Sprzedaż    | Finance and Operations |
|----------|------------------------|
| Konta | Odbiorcy V2           |

## <a name="entity-flow"></a>Przepływ jednostek

Konta klientów są zarządzane w programie Sales i synchronizowane z programem Finance and Operations jako odbiorcy. Właściwość **Obsługiwane zewnętrznie** u tych odbiorców ma ustawioną wartość **Tak**, aby śledzić odbiorców pochodzących z aplikacji Sales. Podczas fakturowania ta informacja jest używana do filtrowania faktur synchronizowanych z aplikacją Sales.

## <a name="prospect-to-cash-solution-for-sales"></a>Rozwiązanie Prospekt na gotówkę dla aplikacji Sales

Pole **Numeru konta** jest dostępne na stronie **Konto**. Jego wartość pełni rolę naturalnego i unikatowego klucza wspierającego integrację. Funkcja klucza naturalnego w rozwiązaniu zarządzania relacjami z klientami (CRM) może mieć wpływ na klientów, którzy już korzystają z pola **Numeru konta**, ale którzy nie używają unikatowych wartości **Numer konta** dla każdego poszczególnych kont klientów. Obecnie rozwiązanie integracji nie obsługuje takiego przypadku.

Podczas tworzenia nowego konta klienta jeśli wartość **Numer konta** jeszcze nie istnieje, jest generowana automatycznie przy użyciu numeracji. Wartość składa się z przedrostka **ACC**, następnie rosnącej liczby kolejnej, a na końcu sześcioznakowego przyrostka. Oto przykład: **ACC-01000-BVRCPS**

Gdy rozwiązanie integracji jest stosowane do aplikacji Sales, skrypt uaktualniania ustawia pole **Numer konta** dla istniejących kont klientów w aplikacji Sales. Jeśli nie ma wartości **Numer konta**, jest używana numeracja podana wcześniej.

## <a name="preconditions-and-mapping-setup"></a>Warunki wstępne i ustawienia mapowania

- Mapowanie pola **CustomerGroupId** musi zostać zaktualizowane o prawidłową wartość w programie Finance and Operations. Można określić wartość domyślną albo ustawiać wartość przy użyciu mapy wartości.

    Wartość domyślna w szablonie to **10**.

- Dodając następujące mapowania, można ograniczyć liczbę koniecznych ręcznych aktualizacji wykonywanych w programie Finance and Operations. Można używać wartości domyślnej lub mapy wartości na przykład z ustawienia **Kraj/region** lub **Miejscowość**.

    - **SiteId** — Oddział jest konieczny do generowania ofert i wierszy zamówień sprzedaży w programie Finance and Operations. Domyślny oddział może być pobierany z produktu albo od odbiorcy z nagłówka zamówienia.

        Wartość domyślna w szablonie to **1**.

    - **WarehouseId** — Magazyn jest konieczny do przetwarzania ofert i wierszy zamówień sprzedaży w programie Finance and Operations. Domyślny magazyn może być pobierany z produktu albo od odbiorcy z nagłówka zamówienia w programie Finance and Operations.

        Wartość domyślna w szablonie to **13**.

    - **LanguageId** — Język jest konieczny do generowania ofert i zamówień sprzedaży w programie Finance and Operations. Domyślnie jest używany język z nagłówka zamówienia od odbiorcy.

        Domyślna wartość pola w szablonie to **en-us**.

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

> [!NOTE]
> Pola **Warunki płatności**, **Warunki frachtu**, **Warunki dostawy**, **Metoda wysyłki** i **Metoda dostawy** nie wchodzą w skład zbioru domyślnych mapowań. Aby zamapować te pola, należy skonfigurować mapowanie wartości specyficzne dla danych w organizacjach, między którymi jest synchronizowana jednostka.

Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych. 

> [!NOTE]
> Mapowanie pokazuje, które informacje z pól zostaną zsynchronizowane z rozwiązania Sales do rozwiązania Finance and Operations.

![Mapowanie szablonu w integracji danych](./media/accounts-direct-template-mapping-data-integrator-1.png)

## <a name="related-topics"></a>Powiązane tematy


[Prospekt na gotówkę](prospect-to-cash.md)

[Synchronizowanie kont bezpośrednio w rozwiązaniu Sales do odbiorców w rozwiązaniu Finance and Operations](accounts-template-mapping-direct.md)

[Synchronizowanie kontaktów bezpośrednio w rozwiązaniu Sales do kontaktów lub odbiorców w rozwiązaniu Finance and Operations](contacts-template-mapping-direct.md)

[Synchronizowanie nagłówków i wierszy zamówień sprzedaży w rozwiązaniu Finance and Operations bezpośrednio z elementami w rozwiązaniu Sales](sales-order-template-mapping-direct-two-ways.md)

[Synchronizowanie nagłówków i wierszy faktur sprzedaży bezpośrednio w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales](sales-invoice-template-mapping-direct.md)


