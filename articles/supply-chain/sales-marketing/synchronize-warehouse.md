---
title: "Synchronizowanie magazynów między aplikacjami Finance and Operations i Field Service"
description: "Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania magazynów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 10/10/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.translationtype: HT
ms.sourcegitcommit: 8c6cb481f1a3fe48d329c5936118d8df88a4175b
ms.openlocfilehash: eb8ba6051777e27bd44504a8160118e8096b1435
ms.contentlocale: pl-pl
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-warehouses-from-finance-and-operations-to-field-service"></a>Synchronizowanie magazynów między aplikacjami Finance and Operations i Field Service

[!include[banner](../includes/banner.md)]

Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania magazynów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.

[![Synchronizacja procesów biznesowych między aplikacjami Finance and Operations i Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)

## <a name="templates-and-tasks"></a>Szablony i zadania
Poniższy szablon i podstawowe zadania są używane do synchronizowania magazynów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.

**Nazwa szablonu w integracji danych:**
- Magazyny (Finance and Operations do Field Service)

**Nazwy zadań w projekcie integracji danych:**
- Magazyn

## <a name="entity-set"></a>Zestaw jednostek
| Field Service    | Finance and Operations                 |
|------------------|----------------------------------------|
| msdyn_warehouses | Magazyny                             |

## <a name="entity-flow"></a>Przepływ jednostek
Magazyny tworzone i obsługiwane w Finance and Operations mogą być synchronizowane z Field Service za pomocą projektu integracji danych realizowanego w usłudze Common Data Service (CDS). Żądane magazyny synchronizowane z Field Service mogą kontrolowane za pomocą zaawansowanych zapytań i filtrów w projekcie. Magazyny synchronizowane z Finance and Operations są tworzone w Field Service z polem Obsługiwane zewnętrznie ustawionym na Tak, a rekord jest tylko do odczytu.
Rozwiązanie CRM Field Service Aby umożliwić integrację między programami Field Service i Finance and Operations, jest wymagana dodatkowa funkcjonalność z rozwiązania CRM Field Service. To rozwiązanie obejmuje następujące zmiany.
Pole **Obsługiwane zewnętrznie** zostało dodane do jednostki **Magazyn (msdyn_warehouses)**. To pomaga w identyfikacji, czy magazyn jest obsługiwany z operacji czy tylko istnieje w Field Service.
- Tak — magazyn pochodził z rozwiązania Finance and Operations i nie będzie można edytować w rozwiązaniu Sales.
- Nie — magazyn został wprowadzony bezpośrednio w Field Service jest obsługiwany w tym miejscu.

Pole **Obsługiwane zewnętrznie** pomaga kontrolować synchronizację poziomów zapasów, korekty, przeniesienia i wykorzystanie w zleceniach. Tylko magazyny z polem **Obsługiwane zewnętrznie** ustawionym na Tak mogą być używane do synchronizowania bezpośrednio z tym samym magazynem w innym systemie. 

Uwaga: Istnieje możliwość utworzenia wielu magazynów w usługach Field Service (z polem **Obsługiwane zewnętrznie** = Nie), a następnie mapowania ich na jeden magazyn w Finance and Operations z funkcją zaawansowanych zapytań i filtrów. Jest to używane w sytuacjach, w których Field Service ma być wzorcem szczegółowego poziomu magazynu i tylko wysyłać aktualizacje do Finance and Operations. W takim przypadku Field Service nie będzie odbierał aktualizacji poziomów zapasów z Finance and Operations. Zobacz dodatkowe informacje w tematach Synchronizowanie korekt zapasów z Field Service do Finance and Operations oraz Synchronizowanie zleceń w Field Service ze zleceniami połączonym z projektami w Finance and Operations.

## <a name="prerequisites-and-mapping-setup"></a>Wymagania wstępne i ustawienia mapowania
### <a name="in-the-data-integration-project"></a>W projekcie integracji danych
Przed synchronizacją magazynów należy upewnić się, że funkcja zaawansowanych zapytań i filtrów w projekcie obejmuje tylko magazyny, które chcesz przenieść z Finance and Operations do Field Service. Należy zwrócić uwagę, że konieczny będzie magazyn w Field Service, aby zastosować go do zleceń, korekt i przeniesień.  

Upewnij się, istnieje wartość **Klucz integracji** dla jednostki **msdyn_warehouses**
1. Przejdź do narzędzia Integracja danych.
2. Wybierz kartę **Zestaw połączeń**.
3. Wybierz zestaw połączeń używany do synchronizacji zleceń pracy.
4. Wybierz kartę **Klucz integracji**.
5. Znajdź jednostkę msdyn_warehouses i sprawdź, czy został dodany klucz **msdyn_name (name)**. Jeśli nie jest widoczny, dodaj go, klikając opcję **Dodaj klucz**, a następnie opcję **Zapisz** u góry strony.

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.

### <a name="warehouses-finance-and-operations-to-field-service-warehouse"></a>Magazyny (Finance and Operations do Field Service): Magazyn

[![Mapowanie szablonu w integracji danych](./media/Warehouse1.png)](./media/Warehouse1.png)
