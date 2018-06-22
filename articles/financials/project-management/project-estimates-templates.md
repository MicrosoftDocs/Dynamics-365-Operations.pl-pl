---
title: "Synchronizowanie szacunków projektu z programu Project Service Automation bezpośrednio do prognoz projektu w programie Finance and Operations"
description: "Ten temat zawiera opis szablonów i podstawowych zadań, które są używane do synchronizowania szacunków czasu projektu i szacunków wydatków projektów bezpośrednio między programem Microsoft Dynamics 365 for Project Service Automation a programem Microsoft Dynamics 365 for Finance and Operations."
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
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 90501f40da0fdc66ad087b3bd746c908cc25711b
ms.contentlocale: pl-pl
ms.lasthandoff: 05/29/2018

---
# <a name="synchronize-project-estimates-from-project-service-automation-directly-to-project-forecasts-in-finance-and-operations"></a>Synchronizowanie szacunków projektu z programu Project Service Automation bezpośrednio do prognoz projektu w programie Finance and Operations

Ten temat zawiera opis szablonów i podstawowych zadań, które są używane do synchronizowania szacunków czasu projektu i szacunków wydatków projektów bezpośrednio między programem Microsoft Dynamics 365 for Project Service Automation a programem Microsoft Dynamics 365 for Finance and Operations.

> [!NOTE]
> Mechanizmy integracji zadań projektu, kategorii transakcji wydatkowych, szacunków godzin, szacunków wydatków i blokowania funkcji są dostępne w programie Dynamics 365 for Finance and Operations w wersji 8.0.


## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Przepływ danych z programu Project Service Automation do Finance and Operations

Rozwiązanie integracji rozwiązania Project Service Automation z rozwiązaniem Finance and Operations korzysta z funkcji integracji danych do synchronizowania danych między wystąpieniami rozwiązania Project Service Automation oraz rozwiązania Finance and Operations. Szablony integracji, które są dostępne z funkcji integracji danych, umożliwiają przepływ danych dotyczących szacunków godzinowych i szacowań wydatków dotyczących projektu z rozwiązania Project Service Automation do rozwiązania Finance and Operations.

Na poniższej ilustracji przedstawiono, w jaki sposób dane są synchronizowane pomiędzy rozwiązaniami Project Service Automation oraz Finance and Operations.

[![Przepływ danych w integracji programu Project Service Automation z programem Finance and Operations](./media/ProjectEstimatesFlow.png)](./media/ProjectEstimatesFlow.png)


## <a name="templates-and-tasks"></a>Szablony i zadania

Aby uzyskać dostęp do dostępnych szablonów w Microsoft PowerApps Admin Center, wybierz **Projekty** i w prawym górnym rogu wybierz **Nowy projekt**, aby wybierać szablony publiczne.

Następujący szablon i zadania podrzędne służą do synchronizowania szacunków godzin projektu z rozwiązania Project Service Automation do rozwiązania Finance and Operations:

-  **Nazwa szablonu w narzędziu Integracja danych:** Szacunki godzin w projekcie (PSA do Fin and Ops)

-  **Nazwa zadania w projekcie:** 
    - Relacje transakcji 
    - Oszacowania wydatków

## <a name="entity-set"></a>Zestaw jednostek

| Project Service Automation      | Finance and Operations                          |
|---------------------------------|-------------------------------------------------|
| Zadania w projekcie                   | Jednostka integracji szacunków godzinowych projektu   |

## <a name="entity-flow"></a>Przepływ jednostek

Zarządzanie szacunkami godzin w projekcie odbywa się w programie Project Service Automation i są one synchronizowane z programem Finance and Operations jako prognozy godzin w projekcie.

## <a name="preconditions"></a>Warunki wstępne

Zanim będzie możliwa synchronizacja szacunków godzin w projektach, należy zsynchronizować projekty, zadania w projektach i kategorie transakcji wydatkowych w projektach.

## <a name="power-query"></a>Zapytanie zaawansowane

Należy użyć programu Microsoft Power Query w szablonie szacunków godzinowych projektu w celu:
- W polu **Identyfikator modelu prognozy** ustaw identyfikator, który będzie używany, gdy funkcja integracji utworzy nowe prognozy godzinowe.
- Odfiltrować wszystkie rekordy specyficzne dla zasobów w zadaniu, które spowodowałyby niepowodzenie integracji z prognozami godzin.
- Odfiltrować wszystkie puste wiersze kategorii transakcji. W przeciwnym razie mogą powstać niepoprawne prognozy godzin.

