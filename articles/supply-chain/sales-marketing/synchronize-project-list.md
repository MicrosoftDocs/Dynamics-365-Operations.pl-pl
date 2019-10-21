---
title: Synchronizowanie listy projektów z rozwiązania Supply Chain Management do rozwiązania Field Service
description: W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania projektów z Dynamics 365 Supply Chain Management do Dynamics 365 Field Service.
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
ms.openlocfilehash: b74a7f0445b3bdad671da4c61e561bc0d9d80cd1
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251599"
---
# <a name="synchronize-project-list-from-supply-chain-management-to-field-service"></a>Synchronizowanie listy projektów z rozwiązania Supply Chain Management do rozwiązania Field Service

[!include[banner](../includes/banner.md)]

W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania projektów z Dynamics 365 Supply Chain Management do Dynamics 365 Field Service.

[![Synchronizacja procesów biznesowych między rozwiązaniami Supply Chain Management i Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)

## <a name="templates-and-tasks"></a>Szablony i zadania
Poniższy szablon i podstawowe zadania są używane do synchronizowania projektów między rozwiązaniami Supply Chain Management i Field Service.

**Mapowanie szablonu w integracji danych**
- Projekty (rozwiązanie Supply Chain Management do rozwiązania Field Service)

**Zadani w projekcie integracji danych**
- Projekty

Następujące zadania synchronizacji są wymagane, zanim będzie można zsynchronizować listę projektu:
- Konta (Sales do Supply Chain Management) 

## <a name="entity-set"></a>Zestaw jednostek
| Field Service           | Zarządzanie łańcuchem dostaw  |
|-------------------------|-------------------------|
|msdynce_externalprojects | Projekty                |

## <a name="entity-flow"></a>Przepływ jednostek
Projekt zewnętrzny jest utworzony w Supply Chain Management. Projekty z **Typem projektu** ustawionym na **Czas i materiał** i **Etapem projektu** ustawionym na **W toku** będą synchronizowały się z jednostką **Projekt zewnętrzny** w Field Service, w tym z numerem projektu, nazwą projektu, etapem projektu i kontem klienta. **Projekt zewnętrzny** jest listą używaną do tworzenia par zleceń Field service i projektów Supply Chain Management.

## <a name="field-service-crm-solution"></a>Rozwiązanie CRM Field Service
Jednostka **Projekt zewnętrzny** pobiera wszystkie projekty z Supply Chain Management. Pole **Projekt zewnętrzny** zostało dodane do jednostka **Zlecenie**. Jest to pole wyszukiwania, więc dzięki oznaczeniu zlecenia za pomocą projektu, zlecenie sprzedaży będzie połączone z projektem w Supply Chain Management. Gdy **Stan systemu** zmieni się z **Otwarte — w toku (690,970,000)** na wyższy status, pole **Projekt zewnętrzny** zostanie zablokowane i nie można dodawać, usuwać ani zmieniać wartości.

## <a name="prerequisites-and-mapping-setup"></a>Wymagania wstępne i ustawienia mapowania
### <a name="supply-chain-management"></a>Zarządzanie łańcuchem dostaw
Włączanie śledzenia zmian w projektach jednostek danych

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych


### <a name="projects-supply-chain-management-to-field-service-projects"></a>Projekty (rozwiązanie Supply Chain Management do rozwiązania Field Service): Porjekty

[![Mapowanie szablonu w integracji danych](./media/FSProject1.png)](./media/FSProject1.png)
