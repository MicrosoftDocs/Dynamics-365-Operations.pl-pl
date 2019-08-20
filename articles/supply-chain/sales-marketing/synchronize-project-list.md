---
title: Synchronizowanie listy projekty między aplikacjami Finance and Operations i Field Service
description: W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania projektów z Microsoft Dynamics 365 for Finance and Operations do Microsoft Dynamics 365 for Field Service.
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
ms.openlocfilehash: 535094821ca7efa33bf40f2057fac8ffc17bb822
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843560"
---
# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a>Synchronizowanie listy projektów z rozwiązania Finance and Operations do rozwiązania Field Service

[!include[banner](../includes/banner.md)]

W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania projektów z Microsoft Dynamics 365 for Finance and Operations do Microsoft Dynamics 365 for Field Service.

[![Synchronizacja procesów biznesowych między aplikacjami Finance and Operations i Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)

## <a name="templates-and-tasks"></a>Szablony i zadania
Poniższy szablon i podstawowe zadania są używane do synchronizowania projektów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.

**Mapowanie szablonu w integracji danych**
- Projekty (z Fin and Ops do Field Service)

**Zadani w projekcie integracji danych**
- Projekty

Następujące zadania synchronizacji są wymagane, zanim będzie można zsynchronizować listę projektu:
- Produkty (z Sales do Fin and Ops) 

## <a name="entity-set"></a>Zestaw jednostek
| Field Service           | Finance and Operations  |
|-------------------------|-------------------------|
|msdynce_externalprojects | Projekty                |

## <a name="entity-flow"></a>Przepływ jednostek
Projekty są tworzone w Finance and Operations. Projekty z **Typem projektu** ustawionym na **Czas i materiał** i **Etapem projektu** ustawionym na **W toku** będą synchronizowały się z jednostką **Projekt zewnętrzny** w Field Service, w tym z numerem projektu, nazwą projektu, etapem projektu i kontem klienta. **Projekt zewnętrzny** jest listą używaną do tworzenia par zleceń Field service i projektów Finance and Operations.

## <a name="field-service-crm-solution"></a>Rozwiązanie CRM Field Service
Jednostka **Projekt zewnętrzny** pobiera wszystkie projekty z Finance and Operations. Pole **Projekt zewnętrzny** zostało dodane do jednostka **Zlecenie**. Jest to pole wyszukiwania, więc dzięki oznaczeniu zlecenia za pomocą projektu, zlecenie sprzedaży będzie połączone z projektem w Finance and Operations. Gdy **Stan systemu** zmieni się z **Otwarte — w toku (690,970,000)** na wyższy status, pole **Projekt zewnętrzny** zostanie zablokowane i nie można dodawać, usuwać ani zmieniać wartości.

## <a name="prerequisites-and-mapping-setup"></a>Wymagania wstępne i ustawienia mapowania
### <a name="finance-and-operations"></a>Finance and Operations
Włączanie śledzenia zmian w projektach jednostek danych

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych


### <a name="projects-fin-and-ops-to-field-service-projects"></a>Projekty (z Fin and Ops do Field Service): Projekty

[![Mapowanie szablonu w integracji danych](./media/FSProject1.png)](./media/FSProject1.png)
