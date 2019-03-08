---
title: Synchronizowanie kategorii wydatków w projekcie między programami Finance and Operations i Project Service Automation
description: Ten temat zawiera opis szablonów i podstawowych zadań, które są używane do synchronizowania kategorii wydatków projektu bezpośrednio między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Project Service Automation.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: c4d09fde2cf4335553243c136590f9f3135db97a
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "347843"
---
# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a>Synchronizowanie kategorii wydatków w projekcie między programami Finance and Operations i Project Service Automation

[!include[banner](../includes/banner.md)]

Ten temat zawiera opis szablonów i podstawowych zadań, które są używane do synchronizowania kategorii wydatków projektu bezpośrednio między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Project Service Automation.

> [!NOTE]
> - Mechanizmy integracji zadań projektu, kategorii transakcji wydatkowych, szacunków godzin, szacunków wydatków i blokowania funkcji są dostępne w programie Microsoft Dynamics 365 for Finance and Operations w wersji 8.0.
> - Funkcja integrowania wartości rzeczywistych jest dostępna w programie Microsoft Dynamics 365 for Finance and Operations w wersji 8.01 i nowszych.
> - Jeśli używasz programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition 7.3.0, po zainstalowaniu aktualizacji KB 4132657 i 4132660 możesz używać szablonów, aby integrować zadania projektu, kategorie transakcji wydatkowych, szacunki godzin, szacunki wydatków i wartości rzeczywiste oraz konfigurować blokowanie funkcji. Jeśli należy zresetować zasady podziału księgowań, zalecamy dodatkowo zainstalować aktualizację KB 4131710.

## <a name="data-flow-for-project-service-automation-and-finance-and-operations"></a>Przepływ danych między programami Project Service Automation i Finance and Operations

Rozwiązanie integracji rozwiązania Project Service Automation oraz Finance and Operations korzysta z funkcji integracji danych do synchronizowania danych między wystąpieniami rozwiązania Project Service Automation oraz Finance and Operations. Szablony integracji, które są dostępne z funkcji integracji danych, umożliwiają przepływ danych dotyczących kategorii transakcji wydatkowych w projektach pomiędzy rozwiązaniem Project Service Automation i rozwiązaniem Finance and Operations.

Jeśli zarządzanie kategoriami wydatków w projekcie odbywa się w programie Finance and Operations, przepływ integracji następuje najpierw z programu Finance and Operations do programu Project Service Automation. Identyfikatory integracji kategorii wydatków w projekcie są następnie aktualizowane poprzez synchronizację z programu Project Service Automation do programu Finance and Operations.

Jeśli zarządzanie kategoriami wydatków w projekcie odbywa się w programie Project Service Automation, przepływ integracji następuje najpierw z programu Project Service Automation do programu Finance and Operations. Kategorie projektu muszą być skonfigurowane w rozwiązaniu Finance and Operations przed synchronizacją z rozwiązania Project Service Automation. Następnie przeprowadź synchronizację z rozwiązania Finance and Operations ponownie do rozwiązania Project Service Automation, a następnie jeszcze raz z rozwiązania Project Service Automation do rozwiązania Finance and Operations. W ten sposób zapewniasz, że kategorie są połączone i nie powstają żadne duplikaty.

> [!NOTE]
> Na ogół kategorie wydatków projektu są zarządzane w aplikacji Finance and Operations. Jednak jeśli nie są one zarządzane w programie Finance and Operations lub jeśli kategorie wydatków zostały już utworzone w programie Project Service Automation, należy je najpierw zsynchronizować przy użyciu szablonu Kategorie transakcji wydatkowych w projekcie (PSA do Fin and Ops). Następnie należy wykonać synchronizację przy użyciu szablonu Kategorie transakcji wydatkowych w projekcie (Fin and Ops do PSA). Następnie należy wykonać jeszcze jedną synchronizację z programu Project Service Automation do programu Finance and Operations.
>
> Jeśli synchronizujesz najpierw z programu Project Service Automation, następujące wymagania muszą być spełnione w programie Finance and Operations przed uruchomieniem synchronizacji:
>
> - Udostępniona kategoria, która pasuje do kategorii projektu skonfigurowanej w programie Project Service Automation, musi istnieć oraz mieć włączone opcje **Projekt** i **Wydatek**.
> - Dla każdej firmy, z którą ma być integrowany program Finance and Operations, muszą istnieć następujące kategorie projektu:
>
>     - Element **Kategoria projektu** istnieje. 
>     - Opcja **Użyj w module wydatków** jest włączona.
>     - Opcja **Aktywne w arkuszu** jest włączona.
>     - W ustawieniu **Typ transakcji** zaznaczono opcję **Wydatek**.

