---
title: "Synchronizowanie kont w rozwiązaniu Sales do odbiorców w rozwiązaniu Finance and Operations"
description: "Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania kont klientów między programem Microsoft Dynamics 365 for Sales a programem Microsoft Dynamics 365 for Finance and Operations Enterprise Edition."
author: ChristianRytt
manager: AnnBe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: ChristianRytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: b497f078d9786a5c7630e924da6bb04cad37f5e9
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---

# <a name="synchronize-accounts-from-sales-to-customers-in-finance-and-operations"></a>Synchronizowanie kont w rozwiązaniu Sales do odbiorców w rozwiązaniu Finance and Operations

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Zanim zaczniesz używać rozwiązania Prospekt na gotówkę, zapoznaj się z tematem [Integracja danych w usłudze 365 Dynamics](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration). 

Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania kont klientów między programem Microsoft Dynamics 365 for Sales (Sales) a programem Microsoft Dynamics 365 for Finance and Operations Enterprise Edition (Finance and Operations).

## <a name="template-and-task"></a>Szablon i zadanie

Następujące szablony i podstawowe zadania są używane do synchronizowania kont klientów z programu Sales do programu Finance and Operations:

- **Nazwa szablonu:** Konta (z Sales do Fin and Ops)
- **Nazwa zadania w projekcie:** Konta - konto - odbiorcy

Zadania synchronizacji wymagane przed synchronizacją konto/odbiorca: brak

## <a name="entity-set"></a>Zestaw jednostek

| Sprzedaż    | CDS     | Finance and Operations |
|----------|---------|------------------------|
| Konta | Konto | Odbiorcy              |

## <a name="entity-flow"></a>Przepływ jednostek

Konta klientów są zarządzane w programie Sales i synchronizowane z programem Finance and Operations jako odbiorcy. Właściwość **Obsługiwane zewnętrznie** u tych odbiorców ma ustawioną wartość **Tak**, aby śledzić odbiorców pochodzących z aplikacji Sales. Podczas fakturowania ta informacja jest używana do filtrowania faktur synchronizowanych z aplikacją Sales.

## <a name="prospect-to-cash-solution-for-sales"></a>Rozwiązanie Prospekt na gotówkę dla aplikacji Sales

Pole **Numeru konta** jest dostępne na stronie **Konto**. Jego wartość pełni rolę naturalnego i unikatowego klucza wspierającego integrację. Funkcja klucza naturalnego w rozwiązaniu zarządzania relacjami z klientami (CRM) może mieć wpływ na klientów, którzy już korzystają z pola **Numeru konta**, ale którzy nie używają unikatowych wartości **Numer konta** dla każdego poszczególnych kont klientów. Obecnie rozwiązanie integracji nie obsługuje takiego przypadku.

Podczas tworzenia nowego konta klienta jeśli wartość **Numer konta** jeszcze nie istnieje, jest generowana automatycznie przy użyciu numeracji. Wartość składa się z przedrostka **ACC**, następnie rosnącej liczby kolejnej, a na końcu sześcioznakowego przyrostka. Oto przykład: **ACC-01000-BVRCPS**

Gdy rozwiązanie integracji jest stosowane do aplikacji Sales, skrypt uaktualniania ustawia pole **Numer konta** dla istniejących kont klientów w aplikacji Sales. Jeśli nie ma wartości **Numer konta**, jest używana numeracja opisana wcześniej.

## <a name="preconditions-and-mapping-setup"></a>Warunki wstępne i ustawienia mapowania

- Pole **CustomerGroupId** musi zostać zaktualizowane o prawidłową wartość w programie Finance and Operations. Można określić wartość domyślną albo ustawiać wartość przy użyciu mapy wartości. Wartość domyślna w szablonie to **10**.
- Pole **Kod kraju/regionu w adresie** jest wymagane w programie Finance and Operations. Aby uniknąć błędów synchronizacji, można określić wartość domyślną. Ta wartość domyślna będzie następnie używana, jeśli to pole jest pozostawione puste w aplikacji Sales.

    - Domyślna wartość pola **AddressCountryRegionISOCode** w szablonie to **USA**.
    - Domyślną wartością pola **DeliveryAddressCountryRegionISOCode** w szablonie jest **Stany Zjednoczone**.

- Dodając następujące mapowania z okna **CDS &gt; Miejsce docelowe**, można ograniczyć liczbę koniecznych ręcznych aktualizacji wykonywanych w programie Finance and Operations. Można używać wartości domyślnej lub mapy wartości na przykład z ustawienia **Kraj/region** lub **Miejscowość**.

    - **SiteId** — Oddział jest konieczny do generowania ofert i wierszy zamówień sprzedaży w programie Finance and Operations. Domyślny oddział może być pobierany z produktu albo od odbiorcy z nagłówka zamówienia. Domyślną wartością pola **SiteId** w szablonie jest **1**.
    - **WarehouseId** — Magazyn jest konieczny do przetwarzania ofert i wierszy zamówień sprzedaży w programie Finance and Operations. Domyślny magazyn może być pobierany z produktu albo od odbiorcy z nagłówka zamówienia w programie Finance and Operations. Domyślną wartością pola **WarehouseId** w szablonie jest **13**.
    - **LanguageId** — Język jest konieczny do generowania ofert i zamówień sprzedaży w programie Finance and Operations. Domyślnie jest używany język z nagłówka zamówienia od odbiorcy. Domyślna wartość pola **LanguageId** w szablonie to **en-us**.

- Zaktualizuj identyfikator organizacji w usłudze CDS (**Organization_OrganizationId**) w mapowaniu **Źródło &gt; CDS**. Wartość domyślna w szablonie to **ORG001**.

## <a name="template-mapping-in-data-integrator"></a>Mapowanie szablonu w integratorze danych

> [!NOTE]
> Pola **Warunki płatności**, **Warunki frachtu**, **Warunki dostawy**, **Metoda wysyłki** i **Metoda dostawy** nie wchodzą w skład zbioru domyślnych mapowań. Aby zamapować pola, należy skonfigurować mapowanie wartości. Mapowania wartości są specyficzne dla danych w organizacjach, między którymi jest synchronizowana jednostka.

Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych.

![Mapowanie szablonu w integratorze danych](./media/accounts-template-mapping-data-integrator-1.png)

![Mapowanie szablonu dla kont klientów w integratorze danych](./media/accounts-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a>Powiązane tematy

[Synchronizowanie produktów w rozwiązaniu Finance and Operations do produktów w rozwiązaniu Sales](products-template-mapping.md)

[Synchronizowanie kontaktów w rozwiązaniu Sales do kontaktów lub odbiorców w rozwiązaniu Finance and Operations](contacts-template-mapping.md)

[Synchronizowanie nagłówków i wierszy ofert sprzedaży w rozwiązaniu Sales do elementów w rozwiązaniu Finance and Operations](sales-quotation-template-mapping.md)




