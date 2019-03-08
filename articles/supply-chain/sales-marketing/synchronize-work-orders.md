---
title: Synchronizowanie zamówień z projektem między aplikacjami Field Service i Finance and Operations
description: Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania zamówień z numerem projektu między programem Microsoft Dynamics 365 for Field Service a Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
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
ms.openlocfilehash: 6b61411a5a235e2d0aad8bb25ae4a3bfcf1248d1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "329857"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a>Synchronizowanie zamówień z projektem między aplikacjami Field Service i Finance and Operations

[!include[banner](../includes/banner.md)]

Ten temat zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania zamówień z numerem projektu między programem Microsoft Dynamics 365 for Field Service a Microsoft Dynamics 365 for Finance and Operations.

[![Synchronizacja procesów biznesowych między aplikacjami Finance and Operations i Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)

Używany szablon **Produkty programu Field Service (z Finance and Operations do Field Service)** jest oparty na szablonie **Produkty (z Finance and Operations do Sales) — bezpośrednie** rozwiązania Prospekt na gotówkę. Aby uzyskać więcej informacji, zobacz [Produkty (z rozwiązania Finance and Operations do rozwiązania Sales) – bezpośrednio](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).

Ten temat wyłącznie opisuje różnice między szablonami **Produkty programu Field Service (z Finance and Operations do Field Service)** i **Produkty Field Service (z Finance and Operations do Field Service) — bezpośrednie**.

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

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheader"></a>Zlecenia z projektem (z Field Service do Finance and Operations): WorkOrderHeader

[![Mapowanie szablonu w integracji danych](./media/FSWOP1.png)](./media/FSWOP1.png)

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheaderproject"></a>Zlecenia z projektem (z Field Service do Finance and Operations): WorkOrderHeaderProject

[![Mapowanie szablonu w integracji danych](./media/FSWOP2.png)](./media/FSWOP2.png)

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderproduct"></a>Zlecenia z projektem (z Field Service do Finance and Operations): WorkOrderProduct

[![Mapowanie szablonu w integracji danych](./media/FSWOP3.png)](./media/FSWOP3.png)

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderservice"></a>Zlecenia z projektem (z Field Service do Finance and Operations): WorkOrderService

[![Mapowanie szablonu w integracji danych](./media/FSWOP4.png)](./media/FSWOP4.png)