### <a name="forecast-model-id"></a>Identyfikator modelu prognozy
Aby zaktualizować domyślny identyfikator modelu prognozy do szablonu, kliknij strzałkę **Mapuj**, aby otworzyć mapowanie. Wybierz opcję otwarcia okna Zaawansowane zapytania i filtrowanie.
- Jeśli używasz domyślnego szablonu Microsoft Project dla szacunków godzin (PSA do Fin and Ops), w sekcji **Zastosowane kroki** zaznacz element na liście **Wstawiony warunek**. We wpisie **Funkcja** zastąp tekst **O_forecast** nazwą **identyfikatora modelu prognozy**, który powinien być używany w integracji. Domyślny szablon zawiera identyfikator modelu prognozy z danych demonstracyjnych.
- Jeśli tworzysz nowy szablon, należy dodać tę kolumnę. Wybierz opcję **Dodaj kolumnę warunkową** i nazwij kolumnę, np. ModelID. Wprowadź warunek dla kolumny, gdzie jeśli parametr Zadanie projektu nie ma wartości null, to <enter the forecast model ID>; w przeciwnym razie null.

### <a name="filter-out-resource-specific-records"></a>Odfiltrowywanie rekordów specyficznych dla zasobów
Szablon Szacunki godzin w projekcie (PSA do Fin and Ops) zawiera filtr domyślny, który usuwa wszystkie rekordy określonych zasobów. Jeśli tworzysz własny szablon, musisz dodać ten filtr. W formularzu Zaawansowane zapytania i filtrowanie wybierz filtrowanie kolumny **msdyn_islinetask** w taki sposób, aby były wyświetlane tylko rekordy spełniające warunek **Fałsz**.

### <a name="filter-out-empty-transaction-category-rows"></a>Odfiltrowywanie wszystkich pustych wierszy kategorii transakcji
Należy dodać filtr, aby usunąć wszystkie wiersze z pustych kategorii transakcji. Jest to potrzebne bez względu na to, czy używa się szablonu domyślnego, czy tworzy własny. Ten filtr spowoduje usunięcie wszystkich wierszy podsumowania pochodzących z rozwiązania Project Service Automation, powodujących nieprawidłowe prognozy godzinowe w programie Finance and Operations. W formularzu Zaawansowane zapytania i filtrowanie wybierz odfiltrowywanie rekordów o wartości null w kolumnie **msdyn_transactioncategory_value**.

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Poniższa ilustracja przedstawia przykład mapowania zadań szablonu w integracji danych. Mapowanie pokazuje informacje z pola, które zostanie zsynchronizowane z rozwiązania Finance and Operations do rozwiązania Project Service Automation.

[![Mapowanie szablonu](./media/ProjectHourEstimatesMapping.jpg)](./media/ProjectHourEstimatesMapping.jpg)

Następujący szablon i zadanie podrzędne służy do synchronizowania szacunków wydatków projektu z rozwiązania Project Service Automation do rozwiązania Finance and Operations:

-  **Nazwa szablonu w narzędziu Integracja danych:** Szacunki wydatków w projekcie (PSA do Fin and Ops)
-  **Nazwa zadania w projekcie:** 
     - Relacje transakcji 
     - Oszacowania wydatków

## <a name="entity-set"></a>Zestaw jednostek

| Project Service Automation      | Finance and Operations                                     |
|---------------------------------|------------------------------------------------------------|
| Połączenia transakcji         | Jednostka integracji relacji transakcji projektu.   |
| Wiersze oszacowania                  | Jednostka integracji szacowań wydatków projektu.           |

## <a name="entity-flow"></a>Przepływ jednostek

Zarządzanie szacunkami wydatków w projekcie odbywa się w aplikacji Project Service Automation i są one synchronizowane z aplikacją Finance and Operations jako prognozy wydatków w projekcie.

## <a name="prerequisites"></a>Wymagania wstępne

Zanim będzie możliwa synchronizacja szacunków wydatków w projektach, należy zsynchronizować projekty, zadania w projektach i kategorie transakcji wydatkowych w projektach.

## <a name="power-query"></a>Zapytanie zaawansowane

