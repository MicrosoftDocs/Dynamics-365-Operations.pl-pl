---
title: Synchronizowanie magazynów z rozwiązania Supply Chain Management do rozwiązania Field Service
description: Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania magazynów między programem Dynamics 365 Supply Chain Management a programem Dynamics 365 Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
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
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: b55a0b9e54eabdcdbd3f858cf3725b8fe833f65d
ms.sourcegitcommit: 0099fb24f5f40ff442020b488ef4171836c35c48
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2019
ms.locfileid: "2653401"
---
# <a name="synchronize-warehouses-from-supply-chain-management-to-field-service"></a>Synchronizowanie magazynów z rozwiązania Supply Chain Management do rozwiązania Field Service

[!include[banner](../includes/banner.md)]

Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania magazynów między programem Dynamics 365 Supply Chain Management a programem Dynamics 365 Field Service.

[![Synchronizacja procesów biznesowych między rozwiązaniami Supply Chain Management i Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)

## <a name="templates-and-tasks"></a>Szablony i zadania
Poniższy szablon i podstawowe zadania są używane do synchronizowania magazynów między rozwiązaniami Supply Chain Management i Field Service.

**Mapowanie szablonu w integracji danych**
- Magazyny (rozwiązanie Supply Chain Management do rozwiązania Field Service)

**Zadani w projekcie integracji danych**
- Magazyn

## <a name="entity-set"></a>Zestaw jednostek
| Field Service    | Zarządzanie łańcuchem dostaw                 |
|------------------|----------------------------------------|
| msdyn_warehouses | Magazyny                             |

## <a name="entity-flow"></a>Przepływ jednostek
Magazyny tworzone i obsługiwane w Supply Chain Management mogą być synchronizowane z Field Service za pomocą projektu integracji danych realizowanego w usłudze Common Data Service (CDS). Żądane magazyny synchronizowane z Field Service mogą kontrolowane za pomocą zaawansowanych zapytań i filtrów w projekcie. Magazyny synchronizowane z Supply Chain Management są tworzone w Field Service z polem **Obsługiwane zewnętrznie** ustawionym na **Tak**, a rekord jest tylko do odczytu.

## <a name="field-service-crm-solution"></a>Rozwiązanie CRM Field Service
Aby umożliwić integrację między programami Field Service i Supply Chain Management, jest wymagana dodatkowa funkcjonalność z rozwiązania CRM Field Service. W rozwiązaniu pole **Obsługiwane zewnętrznie** zostało dodane do jednostki **Magazyn (msdyn_warehouses)**. To pomaga w identyfikacji, czy magazyn jest obsługiwany z Supply Chain Management czy tylko istnieje w Field Service. Ustawienia tego pól obejmują:
- **Tak** — Magazyn pochodził z rozwiązania Supply Chain Management i nie będzie można edytować w rozwiązaniu Sales.
- **Nie** — magazyn został wprowadzony bezpośrednio w Field Service jest obsługiwany w tym miejscu.

Pole **Obsługiwane zewnętrznie** pomaga kontrolować synchronizację poziomów zapasów, korekty, przeniesienia i wykorzystanie w zleceniach. Tylko magazyny z polem **Obsługiwane zewnętrznie** ustawionym na **Tak** mogą być używane do synchronizowania bezpośrednio z tym samym magazynem w innym systemie. 

> [!NOTE]
> Istnieje możliwość utworzenia wielu magazynów w usługach Field Service (z polem **Obsługiwane zewnętrznie** = Nie), a następnie mapowania ich na jeden magazyn z funkcją zaawansowanych zapytań i filtrów. Jest to używane w sytuacjach, w których Field Service ma być wzorcem szczegółowego poziomu magazynu i tylko wysyłać aktualizacje do Supply Chain Management. W takim przypadku Field Service nie będzie odbierał aktualizacji poziomów zapasów z Supply Chain Management. Aby uzyskać dodatkowe informacje, zobacz [Synchronizowanie korekt zapasów z Field Service do Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) oraz [Synchronizowanie zleceń w Field Service ze zleceniami połączonym z projektami w Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

## <a name="prerequisites-and-mapping-setup"></a>Wymagania wstępne i ustawienia mapowania
### <a name="data-integration-project"></a>Projekt integracji danych
Przed synchronizacją magazynów należy upewnić się, że funkcja zaawansowanych zapytań i filtrów w projekcie obejmuje tylko magazyny, które chcesz przenieść z Supply Chain Management do Field Service. Należy zwrócić uwagę, że konieczny będzie magazyn w Field Service, aby zastosować go do zleceń, korekt i przeniesień.  

Aby mieć pewność, że istnieje wartość **Klucz integracji** dla jednostki **msdyn_warehouses**:
1. Przejdź do narzędzia Integracja danych.
2. Wybierz kartę **Zestaw połączeń**.
3. Wybierz zestaw połączeń używany do synchronizacji zleceń pracy.
4. Wybierz kartę **Klucz integracji**.
5. Znajdź jednostkę msdyn_warehouses i sprawdź, czy został dodany klucz **msdyn_name (name)**. Jeśli nie jest widoczny, dodaj go, klikając opcję **Dodaj klucz**, a następnie opcję **Zapisz** u góry strony.

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.

### <a name="warehouses-supply-chain-management-to-field-service-warehouse"></a>Magazyny (rozwiązanie Supply Chain Management do rozwiązania Field Service): Magazyn

[![Mapowanie szablonu w integracji danych](./media/Warehouse1.png)](./media/Warehouse1.png)
