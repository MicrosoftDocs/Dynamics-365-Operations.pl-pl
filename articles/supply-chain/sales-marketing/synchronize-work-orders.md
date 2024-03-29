---
title: Synchronizowanie zleceń z projektem z rozwiązania Field Service do Supply Chain Management
description: Ten artykuł zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania zamówień z numerem projektu między programem Dynamics 365 Field Service a Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 03/12/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: henrikan
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: a43a7f7e900205bdb23fb9a35ca1518369683a42
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860501"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-supply-chain-management"></a>Synchronizowanie zleceń z projektem z rozwiązania Field Service do Supply Chain Management

[!include[banner](../includes/banner.md)]

Ten artykuł zawiera omówienie szablonów i podstawowego zadania, które są używane do synchronizowania zamówień z numerem projektu między programem Dynamics 365 Field Service a Dynamics 365 Supply Chain Management.

[![Synchronizacja procesów biznesowych między rozwiązaniami Supply Chain Management i Field Service.](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)

Używany szablon **Zlecenia z projektem (z Field Service do Supply Chain Management)** jest oparty na szablonie **Zlecenia (z Field Service do Supply Chain Management)**. Więcej informacji znajduje się w temacie [Synchronizowanie zleceń pracy w rozwiązaniu Field Service z zamówieniami sprzedaży w rozwiązaniu Supply Chain Management](/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order)

W tym artykule opisano tylko różnice między dwoma szablonami:
- **Zlecenia pracy z projektem (Field Service do Supply Chain Management)**
- **Zlecenia pracy (Field Service do Supply Chain Management)**

Główna różnica polega na tym, że ten szablon obejmuje mapowanie numeru projektu przypisanego do zlecenia w aplikacji Field Service, który zapewnia, że zlecenie sprzedaży utworzone w aplikacji Supply Chain Management zawiera numer projektu i że fakturowanie może zostać wykonane w odniesieniu do powiązanego projektu. Poza tym szablon używa Zaawansowanego zapytania i filtrowania.

## <a name="templates-and-tasks"></a>Szablony i zadania

**Nazwa szablonu w integracji danych:**

- Zlecenia pracy z projektem (Field Service do Supply Chain Management)

**Nazwa zadania w projekcie integracji danych:**

- WorkOrderHeader
- WorkOrderHeaderProject
- WorkOrderProduct
- WorkOrderService

## <a name="field-service-crm-solution"></a>Rozwiązanie CRM Field Service
Pole **Projekt zewnętrzny** zostało dodane do jednostka Zlecenie. Jest to pole wyszukiwania, więc dzięki oznaczeniu zlecenia pracy za pomocą projektu, zlecenie sprzedaży będzie połączone z projektem w Supply Chain Management. Gdy **Stan systemu** zmieni się z Otwarte — w toku (690 970 000) na wyższy status, to pole **Projekt zewnętrzny** zostanie zablokowane i nie można dodawać, usuwać ani zmieniać wartości.

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheader"></a>Zlecenia pracy z projektem (Field Service do Supply Chain Management): WorkOrderHeader

[![Mapowanie szablonów w integracji danych, zlecenia pracy z projektem (Field Service do Supply Chain Management): WorkOrderHeader.](./media/FSWOP1.png)](./media/FSWOP1.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheaderproject"></a>Zlecenia pracy z projektem (Field Service do Supply Chain Management): WorkOrderHeaderProject

[![Mapowanie szablonów w integracji danych, zlecenia pracy z projektem (Field Service do Supply Chain Management): WorkOrderHeaderProject.](./media/FSWOP2.png)](./media/FSWOP2.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderproduct"></a>Zlecenia pracy z projektem (Field Service do Supply Chain Management): WorkOrderProduct

[![Mapowanie szablonów w integracji danych, zlecenia pracy z projektem (Field Service do Supply Chain Management): WorkOrderProduct.](./media/FSWOP3.png)](./media/FSWOP3.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderservice"></a>Zlecenia pracy z projektem (Field Service do Supply Chain Management): WorkOrderService

[![Mapowanie szablonów w integracji danych, zlecenia pracy z projektem (Field Service do Supply Chain Management): WorkOrderService.](./media/FSWOP4.png)](./media/FSWOP4.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]