Należy użyć programu Microsoft Power Query w szablonie szacowań wydatków projektu w celu:
- Wyfiltrować, aby uwzględnić tylko rekordy wierszy szacowania wydatków.
- W polu **Identyfikator modelu prognozy** ustaw identyfikator, który będzie używany, gdy funkcja integracji utworzy nowe prognozy godzinowe.
- Przekształć typy fakturowania.
- Przekształć typy transakcji.

### <a name="filter-to-include-only-expense-estimate-lines"></a>Filtrowanie w celu uwzględnienia tylko wierszy szacowania wydatków
Szablon Szacunki wydatków w projekcie (PSA do Fin and Ops) ma domyślny filtr uwzględniający w integracji tylko wiersze wydatków. Jeśli tworzysz własny szablon, musisz dodać ten filtr. Wybierz zadanie Relacje transakcji i kliknij strzałkę **Mapuj**. Wybierz opcję **Zaawansowane zapytania i filtrowanie**. Wyfiltruj kolumnę **msdyn_transactiontype1**, aby zawierała tylko element **msdyn_estimateline**.

### <a name="forecast-model-id"></a>Identyfikator modelu prognozy
Aby zaktualizować domyślny identyfikator modelu prognozy do szablonu dla zadania szacunku wydatków, kliknij strzałkę **Mapuj**, aby otworzyć mapowanie. Wybierz opcję otwarcia okna Zaawansowane zapytania i filtrowanie.
- Jeśli używasz domyślnego szablonu Microsoft Project dla szacunków wydatków (PSA do Fin and Ops), w sekcji **Zastosowane kroki** zaznacz pierwszy element na liście **Wstawiony warunek**. We wpisie **Funkcja** zastąp tekst **O_forecast** nazwą **identyfikatora modelu prognozy**, który powinien być używany w integracji. Domyślny szablon zawiera identyfikator modelu prognozy z danych demonstracyjnych.
- Jeśli tworzysz nowy szablon, należy dodać tę kolumnę. Wybierz opcję **Dodaj kolumnę warunkową** i nazwij kolumnę, np. ModelID. Wprowadź warunek dla kolumny, gdzie jeśli parametr Identyfikator wiersza szacowania nie ma wartości null, to < wprowadź identyfikatora modelu prognozy >; w przeciwnym razie null.

### <a name="transform-the-billing-types"></a>Przekształć typy fakturowania
Szablon Szacunki wydatków w projekcie (PSA do Fin and Ops) ma warunkową kolumnę dodawaną do przekształcania typów faktur otrzymanych z rozwiązania Project Service Automation podczas integracji.
- Jeśli tworzysz własny szablon, musisz dodać tę kolumnę warunkową. W formularzu Zaawansowane zapytania i filtrowanie wybierz opcję **Dodaj kolumnę warunkową**. Nadaj kolumnie nazwę, taką jak „BillingType”. Warunek do wprowadzania wygląda następująco:

    If **msdyn_billingtype** = 192350000 then **NonChargeable** else if **msdyn_billingtype** = 192350001, then **Chargeable** else if **msdyn_billingtype** = 192350002, then **Complimentary** else **NotAvailable**

### <a name="transform-the-transaction-types"></a>Przekształć typy transakcji
Szablon Szacunki wydatków w projekcie (PSA do Fin and Ops) ma warunkową kolumnę dodawaną do przekształcania typów transakcji otrzymanych z rozwiązania Project Service Automation podczas integracji.
- Jeśli tworzysz własny szablon, musisz dodać tę kolumnę warunkową. W formularzu Zaawansowane zapytania i filtrowanie wybierz opcję **Dodaj kolumnę warunkową**. Nadaj kolumnie nazwę, taką jak „TransactionType”. Warunek do wprowadzania wygląda następująco: If **msdyn_transactiontypecode** = 192350000, then **Koszt** else if **msdyn_transactiontypecode** = 192350005, then **sprzedaż** else **null**

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Poniższa ilustracja przedstawia przykłady mapowań zadań szablonu w integracji danych. Mapowanie pokazuje informacje z pola, które zostanie zsynchronizowane z rozwiązania Finance and Operations do rozwiązania Project Service Automation.

[![Mapowanie szablonu](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)

[![Mapowanie szablonu](./media/ExpenseEstimatesMapping.jpg)](./media/ExpenseEstimatesMapping.jpg)




