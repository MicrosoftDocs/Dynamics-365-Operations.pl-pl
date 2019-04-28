---
title: Synchronizowanie przeniesień i korekt zapasów z Field Service do Finance and Operations
description: Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania korekt i przeniesień zapasów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.
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
ms.openlocfilehash: 75181661c41d238cdc06ffbb6969a2efd7d88d46
ms.sourcegitcommit: a6d385db6636ef2b7fb6b24d37a2160c8d5a3c0f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "842422"
---
# <a name="synchronize-inventory-adjustments-from-field-service-to-finance-and-operations"></a>Synchronizowanie korekt zapasów z Field Service do Finance and Operations

[!include[banner](../includes/banner.md)]

Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania korekt i przeniesień zapasów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.

[![Synchronizacja procesów biznesowych między aplikacjami Finance and Operations i Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)

## <a name="templates-and-tasks"></a>Szablony i zadania
Poniższy szablon i podstawowe zadania są używane do synchronizowania korekt i przeniesień zapasów między programem Microsoft Dynamics 365 for Field Service a programem Microsoft Dynamics 365 for Finance and Operations.

**Mapowanie szablonów w integracji danych**
- Korekta zapasów (z Field Service do Fin and Ops)
- Przeniesienia zapasów (z Field Service do Fin and Ops)

**Zadania w projektach integracji danych**
- Korekty zapasów
- Przeniesienia zapasów

## <a name="entity-set"></a>Zestaw jednostek
| Field Service                     | Finance and Operations                             |
|-----------------------------------|----------------------------------------------------|
| msdyn_inventoryadjustmentproducts |   CDS Nagłówki i wiersze arkuszy korekt zapasów |
| msdyn_inventoryadjustmentproducts | CDS Nagłówki i wiersze arkuszy przesunięć magazynowych   |

## <a name="entity-flow"></a>Przepływ jednostek
Korekty i przeniesienia zapasów dokonane w Field Service będą synchronizowane w Finance and Operations, gdy **Stan księgowania** zostaje zmieniony z **Utworzone** na **Zaksięgowane**. Kiedy to nastąpi, zamówienie korekty lub przeniesienia zostanie zablokowane i będzie dostępne tylko do odczytu. Oznacza to, że korekty i przeniesienia mogą być księgowane w Finance and Operations, ale nie mogą być modyfikowane. W Finance and Operations możesz ustawić zadanie wsadowe do automatycznego księgowania korekt i przenoszenia arkuszy magazynowych wygenerowanych za pomocą integracji. Zobacz wymagania wstępne poniżej, aby uzyskać szczegółowe informacje o sposobie włączania zadania wsadowego.

## <a name="field-service-crm-solution"></a>Rozwiązanie CRM Field Service 
Pole **Jednostka magazynowa** zostało dodane do jednostki **Produkt**. To pole jest wymagane ponieważ jednostka sprzedaży i magazynowa nie zawsze jest taka sama w Finance and Operations i jednostka magazynowa jest wymagana dla Zapasów w magazynie w Finance and Operations.
Po ustawieniu produktu w produkcie korekty zapasów dla korekt zapasów i przeniesień zapasów jednostka zostanie pobrana z wartości produktu w magazynie. Jeśli wartość zostanie znaleziona, pole **Jednostka** zostanie zablokowane na Produkt korekty zapasów.

Pole **Stan księgowania** zostało dodane zarówno do jednostki **Korekta zapasów**, jak i **Przeniesienie zapasów**. To pole jest używane jako filtr podczas wysyłania korekty lub przeniesienia do Finance and Operations. Domyślną wartością tego pola jest Utworzone (1), ale nie jest ono wysyłane do Finance and Operations. Po zaktualizowaniu wartości Zaksięgowane (2) jest ona wysyłana do Finance and Operations ale potem nie możesz już zmienić korekty ani przeniesienia ani dodawać nowych wierszy.

Pole **Sekwencja numerów** zostało dodane do jednostki **Produktu korekty zapasów**. To pole zapewnia, że integracja ma unikatowy numer, więc integracja może utworzyć i zaktualizować korektę. Podczas tworzenia pierwszego produktu korekty zapasów utworzy on nowy rekord w jednostce **P2C AutoNumber** do obsługi serii numerów i używanego prefiksu.

## <a name="prerequisites-and-mapping-setup"></a>Wymagania wstępne i ustawienia mapowania

### <a name="finance-and-operations"></a>Finance and Operations
Arkusze magazynowe integracji wygenerowane przez integrację mogą być automatycznie księgowane za pomocą zadania wsadowego. Tę opcję włącza się z: **Zarządzanie zapasami > Zadania okresowe > Integracja z usługą CDS > Księguj arkusze magazynowe integracji**.

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.

### <a name="inventory-adjustment-field-service-to-fin-and-ops-inventory-adjustment"></a>Korekta zapasów (Field Service do Finance and Operations): Korekta zapasów

[![Mapowanie szablonu w integracji danych](./media/FSAdj1.png)](./media/FSAdj1.png)


### <a name="inventory-transfer-field-service-to-fin-and-ops-inventory-transfer"></a>Przeniesienie zapasów (Field Service do Finance and Operations): Przeniesienie zapasów

[![Mapowanie szablonu w integracji danych](./media/FSTrans1.png)](./media/FSTrans1.png)
