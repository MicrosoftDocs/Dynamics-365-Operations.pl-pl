---
title: "Synchronizowanie listy projekty między aplikacjami Finance and Operations i Field Service"
description: "Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania projektów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
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
ms.openlocfilehash: adcb1c1b241ce2b073cd26cf2a8a8d64931c8b0f
ms.contentlocale: pl-pl
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a>Synchronizowanie listy projekty między aplikacjami Finance and Operations i Field Service

[!include[banner](../includes/banner.md)]

Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania projektów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.

[![Synchronizacja procesów biznesowych między aplikacjami Finance and Operations i Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)

## <a name="templates-and-tasks"></a>Szablony i zadania
Poniższy szablon i podstawowe zadania są używane do synchronizowania projektów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.

**Nazwa szablonu w integracji danych:**
- Projekty (Finance and Operations do Field Service)

**Nazwy zadań w projekcie integracji danych:**
- Projekty

Następujące zadania synchronizacji są wymagane, zanim będzie można zsynchronizować listę projektu:
- Konta (Sales do Finance and Operations) 

## <a name="entity-set"></a>Zestaw jednostek
Field Service   Finance and Operations

| Field Service           | Finance and Operations  |
|-------------------------|-------------------------|
|msdynce_externalprojects | Projekty                |

## <a name="entity-flow"></a>Przepływ jednostek
Projekty są tworzone w Finance and Operations. Projekty z **Typem projektu** Czas i materiał i **Etapem projektu** W toku będą synchronizowały się z jednostką **Projekt zewnętrzny** w Field Service, w tym z numerem projektu, nazwą projektu, etapem projektu i kontem klienta. Lista **Projekt zewnętrzny** jest używana do tworzenia par zleceń Field service i projektów Finance and Operations.
Rozwiązanie CRM Field Service Projekt zewnętrzny jest nową jednostką, która otrzymuje wszystkie projekty z Operations.
Pole Projekt zewnętrzny zostało dodane do jednostka Zlecenie. To pole jest wyszukiwaniem i zakupem, które wyzwalają Zlecenie z projektem; następnie Zlecenie sprzedaży jest łączone z Projektem w Operations. Gdy Stan systemu zmieni się z Otwarte — w toku (690,970,000) na wyższy status, pole Projekt zewnętrzny zostanie zablokowane i nie można dodawać, usuwać ani zmieniać wartości.

## <a name="prerequisites-and-mapping-setup"></a>Wymagania wstępne i ustawienia mapowania
### <a name="in-finance-and-operations"></a>W programie Finance and Operations
Włączanie śledzenia zmian w projektach jednostek danych

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych


### <a name="projects-finance-and-operations-to-field-service-projects"></a>Projekty (Finance and Operations do Field Service): Projekty

[![Mapowanie szablonu w integracji danych](./media/FSProject1.png)](./media/FSProject1.png)

