---
title: Synchronizowanie przesunięć magazynowych i korekt z rozwiązania Field Service do rozwiązania Supply Chain Management
description: Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania korekt i przeniesień zapasów między programem Dynamics 365 Supply Chain Management a programem Dynamics 365 Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 04/30/2019
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
ms.openlocfilehash: c989e6efff88768f0b370fc81eea971c5c11bcef
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251645"
---
# <a name="synchronize-inventory-adjustments-from-field-service-to-supply-chain-management"></a>Synchronizowanie korekt magazynowych z rozwiązania Field Service do rozwiązania Supply Chain Management

[!include[banner](../includes/banner.md)]

Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania korekt i przeniesień zapasów między programem Dynamics 365 Supply Chain Management a programem Dynamics 365 Field Service.

[![Synchronizacja procesów biznesowych między rozwiązaniami Supply Chain Management i Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)

## <a name="templates-and-tasks"></a>Szablony i zadania
Poniższy szablon i podstawowe zadania są używane do synchronizowania stanu i przeniesień dostepnych zasobów między rozwiązaniami Supply Chain Management i Field Service.

**Mapowanie szablonów w integracji danych**
- Korekta zapasów (rozwiązanie Field Service do Supply Chain Management)
- Przeniesienia zapasów (rozwiązanie Field Service do Supply Chain Management)

**Zadania w projektach integracji danych**
- Korekty zapasów
- Przeniesienia zapasów

## <a name="entity-set"></a>Zestaw jednostek
| Field Service                     | Zarządzanie łańcuchem dostaw                          |
|-----------------------------------|----------------------------------------------------|
| msdyn_inventoryadjustmentproducts |   CDS Nagłówki i wiersze arkuszy korekt zapasów |
| msdyn_inventoryadjustmentproducts | CDS Nagłówki i wiersze arkuszy przesunięć magazynowych   |

## <a name="entity-flow"></a>Przepływ jednostek
Korekty i przeniesienia zapasów dokonane w Field Service będą synchronizowane w Supply Chain Management, gdy **Stan księgowania** zostaje zmieniony z **Utworzone** na **Zaksięgowane**. Kiedy to nastąpi, zamówienie korekty lub przeniesienia zostanie zablokowane i będzie dostępne tylko do odczytu. Oznacza to, że korekty i przeniesienia mogą być księgowane w Supply Chain Management, ale nie mogą być modyfikowane. W Supply Chain Management możesz ustawić zadanie wsadowe do automatycznego księgowania korekt i przenoszenia arkuszy magazynowych wygenerowanych za pomocą integracji. Zobacz wymagania wstępne poniżej, aby uzyskać szczegółowe informacje o sposobie włączania zadania wsadowego.

## <a name="field-service-crm-solution"></a>Rozwiązanie CRM Field Service 
Pole **Jednostka magazynowa** zostało dodane do jednostki **Produkt**. To pole jest wymagane ponieważ jednostka sprzedaży i magazynowa nie zawsze jest taka sama w Supply Chain Management i jednostka magazynowa jest wymagana dla Zapasów w magazynie w Supply Chain Management.
Po ustawieniu produktu w produkcie korekty zapasów dla korekt zapasów i przeniesień zapasów jednostka zostanie pobrana z wartości produktu w magazynie. Jeśli wartość zostanie znaleziona, pole **Jednostka** zostanie zablokowane na Produkt korekty zapasów.

Pole **Stan księgowania** zostało dodane zarówno do jednostki **Korekta zapasów**, jak i **Przeniesienie zapasów**. To pole jest używane jako filtr podczas wysyłania korekty lub przeniesienia do Supply Chain Management. Domyślną wartością tego pola jest Utworzone (1), ale nie jest ono wysyłane do Supply Chain Management. Po zaktualizowaniu wartości Zaksięgowane (2) jest ona wysyłana do Supply Chain Management ale potem nie możesz już zmienić korekty ani przeniesienia ani dodawać nowych wierszy.

Pole **Sekwencja numerów** zostało dodane do jednostki **Produktu korekty zapasów**. To pole zapewnia, że integracja ma unikatowy numer, więc integracja może utworzyć i zaktualizować korektę. Podczas tworzenia pierwszego produktu korekty zapasów utworzy on nowy rekord w jednostce **P2C AutoNumber** do obsługi serii numerów i używanego prefiksu.

## <a name="prerequisites-and-mapping-setup"></a>Wymagania wstępne i ustawienia mapowania

### <a name="supply-chain-management"></a>Zarządzanie łańcuchem dostaw
Arkusze magazynowe integracji wygenerowane przez integrację mogą być automatycznie księgowane za pomocą zadania wsadowego. Tę opcję włącza się z: **Zarządzanie zapasami > Zadania okresowe > Integracja z usługą CDS > Księguj arkusze magazynowe integracji**.

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.

### <a name="inventory-adjustment-field-service-to-supply-chain-management-inventory-adjustment"></a>Korekta zapasów (z rozwiązania Field Service do Supply Chain Management): Korekta zapasów

[![Mapowanie szablonu w integracji danych](./media/FSAdj1.png)](./media/FSAdj1.png)


### <a name="inventory-transfer-field-service-to-supply-chain-management-inventory-transfer"></a>Przeniesienie zapasów (z rozwiązania Field Service do Supply Chain Management): Przeniesienie zapasów

[![Mapowanie szablonu w integracji danych](./media/FSTrans1.png)](./media/FSTrans1.png)