Na poniższej ilustracji przedstawiono, w jaki sposób dane są synchronizowane pomiędzy rozwiązaniami Project Service Automation oraz Finance and Operations.

[![Przepływ danych w integracji programu Project Service Automation z programem Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)

## <a name="project-expense-category-synchronization-from-finance-and-operations-to-project-service-automation"></a>Synchronizowanie kategorii wydatków w projekcie z programu Finance and Operations do programu Project Service Automation

### <a name="template-and-task"></a>Szablon i zadanie

Aby uzyskać dostęp do szablonu, w centrum administracyjnym usługi Microsoft PowerApps wybierz opcję **Projekty** i w prawym górnym rogu wybierz opcję **Nowy projekt**, aby wybrać spośród szablonów publicznych.

Następujący szablon i podstawowe zadania służą do synchronizowania kategorii wydatków projektu z rozwiązania Finance and Operations do rozwiązania Project Service Automation:

- **Nazwa szablonu w narzędziu Integracja danych:** Kategorie transakcji wydatkowych w projekcie (Fin and Ops do PSA)
- **Nazwa zadania w projekcie:** Synchronizowanie kategorii do PSA

### <a name="entity-set"></a>Zestaw jednostek

| Finance and Operations            | Project Service Automation |
|-----------------------------------|----------------------------|
| Jednostka integracji kategorii | Kategorie transakcji     |

### <a name="entity-flow"></a>Przepływ jednostek

Zarządzanie kategoriami wydatków w projekcie odbywa się w aplikacji Finance and Operations i są one synchronizowane z aplikacją Project Service Automation jako kategorie transakcji.

### <a name="power-query"></a>Zapytanie zaawansowane

Jeżeli synchronizujesz z rozwiązania Project Service Automation, należy za pomocą dodatku Microsoft Power Query dla programu Excel ustawić typ fakturowania w kategorii transakcji. Szablon Kategorie transakcji wydatkowych w projekcie (Fin and Ops do PSA) zawiera domyślną kolumnę i mapowanie. Jeśli tworzysz własny szablon, musisz dodać tę kolumnę warunkową w narzędziu Power Query. Wykonaj następujące kroki.

1. Kliknij strzałkę, aby otworzyć mapowanie zadania kategorie wydatków w projekcie w szablonie Kategorie transakcji wydatkowych w projekcie (Fin and Ops do PSA).
2. Kliknij łącze **Zaawansowane zapytania i filtrowanie**, aby otworzyć aplikację Power Query.
2. Wybierz opcję **Dodaj kolumnę warunkową**.
3. Nadaj nazwę nowej kolumnie, taką jak **BillingType**.
4. Wprowadź następujący warunek: **if CATEGORYID not equal to null then 19235001, Otherwise null**.
5. W kolumnie kliknij przycisk **OK**.
6. Pamiętaj, aby zamapować tę nową kolumnę na stronie mapowania.

Poniższa ilustracja przedstawia przykład mapowania zadań szablonu w integracji danych. Mapowanie pokazuje informacje z pola, które zostanie zsynchronizowane z rozwiązania Finance and Operations do rozwiązania Project Service Automation.

[![Mapowanie szablonu](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)

## <a name="project-expense-category-synchronization-from-project-service-automation-to-finance-and-operations"></a>Synchronizowanie kategorii wydatków w projekcie z programu Project Service Automation do programu Finance and Operations

### <a name="template-and-task"></a>Szablon i zadanie

Następujący szablon i podstawowe zadania służą do synchronizowania kategorii wydatków projektu z rozwiązania Project Service Automation do rozwiązania Finance and Operations:

- **Nazwa szablonu w narzędziu Integracja danych:** Kategorie transakcji wydatkowych w projekcie (PSA do Fin and Ops)
- **Nazwa zadania w projekcie:** Synchronizowanie kategorii do Fin Ops

### <a name="entity-set"></a>Zestaw jednostek

| Project Service Automation | Finance and Operations            |
|----------------------------|-----------------------------------|
| Kategorie transakcji     | Jednostka integracji kategorii |

### <a name="entity-flow"></a>Przepływ jednostek

Zarządzanie kategoriami wydatków w projekcie odbywa się w aplikacji Finance and Operations i są one synchronizowane z aplikacją Project Service Automation jako kategorie transakcji. Ponowna synchronizacja do rozwiązania Finance and Operations aktualizuje kategorię projektu w rozwiązaniu Finance and Operations o identyfikator integracji z rozwiązania Project Service Automation.

### <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Poniższa ilustracja przedstawia przykład mapowania zadań szablonu w integracji danych.

> [!NOTE]
> Mapowanie pokazuje informacje z pola, które zostanie zsynchronizowane z rozwiązania Finance and Operations do rozwiązania Project Service Automation.

[![Mapowanie szablonu](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)
