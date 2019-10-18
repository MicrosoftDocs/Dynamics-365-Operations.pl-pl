---
title: Synchronizowanie zadań projektu bezpośrednio z programu Project Service Automation do programu Finance and Operations
description: W tym temacie omówiono szablon i podstawowe zadanie, które są używane do synchronizowania zadań projektu bezpośrednio z Microsoft Dynamics 365 Project Service Automation do Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: 977037f0e2b313ebf05a3e1616d34567f82e82d7
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250399"
---
# <a name="synchronize-project-tasks-directly-from-project-service-automation-to-finance-and-operations"></a>Synchronizowanie zadań projektu bezpośrednio z programu Project Service Automation do programu Finance and Operations

[!include[banner](../includes/banner.md)]

W tym temacie omówiono szablon i podstawowe zadanie, które są używane do synchronizowania zadań projektu bezpośrednio z Dynamics 365 Project Service Automation do Dynamics 365 Finance.

> [!NOTE]
> - Mechanizmy integracji zadań projektu, kategorii transakcji wydatkowych, szacunków godzin, szacunków wydatków i blokowania funkcji są dostępne w wersji 8.0.
> - Jeśli używasz Enterprise Edition 7.3.0, po zainstalowaniu aktualizacji KB 4132657 i 4132660 możesz używać szablonów, aby integrować zadania projektu, kategorie transakcji wydatkowych, szacunki godzin, szacunki wydatków i wartości rzeczywiste oraz konfigurować blokowanie funkcji. Jeśli należy zresetować zasady podziału księgowań, zalecamy dodatkowo zainstalować aktualizację KB 4131710.
> - Funkcja integrowania wartości rzeczywistych jest dostępna wersji 8.01 i nowszych.

## <a name="data-flow-for-project-service-automation-to-finance"></a>Przepływ danych z programu Project Service Automation do Finance

Rozwiązanie integracji rozwiązania Project Service Automation dp Finance korzysta z funkcji integracji danych do synchronizowania danych między wystąpieniami rozwiązania Project Service Automation oraz Finance and Operations. Szablon integracji, który jest dostępny z funkcji integracji danych, umożliwia przepływ danych dotyczących zadań projektu z rozwiązania Project Service Automation do rozwiązania Finance.

Na poniższej ilustracji przedstawiono, w jaki sposób dane są synchronizowane pomiędzy rozwiązaniami Project Service Automation oraz Finance.

[![Przepływ danych w integracji programu Project Service Automation z programem Finance](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)

## <a name="template-and-task"></a>Szablon i zadanie

Aby uzyskać dostęp do szablonu, w centrum administracyjnym usługi Microsoft PowerApps wybierz opcję **Projekty** i w prawym górnym rogu wybierz opcję **Nowy projekt**, aby wybrać spośród szablonów publicznych.

Następujący szablon i podstawowe zadanie służą do synchronizowania zadań projektu z rozwiązania Project Service Automation do rozwiązania Finance:

- **Nazwa szablonu w narzędziu Integracja danych:** Zadania w projekcie (PSA do Fin and Ops)
- **Nazwa zadania w projekcie:** Zadania w projekcie

Zanim będzie możliwa synchronizacja zadań w projektach, należy zsynchronizować umowy na projekty i projekty.

## <a name="entity-set"></a>Zestaw jednostek

| Project Service Automation | Finanse                             |
|----------------------------|-------------------------------------|
| Zadania w projekcie              | Jednostka integracji zadania projektu |

## <a name="entity-flow"></a>Przepływ jednostek

Zarządzanie zadaniami w projekcie odbywa się w aplikacji Project Service Automation i są one synchronizowane z programem Finance jako działania w projekcie.

## <a name="prerequisites-and-mapping-setup"></a>Wymagania wstępne i ustawienia mapowania

Zanim będzie możliwa synchronizacja zadań w projektach, należy zsynchronizować umowy na projekty i projekty.

## <a name="power-query"></a>Zapytanie zaawansowane

Należy użyć dodatku Microsoft Power Query dla programu Excel do odfiltrowania danych, jeśli jest spełniony następujący warunek:

- Masz rekordy przypisane do zasobów w zadaniu w projekcie.

Jeśli musisz używać narzędzia Power Query, przestrzegaj następującej wytycznej:

- Szablon Zadania w projekcie (PSA do Fin and Ops) ma domyślny filtr, który wyklucza rekordy określonego zasobu z zadania w projekcie przez ustawienie filtru **IsLineTask** na wartość **False**. Jeśli tworzysz własny szablon, musisz dodać ten filtr.

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Poniższa ilustracja przedstawia przykład mapowań zadań szablonu w integracji danych. Mapowanie pokazuje informacje z pola, które zostanie zsynchronizowane z rozwiązania Finance do rozwiązania Project Service Automation.

[![Mapowanie szablonu](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)
