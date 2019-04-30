---
title: Synchronizowanie informacji poziomu zapasów między aplikacjami Finance and Operations i Field Service
description: Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania danych poziomu zapasów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 6b2bdf1ca6f6ae43cd85c8a1353ee8305052761d
ms.sourcegitcommit: a6d385db6636ef2b7fb6b24d37a2160c8d5a3c0f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "842563"
---
# <a name="synchronize-inventory-level-information-from-finance-and-operations-to-field-service"></a>Synchronizowanie informacji na poziomie zapasów z rozwiązania Finance and Operations do rozwiązania Field Service 

[!include[banner](../includes/banner.md)]

Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania danych poziomu zapasów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.

[![Synchronizacja procesów biznesowych między aplikacjami Finance and Operations i Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)

## <a name="templates-and-tasks"></a>Szablony i zadania
Poniższy szablon i podstawowe zadania są używane do synchronizowania poziomów dostępnych zapasów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.

**Mapowanie szablonu w integracji danych**
- Zapasy produktu (z Fin and Ops do Field Service)
  
**Zadani w projekcie integracji danych**
- Zapasy produktu

Następujące zadania synchronizacji są wymagane, zanim będzie można zsynchronizować poziomy zapasów:
- Magazyny (z Fin and Ops do Field Service) 
- Produkty Field Service z jednostką magazynową (Finance and Operations do Sales) 

## <a name="entity-set"></a>Zestaw jednostek

| Field Service                      | Finance and Operations                 |
|------------------------------------|----------------------------------------|
| msdynce_externalproductinventories | CDS Dostępne zapasy według magazynu     |

## <a name="entity-flow"></a>Przepływ jednostek
Informacje poziomu zapasów z Finance and Operations są wysyłane do Field Service dla wybranych produktów. Informacje poziomu zapasów obejmują: 
- Dostępna ilość (aktualnie zarejestrowana fizyczna ilość znajdująca się w magazynie)
- Ilość na zamówieniach (łączna ilość na zamówieniach sprzedaży)
- Zamówiona ilość (łączna ilość na zamówieniach zakupu)

Te informacje są rejestrowane według zwalnianych produktów dla każdego magazynu i synchronizowane w oparciu o śledzenie zmian, gdy poziomy zapasów się zmieniają.

W Field Service rozwiązanie integracji tworzy arkusze magazynowe dla różnicy, aby dopasować w Field Service z poziomami w Finance and Operations.

Finance and Operations będzie działać jako wzorzec poziomów zapasów. Dlatego ważne jest skonfigurowanie integracji dla zleceń, przeniesień i korekt z Field Service do Finance and Operations, jeśli ta funkcja jest używana w Field Service, razem z synchronizacją poziomów zapasów z Finance and Operations.

Produkty i magazyny, w których poziomy zapasów są wzorowane na Finance and Operations mogą być kontrolowane za pomocą funkcji Zaawansowane zapytania i filtrowanie (Zapytanie zaawansowane).

> [!NOTE]
> Istnieje możliwość utworzenia wielu magazynów w usługach Field Service (z polem **Obsługiwane zewnętrznie = Nie**), a następnie mapowania ich na jeden magazyn w Finance and Operations z funkcją zaawansowanych zapytań i filtrów. Jest to używane w sytuacjach, w których Field Service ma być wzorcem szczegółowego poziomu magazynu i tylko wysyłać aktualizacje do Finance and Operations. W takim przypadku Field Service nie będzie odbierał aktualizacji poziomów zapasów z Finance and Operations. Aby uzyskać dodatkowe informacje, zobacz [Synchronizowanie korekt zapasów z Field Service do Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) oraz [Synchronizowanie zleceń w Field Service ze zleceniami połączonym z projektami w Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

## <a name="field-service-crm-solution"></a>Rozwiązanie CRM Field Service
**Jednostka magazynowa Produkt zewnętrzny** jest używana tylko do integracji w systemach zaplecza. Ta jednostka odbiera wartości poziomu zapasów z Finance and Operations w ramach integracji, a następnie przekształca te wartości na ręczne arkusze magazynowe, które następnie zmieniają produkty zapasów w magazynie.

## <a name="prerequisites-and-mapping-setup"></a>Wymagania wstępne i ustawienia mapowania

### <a name="data-integration-project"></a>Projekt integracji danych
Można zastosować filtry za pomocą funkcji Zaawansowane zapytanie i filtrowanie, aby tylko niektóre produkty i magazyny wysyłały informacji o poziomie zapasów z Finance and Operations do Field Service.

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

### <a name="product-inventory-fin-and-ops-to-field-service-product-inventory"></a>Zapasy produktu (Finance and Operations do Field Service): Zapasy produktu

[![Mapowanie szablonu w integracji danych](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)
