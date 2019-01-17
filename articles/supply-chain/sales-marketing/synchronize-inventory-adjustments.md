---
title: "Synchronizowanie przeniesień i korekt zapasów z Field Service do Finance and Operations"
description: "Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania korekt i przeniesień zapasów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service."
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
ms.openlocfilehash: 79a1cfac3fa94223cc9af73e758ce95fd47065c9
ms.contentlocale: pl-pl
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-inventory-adjustments-from-field-service-to-finance-and-operations"></a>Synchronizowanie korekt zapasów z Field Service do Finance and Operations

[!include[banner](../includes/banner.md)]

Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania korekt i przeniesień zapasów między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Field Service.

[![Synchronizacja procesów biznesowych między aplikacjami Finance and Operations i Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)

## <a name="templates-and-tasks"></a>Szablony i zadania
Poniższy szablon i podstawowe zadania są używane do synchronizowania korekt przeniesień zapasów z Microsoft Dynamics 365 for Finance and Operations do Microsoft Dynamics 365 for Field Service.

**Nazwa szablonów w integracji danych:**
- Korekta zapasów (Field Service do Finance and Operations)
- Przeniesienia zapasów (Field Service do Finance and Operations)

**Nazwy zadań w projektach integracji danych:**
- Korekty zapasów
- Przeniesienia zapasów

## <a name="entity-set"></a>Zestaw jednostek
| Field Service                     | Finance and Operations                             |
|-----------------------------------|----------------------------------------------------|
| msdyn_inventoryadjustmentproducts |   CDS Nagłówki i wiersze arkuszy korekt zapasów |
| msdyn_inventoryadjustmentproducts | CDS Nagłówki i wiersze arkuszy przesunięć magazynowych   |

## <a name="entity-flow"></a>Przepływ jednostek
Korekty i przeniesienia zapasów dokonane w Field Service będą synchronizowane w Finance and Operations, gdy **Stan księgowania** zostaje zmieniony z Utworzone na Zaksięgowane. Gdy to się dzieje, zlecenie korekty lub przeniesienie zostanie zablokowane i stanie się tylko do odczytu, ponieważ korekty i przeniesienia mogą być księgowane w Finance and Operations i dlatego nie mogą być modyfikowane.
W Finance and Operations możesz ustawić zadanie wsadowe do automatycznego księgowania korekt i przenoszenia arkuszy magazynowych wygenerowanych za pomocą integracji. Zobacz wymaganie wstępne poniżej, aby uzyskać szczegółowe informacje o sposobie włączania zadania wsadowego.

## <a name="field-service-crm-solution"></a>Rozwiązanie CRM Field Service 
Pole Jednostka magazynowa zostało dodane do jednostki Produkt. To pole jest wymagane ponieważ jednostka sprzedaży i magazynowa nie zawsze jest taka sama w Operations i dla Zapasów w magazynie w operacjach potrzebujemy jednostki magazynowej.
Po ustawieniu produktu w produkcie korekty zapasów dla korekt zapasów i przeniesień zapasów jednostka zostanie pobrana z wartości produktu w magazynie. Jeśli wartość zostanie znaleziona, pole Jednostka zostanie zablokowane na Produkt korekty zapasów.

Pole Stan księgowania zostało dodane zarówno do jednostki Korekta zapasów, jak i Przeniesienie zapasów. To pole jest używane jako filtr podczas wysyłania korekty lub przeniesienia do Operations. To pole jest ustawiane domyślnie na wartość Utworzono (1), a następnie nie jest wysyłane do Operations. Po wprowadzeniu zmiany na Zaksięgowane (2) następuje wysłanie do operacji, ale nie możesz już zmienić niczego w opcji Korekta lub Przeniesienie anie dodawać tam nowych wierszy.
Pole Sekwencja numerów zostało dodane do jednostki produktu korekty zapasów. To pole pozwala ustawić dla integracji niepowtarzalny numer, dzięki czemu integracja wie, kiedy tworzyć a kiedy aktualizować. Podczas tworzenia pierwszego produktu korekty zapasów utworzy on nowy rekord w jednostce P2C AutoNumber do obsługi serii numerów i używanego prefiksu.

## <a name="prerequisites-and-mapping-setup"></a>Wymagania wstępne i ustawienia mapowania

### <a name="in-finance-and-operations"></a>W programie Finance and Operations
Arkusze magazynowe integracji wygenerowane przez integrację mogą być automatycznie księgowane za pomocą zadania wsadowego. Tę opcję włącza się z: Zarządzanie zapasami > Zadania okresowe > Integracja z usługą CDS > Księguj arkusze magazynowe integracji

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Na poniższych ilustracjach pokazano mapowanie szablonu w narzędziu Integracja danych.

### <a name="inventory-adjustment-field-service-to-finance-and-operations-inventory-adjustment"></a>Korekta zapasów (Field Service do Finance and Operations): Korekta zapasów

[![Mapowanie szablonu w integracji danych](./media/FSAdj1.png)](./media/FSAdj1.png)


### <a name="inventory-transfer-field-service-to-finance-and-operations-inventory-transfer"></a>Przeniesienie zapasów (Field Service do Finance and Operations): Przeniesienie zapasów

[![Mapowanie szablonu w integracji danych](./media/FSTrans1.png)](./media/FSTrans1.png)

