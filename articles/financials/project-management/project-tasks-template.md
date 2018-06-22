---
title: "Synchronizowanie zadań w projekcie z programu Project Service Automation"
description: "Ten temat zawiera opis szablonu i podstawowego zadania, które jest używane do synchronizowania zadań projektu bezpośrednio między programem Microsoft Dynamics 365 for Project Service Automation a programem Microsoft Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: 399b519ab0da4de405aeb06f3e7f4bf29a6c5cc3
ms.openlocfilehash: 89df0d99d780441ad08cd6bff3e1fd203694eb8e
ms.contentlocale: pl-pl
ms.lasthandoff: 05/30/2018

---

# <a name="synchronize-project-tasks-from-project-service-automation-directly-to-project-activities-in-finance-and-operations"></a>Synchronizowanie zadań w projekcie z programu Project Service Automation bezpośrednio do działań w projekcie w programie Finance and Operations

Ten temat zawiera opis szablonu i podstawowego zadania, które jest używane do synchronizowania zadań projektu bezpośrednio między programem Microsoft Dynamics 365 for Project Service Automation a programem Microsoft Dynamics 365 for Finance and Operations.

> [!NOTE]
> Mechanizmy integracji zadań projektu, kategorii transakcji wydatkowych, szacunków godzin, szacunków wydatków i blokowania funkcji są dostępne w programie Dynamics 365 for Finance and Operations w wersji 8.0.

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Przepływ danych z programu Project Service Automation do Finance and Operations

Rozwiązanie integracji rozwiązania Project Service Automation z rozwiązaniem Finance and Operations korzysta z funkcji integracji danych do synchronizowania danych między wystąpieniami rozwiązania Project Service Automation oraz rozwiązania Finance and Operations. Szablon integracji, który jest dostępny z funkcji integracji danych, umożliwia przepływ danych dotyczących zadań projektu z rozwiązania Project Service Automation do rozwiązania Finance and Operations.

Na poniższej ilustracji przedstawiono, w jaki sposób dane są synchronizowane pomiędzy rozwiązaniami Project Service Automation oraz Finance and Operations.

[![Przepływ danych w integracji programu Project Service Automation z programem Finance and Operations](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)

## <a name="template-and-task"></a>Szablon i zadanie

Aby uzyskać dostęp do szablonu w programie Microsoft PowerApps Admin Center wybierz **Projekty**i w prawym górnym rogu, wybierz **Nowy projekt**, aby wybierać szablony publiczne.

Następujący szablon i zadanie podrzędne służy do synchronizowania zadań projektu z rozwiązania Project Service Automation do rozwiązania Finance and Operations:

-**Nazwa szablonu w narzędziu Integracja danych:** Zadania w projekcie (PSA do Fin and Ops) -**Nazwa zadania w projekcie:** Zadania w projekcie

Zanim będzie możliwa synchronizacja zadań w projektach, należy zsynchronizować umowy na projekty i projekty.

## <a name="entity-set"></a>Zestaw jednostek

|Project Service Automation               | Finance and Operations                |
|-----------------------------------------|---------------------------------------|
| Zadania w projekcie                           | Jednostka integracji zadania projektu.   |

## <a name="entity-flow"></a>Przepływ jednostek

Zarządzanie zadaniami w projekcie odbywa się w aplikacji Project Service Automation i są one synchronizowane z programem Finance and Operations jako działania w projekcie.

## <a name="prerequisites-and-mapping-setup"></a>Wymagania wstępne i ustawienia mapowania

Zanim będzie możliwa synchronizacja zadań w projektach, należy zsynchronizować umowy na projekty i projekty.

## <a name="power-query"></a>Zapytanie zaawansowane

Należy użyć programu Microsoft Power Query do odfiltrowania danych, jeśli są spełnione te warunki:

- Masz rekordy przypisane do zasobów w ramach zadania w projekcie.

Jeśli musisz używać narzędzia Power Query, przestrzegaj następujących wytycznych:

- Szablon Zadania w projekcie (PSA do Fin and Ops) ma domyślny filtr do wykluczania rekordów określonego zasobu z w ramach zadania w projekcie przez ustawienie filtru na **IsLineTask** na wartość **False**. Jeśli tworzysz własny szablon, musisz dodać ten filtr.

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Poniższa ilustracja przedstawia przykład mapowań zadań szablonu w integracji danych. Mapowanie pokazuje informacje z pola, które zostanie zsynchronizowane z rozwiązania Finance and Operations do rozwiązania Project Service Automation.

[![Mapowanie szablonu](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)


