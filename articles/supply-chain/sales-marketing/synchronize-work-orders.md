---
title: Synchronizowanie zamówień z projektem między aplikacjami Field Service i Finance and Operations
description: Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania zamówień z numerem projektu między programem Microsoft Dynamics 365 for Field Service a Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 03/12/2019
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
ms.openlocfilehash: 5ca01b085315d916a18c512af28fc7534ce76ee8
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1536740"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a>Synchronizowanie zamówień z projektem między aplikacjami Field Service i Finance and Operations

[!include[banner](../includes/banner.md)]

Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania zamówień z numerem projektu między programem Microsoft Dynamics 365 for Field Service a Microsoft Dynamics 365 for Finance and Operations.

[![Synchronizacja procesów biznesowych między aplikacjami Finance and Operations i Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)

Używany szablon **Zlecenia z projektem (z Field Service do Fin and Ops)** jest oparty na szablonie **Zlecenia (z Field Service do Fin Ops)**. Więcej informacji znajduje się w temacie [Synchronizowanie zleceń pracy w rozwiązaniu Field Service z zamówieniami sprzedaży w rozwiązaniu Finance and Operations](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order)

W tym temacie opisano tylko różnice między dwoma szablonami:
- **Zlecenia z projektem (z Field Service do Finance and Operations)**
- **Zlecenia (z Field Service do Finance and Operations)**

Główna różnica polega na tym, że ten szablon obejmuje mapowanie numeru projektu przypisanego do zlecenia w aplikacji Field Service, który zapewnia, że zlecenie sprzedaży utworzone w aplikacji Finance and Operations zawiera numer projektu i że fakturowanie może zostać wykonane w odniesieniu do powiązanego projektu. Poza tym szablon używa Zaawansowanego zapytania i filtrowania.

## <a name="templates-and-tasks"></a>Szablony i zadania

**Nazwa szablonu w integracji danych:**

- Zlecenia z projektem (z Field Service do Finance and Operations)

**Nazwa zadania w projekcie integracji danych:**

- WorkOrderHeader
- WorkOrderHeaderProject
- WorkOrderProduct
- WorkOrderService

## <a name="field-service-crm-solution"></a>Rozwiązanie CRM Field Service
Pole **Projekt zewnętrzny** zostało dodane do jednostka Zlecenie. To pole jest wyszukiwaniem i zakupem, które wyzwalają Zlecenie z projektem; następnie Zlecenie sprzedaży jest łączone z Projektem w Finance and Operations. Gdy **Stan systemu** zmieni się z Otwarte — w toku (690,970,000) na wyższy status, pole **Projekt zewnętrzny** zostanie zablokowane i nie można dodawać, usuwać ani zmieniać wartości.

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheader"></a>Zlecenia z projektem (z Field Service do Finance and Operations): WorkOrderHeader

[![Mapowanie szablonu w integracji danych](./media/FSWOP1.png)](./media/FSWOP1.png)

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheaderproject"></a>Zlecenia z projektem (z Field Service do Finance and Operations): WorkOrderHeaderProject

[![Mapowanie szablonu w integracji danych](./media/FSWOP2.png)](./media/FSWOP2.png)

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderproduct"></a>Zlecenia z projektem (z Field Service do Finance and Operations): WorkOrderProduct

[![Mapowanie szablonu w integracji danych](./media/FSWOP3.png)](./media/FSWOP3.png)

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderservice"></a>Zlecenia z projektem (z Field Service do Finance and Operations): WorkOrderService

[![Mapowanie szablonu w integracji danych](./media/FSWOP4.png)](./media/FSWOP4.png)
