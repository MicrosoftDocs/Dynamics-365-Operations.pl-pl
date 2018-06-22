---
title: "Synchronizowanie kategorii wydatków w projekcie z aplikacji Project Service Automation"
description: "Ten temat zawiera opis szablonów i podstawowych zadań, które są używane do synchronizowania kategorii wydatków projektu bezpośrednio między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Project Service Automation."
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
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: dcdb9b6ec296073d511c069cdceb1c61080b6d97
ms.contentlocale: pl-pl
ms.lasthandoff: 05/29/2018

---

# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a>Synchronizowanie kategorii wydatków w projekcie między programami Finance and Operations i Project Service Automation

Ten temat zawiera opis szablonów i podstawowych zadań, które są używane do synchronizowania kategorii wydatków projektu bezpośrednio między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Project Service Automation.

> [!NOTE]
> Mechanizmy integracji zadań projektu, kategorii transakcji wydatkowych, szacunków godzin, szacunków wydatków i blokowania funkcji są dostępne w programie Dynamics 365 for Finance and Operations w wersji 8.0.

## <a name="data-flow-for-project-service-automation-and-finance-and-operations"></a>Przepływ danych między programami Project Service Automation i Finance and Operations

Rozwiązanie integracji rozwiązania Project Service Automation oraz Finance and Operations korzysta z funkcji integracji danych do synchronizowania danych między wystąpieniami rozwiązania Project Service Automation oraz Finance and Operations. Szablony integracji, które są dostępne z funkcji integracji danych, umożliwiają przepływ danych dotyczących kategorii transakcji wydatkowych w projektach pomiędzy rozwiązaniem Project Service Automation i rozwiązaniem Finance and Operations.

Jeśli zarządzanie kategoriami wydatków w projekcie odbywa się w programie Finance and Operations, przepływ integracji następuje najpierw z programu Finance and Operations do programu Project Service Automation, po czym są aktualizowane identyfikatory integracji kategorii wydatków w projekcie poprzez synchronizację z programu Project Service Automation do programu Finance and Operations.

Jeśli zarządzanie kategoriami wydatków w projekcie odbywa się w programie Project Service Automation, przepływ integracji następuje najpierw z programu Project Service Automation do programu Finance and Operations. Kategorie projektu muszą być skonfigurowane w rozwiązaniu Finance and Operations przed synchronizacją z rozwiązania Project Service Automation. Następnie przeprowadź synchronizację z rozwiązania Finance and Operations ponownie do rozwiązania Project Service Automation, a następnie jeszcze raz z rozwiązania Project Service Automation do rozwiązania Finance and Operations. Dzięki temu kategorie są połączone i duplikaty nie są tworzone.

> [!NOTE]
> Na ogół kategorie wydatków projektu będą zarządzane w Finance and Operations. Jeśli w Twojej firmie tak nie jest albo masz już utworzone kategorie wydatków w aplikacji Project Service Automation, należy najpierw zsynchronizować przy użyciu szablonu Kategorie transakcji wydatkowych w projekcie (PSA do Fin and Ops), a następnie zsynchronizować przy użyciu szablonu Kategorie transakcji wydatkowych w projekcie (Fin and Ops do PSA). Należy następnie uruchomić proces synchronizacji z PSA do rozwiązania Fin and Ops jeszcze raz.

> Jeśli synchronizujesz najpierw z programu Project Service Automation, kategorie projektu muszą już być skonfigurowana w programie Finance and Operations, a wszystkie kategorie projektów, które mają być synchronizowane z kategoriami transakcji w programie Project Service Automation, muszą mieć ustawioną opcję **Aktywne w arkuszach**.

Na poniższej ilustracji przedstawiono, w jaki sposób dane są synchronizowane pomiędzy rozwiązaniami Project Service Automation oraz Finance and Operations.

[![Przepływ danych w integracji programu Project Service Automation z programem Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)


## <a name="templates-and-tasks"></a>Szablony i zadania

Aby uzyskać dostęp do dostępnych szablonów w Microsoft PowerApps Admin Center, wybierz **Projekty** i w prawym górnym rogu wybierz **Nowy projekt**, aby wybierać szablony publiczne.

Następujący szablon i zadania podrzędne służy do synchronizowania kategorii wydatków projektu z rozwiązania Finance and Operations do rozwiązania Project Service Automation:

-  **Nazwa szablonu w narzędziu Integracja danych:** Kategorie transakcji wydatkowych w projekcie (Fin and Ops do PSA)
-  **Nazwa zadania w projekcie:** Synchronizowanie kategorii do PSA

## <a name="entity-set"></a>Zestaw jednostek

| Finance and Operations               | Project Service Automation    |
|--------------------------------------|-------------------------------|
| Jednostka integracji kategorii    | Kategorie transakcji        |

## <a name="entity-flow"></a>Przepływ jednostek

Zarządzanie kategoriami wydatków w projekcie odbywa się w aplikacji Finance and Operations i są one synchronizowane z aplikacją Project Service Automation jako kategorie transakcji.

## <a name="power-query"></a>Zapytanie zaawansowane

Należy użyć programu Microsoft Power Query w celu ustawienia typu fakturowania w kategorii transakcji podczas synchronizacji z rozwiązaniem Project Service Automation. Szablon Kategorie transakcji wydatkowych w projekcie (Fin and Ops do PSA) ma domyślną kolumnę i dostarczone mapowania. Jeśli tworzysz własny szablon, musisz dodać tę kolumnę warunkową w narzędziu Power Query.
- Otwórz formularz Zaawansowane zapytania i filtrowanie z poziomu mapowania zadania kategorii wydatków w projekcie.
- Wybierz opcję **Dodaj kolumnę warunkową**.
- Nadaj nowej kolumnie nazwę, taką jak BillingType.
- Wprowadź następujący warunek: if **CATEGORYID not equal to null then 19235001, Otherwise null**.
- W kolumnie kliknij przycisk **OK**.
- Pamiętaj, aby zamapować tę nową kolumnę na stronie mapowania.

Poniższa ilustracja przedstawia przykład mapowania zadań szablonu w integracji danych. Mapowanie pokazuje informacje z pola, które zostanie zsynchronizowane z rozwiązania Finance and Operations do rozwiązania Project Service Automation.

[![Mapowanie szablonu](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)

Następujący szablon i zadanie podrzędne służy do synchronizowania kategorii wydatków projektu z rozwiązania Project Service Automation do rozwiązania Finance and Operations:

-**Nazwa szablonu w narzędziu Integracja danych:** Kategorie transakcji wydatkowych w projekcie (PSA do Fin and Ops) -**Nazwa zadania w projekcie:** Synchronizowanie kategorii do Fin Ops

## <a name="entity-set"></a>Zestaw jednostek

| Project Service Automation      | Finance and Operations             |
|---------------------------------|------------------------------------|
| Kategorie transakcji          | Jednostka integracji kategorii  | 

## <a name="entity-flow"></a>Przepływ jednostek

Zarządzanie kategoriami wydatków w projekcie odbywa się w aplikacji Finance and Operations i są one synchronizowane z aplikacją Project Service Automation jako kategorie transakcji. Ponowna synchronizacja do rozwiązania Finance and Operations aktualizuje identyfikator integracji z rozwiązania Project Service Automation w kategorii projektów rozwiązania Finance and Operations.

Poniższa ilustracja przedstawia przykład mapowania zadań szablonu w integracji danych.

> [!NOTE]
> Mapowanie pokazuje informacje z pola, które zostanie zsynchronizowane z rozwiązania Finance and Operations do rozwiązania Project Service Automation.

[![Mapowanie szablonu](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)

