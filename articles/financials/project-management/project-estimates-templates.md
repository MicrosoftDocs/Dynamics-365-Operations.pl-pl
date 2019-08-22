---
title: Synchronizowanie szacunków projektu bezpośrednio z programu Project Service Automation do programu Finance and Operations
description: Ten temat zawiera opis szablonów i podstawowych zadań, które są używane do synchronizowania szacunków czasu projektu i szacunków wydatków projektów bezpośrednio między programem Microsoft Dynamics 365 for Project Service Automation a programem Microsoft Dynamics 365 for Finance and Operations.
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
ms.openlocfilehash: 6bdf139ddd0faa7ba2c9c14b93286eff0ef757fe
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846010"
---
# <a name="synchronize-project-estimates-directly-from-project-service-automation-to-finance-and-operations"></a>Synchronizowanie szacunków projektu bezpośrednio z programu Project Service Automation do programu Finance and Operations

[!include[banner](../includes/banner.md)]

Ten temat zawiera opis szablonów i podstawowych zadań, które są używane do synchronizowania szacunków czasu projektu i szacunków wydatków projektów bezpośrednio między programem Microsoft Dynamics 365 for Project Service Automation a programem Dynamics 365 for Finance and Operations.

> [!NOTE]
> - Mechanizmy integracji zadań projektu, kategorii transakcji wydatkowych, szacunków godzin, szacunków wydatków i blokowania funkcji są dostępne w programie Microsoft Dynamics 365 for Finance and Operations w wersji 8.0.
> - Funkcja integrowania wartości rzeczywistych jest dostępna w programie Microsoft Dynamics 365 for Finance and Operations w wersji 8.01 i nowszych.
> - Jeśli używasz programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition 7.3.0, po zainstalowaniu aktualizacji KB 4132657 i 4132660 możesz używać szablonów, aby integrować zadania projektu, kategorie transakcji wydatkowych, szacunki godzin, szacunki wydatków i wartości rzeczywiste oraz konfigurować blokowanie funkcji. Jeśli należy zresetować zasady podziału księgowań, zalecamy dodatkowo zainstalować aktualizację KB 4131710.

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Przepływ danych z programu Project Service Automation do Finance and Operations

Rozwiązanie integracji rozwiązania Project Service Automation z rozwiązaniem Finance and Operations korzysta z funkcji integracji danych do synchronizowania danych między wystąpieniami rozwiązania Project Service Automation oraz rozwiązania Finance and Operations. Szablony integracji, które są dostępne z funkcji integracji danych, umożliwiają przepływ danych dotyczących szacunków godzinowych i szacowań wydatków dotyczących projektu z rozwiązania Project Service Automation do rozwiązania Finance and Operations.

Na poniższej ilustracji przedstawiono, w jaki sposób dane są synchronizowane pomiędzy rozwiązaniami Project Service Automation oraz Finance and Operations.

[![Przepływ danych w integracji programu Project Service Automation z programem Finance and Operations](./media/ProjectEstimatesFlow.png)](./media/ProjectEstimatesFlow.png)

## <a name="project-hour-estimates"></a>Szacunki godzinowe projektu

### <a name="template-and-tasks"></a>Szablon i zadania

Aby przejść do dostępnych szablonów, w centrum administracyjnym usługi Microsoft PowerApps wybierz opcję **Projekty** i w prawym górnym rogu wybierz opcję **Nowy projekt**, aby wybrać spośród szablonów publicznych.

Następujący szablon i zadania podrzędne służą do synchronizowania szacunków godzin projektu z rozwiązania Project Service Automation do rozwiązania Finance and Operations:

- **Nazwa szablonu w narzędziu Integracja danych:** Szacunki godzin w projekcie (PSA do Fin and Ops)
- **Nazwa zadania w projekcie:**

    - Relacje transakcji
    - Oszacowania wydatków

### <a name="entity-set"></a>Zestaw jednostek

| Project Service Automation | Finance and Operations                        |
|----------------------------|-----------------------------------------------|
| Zadania w projekcie              | Jednostka integracji szacunków godzinowych projektu |

### <a name="entity-flow"></a>Przepływ jednostek

Zarządzanie szacunkami godzin w projekcie odbywa się w programie Project Service Automation i są one synchronizowane z programem Finance and Operations jako prognozy godzin w projekcie.

### <a name="prerequisites"></a>Wymagania wstępne

Zanim będzie możliwa synchronizacja szacunków godzin w projektach, należy zsynchronizować projekty, zadania w projektach i kategorie transakcji wydatkowych w projektach.

### <a name="power-query"></a>Zapytanie zaawansowane

W szablonie szacunków godzinowych projektu należy za pomocą dodatku Microsoft Power Query dla programu Excel wykonać następujące zadania:

- Ustawienie domyślnego identyfikatora modelu prognozy, który będzie używany, gdy funkcja integracji utworzy nowe prognozy godzinowe.
- Odfiltrowanie wszystkich rekordów specyficznych dla zasobów w zadaniu, które spowodowałyby niepowodzenie integracji z prognozami godzin.
- Odfiltrować wszystkie puste wiersze kategorii transakcji. Niewykonanie tych zadań może spowodować błędy w prognozach godzin.

#### <a name="set-the-default-forecast-model-id"></a>Ustawianie domyślnego identyfikatora modelu prognozy

Aby zaktualizować domyślny identyfikator modelu prognozy do szablonu, kliknij strzałkę **Mapuj**, aby otworzyć mapowanie. Następnie kliknij łącze **Zaawansowane zapytania i filtrowanie**.

- Jeśli używasz domyślnego szablonu Szacunki godzin w projekcie (PSA do Fin and Ops), na liście **Zastosowane kroki** zaznacz element **Wstawiony warunek**. We wpisie **Funkcja** zastąp tekst **O\_forecast** nazwą identyfikatora modelu prognozy, który powinien być używany w integracji. Domyślny szablon zawiera identyfikator modelu prognozy z danych demonstracyjnych.
- Jeśli tworzysz nowy szablon, należy dodać tę kolumnę. W narzędziu Power Query wybierz opcję **Dodaj kolumnę warunkową**, a następnie nadaj nowej kolumnie nazwę, taką jak **ModelID**. Wprowadź warunek dla kolumny, gdzie jeśli parametr Zadanie projektu nie ma wartości null, to \<wprowadź identyfikatora modelu prognozy\>; w przeciwnym razie null.

#### <a name="filter-out-resource-specific-records"></a>Odfiltrowywanie rekordów specyficznych dla zasobów

Szablon Szacunki godzin w projekcie (PSA do Fin and Ops) zawiera filtr domyślny, który usuwa wszystkie rekordy określonych zasobów. Jeśli tworzysz własny szablon, musisz dodać ten filtr. Kliknij łącze **Zaawansowane zapytania i filtrowanie**, aby wyfiltrować według kolumny **msdyn\_islinetask** i wyświetlić tylko rekordy spełniające warunek **Fałsz**.

#### <a name="filter-out-empty-transaction-category-rows"></a>Odfiltrowywanie wszystkich pustych wierszy kategorii transakcji

Należy dodać filtr, aby usunąć wszystkie wiersze mające puste kategorie transakcji. To zadanie jest wymagane bez względu na to, czy używasz szablonu domyślnego, czy tworzysz własny. Ten filtr spowoduje usunięcie wszystkich wierszy podsumowania pochodzących z rozwiązania Project Service Automation, które mogą powodować nieprawidłowe prognozy godzinowe w programie Finance and Operations. Kliknij łącze **Zaawansowane zapytania i filtrowanie**, aby odfiltrować rekordy o wartości null w kolumnie **msdyn\_transactioncategory\_value**.

### <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Poniższa ilustracja przedstawia przykład mapowania zadań szablonu w integracji danych. Mapowanie pokazuje informacje z pola, które zostanie zsynchronizowane z rozwiązania Finance and Operations do rozwiązania Project Service Automation.

[![Mapowanie szablonu](./media/ProjectHourEstimatesMapping.jpg)](./media/ProjectHourEstimatesMapping.jpg)

## <a name="project-expense-estimates"></a>Szacunki wydatków w projekcie

### <a name="template-and-tasks"></a>Szablon i zadania

Następujący szablon i podstawowe zadania służą do synchronizowania szacunków wydatków projektu z rozwiązania Project Service Automation do rozwiązania Finance and Operations:

- **Nazwa szablonu w narzędziu Integracja danych:** Szacunki wydatków w projekcie (PSA do Fin and Ops)
- **Nazwa zadania w projekcie:**

    - Relacje transakcji 
    - Oszacowania wydatków

### <a name="entity-set"></a>Zestaw jednostek

| Project Service Automation | Finance and Operations                                   |
|----------------------------|----------------------------------------------------------|
| Połączenia transakcji    | Jednostka integracji relacji transakcji projektu |
| Wiersze oszacowania             | Jednostka integracji szacowań wydatków projektu         |

### <a name="entity-flow"></a>Przepływ jednostek

Zarządzanie szacunkami wydatków w projekcie odbywa się w aplikacji Project Service Automation i są one synchronizowane z aplikacją Finance and Operations jako prognozy wydatków w projekcie.

### <a name="prerequisites"></a>Wymagania wstępne

Zanim będzie możliwa synchronizacja szacunków wydatków w projektach, należy zsynchronizować projekty, zadania w projektach i kategorie transakcji wydatkowych w projektach.

### <a name="power-query"></a>Zapytanie zaawansowane

W szablonie szacunków wydatków projektu należy użyć programu Power Query w celu wykonania następujących zadań:

- Wyfiltrowanie, aby uwzględnić tylko rekordy wierszy szacowania wydatków.
- Ustawienie domyślnego identyfikatora modelu prognozy, który będzie używany, gdy funkcja integracji utworzy nowe prognozy godzinowe.
- Przekształć typy fakturowania.
- Przekształć typy transakcji.

#### <a name="filter-to-include-only-expense-estimate-lines"></a>Filtrowanie w celu uwzględnienia tylko wierszy szacowania wydatków

Szablon Szacunki wydatków w projekcie (PSA do Fin and Ops) ma domyślny filtr uwzględniający w integracji tylko wiersze wydatków. Jeśli tworzysz własny szablon, musisz dodać ten filtr. Wybierz zadanie **Relacje transakcji**, a następnie kliknij strzałkę **Mapuj**, aby otworzyć mapowanie. Kliknij łącze **Zaawansowane zapytania i filtrowanie**. Wyfiltruj kolumnę **msdyn\_transactiontype1**, tak aby zawierała tylko element **msdyn\_estimateline**.

#### <a name="set-the-default-forecast-model-id"></a>Ustawianie domyślnego identyfikatora modelu prognozy

Aby zaktualizować domyślny identyfikator modelu prognozy w szablonie, wybierz zadanie **Oszacowania wydatków**, a następnie kliknij strzałkę **Mapuj**, aby otworzyć mapowanie. Kliknij łącze **Zaawansowane zapytania i filtrowanie**.

- Jeśli używasz domyślnego szablonu Szacunki wydatków w projekcie (PSA do Fin and Ops), w programie Power Query w sekcji **Zastosowane kroki** zaznacz pierwszy element na liście **Wstawiony warunek**. We wpisie **Funkcja** zastąp tekst **O\_forecast** nazwą identyfikatora modelu prognozy, który powinien być używany w integracji. Domyślny szablon zawiera identyfikator modelu prognozy z danych demonstracyjnych.
- Jeśli tworzysz nowy szablon, należy dodać tę kolumnę. W narzędziu Power Query wybierz opcję **Dodaj kolumnę warunkową**, a następnie nadaj nowej kolumnie nazwę, taką jak **ModelID**. Wprowadź warunek dla kolumny, gdzie jeśli parametr Identyfikator wiersza szacowania nie ma wartości null, to \<wprowadź identyfikatora modelu prognozy\>; w przeciwnym razie null.

#### <a name="transform-the-billing-types"></a>Przekształć typy fakturowania

Szablon Szacunki wydatków w projekcie (PSA do Fin and Ops) zawiera warunkową kolumnę używaną do przekształcania typów faktur otrzymanych z rozwiązania Project Service Automation podczas integracji. Jeśli tworzysz własny szablon, musisz dodać tę kolumnę warunkową. Kliknij łącze **Zaawansowane zapytania i filtrowanie**, a następnie wybierz opcję **Dodaj kolumnę warunkową**. Nadaj nazwę nowej kolumnie, taką jak **BillingType**. Następnie wprowadź poniższy warunek:

If **msdyn\_billingtype** = 192350000, then **NonChargeable**  
else if **msdyn\_billingtype** = 192350001, then **Chargeable**  
else if **msdyn\_billingtype** = 192350002, then **Complimentary**  
else **NotAvailable**

#### <a name="transform-the-transaction-types"></a>Przekształć typy transakcji

Szablon Szacunki wydatków w projekcie (PSA do Fin and Ops) zawiera warunkową kolumnę używaną do przekształcania typów transakcji otrzymanych z rozwiązania Project Service Automation podczas integracji. Jeśli tworzysz własny szablon, musisz dodać tę kolumnę warunkową. Kliknij łącze **Zaawansowane zapytania i filtrowanie**, a następnie wybierz opcję **Dodaj kolumnę warunkową**. Nadaj nazwę nowej kolumnie, taką jak **TransactionType**. Następnie wprowadź poniższy warunek:

If **msdyn\_transactiontypecode** = 192350000, then **Koszt**  
else if **msdyn\_transactiontypecode** = 192350005, then **Sprzedaż**  
else **null**

### <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Poniższa ilustracja przedstawia przykłady mapowań zadań szablonu w integracji danych. Mapowanie pokazuje informacje z pola, które zostanie zsynchronizowane z rozwiązania Finance and Operations do rozwiązania Project Service Automation.

[![Mapowanie szablonu](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)

[![Mapowanie szablonu](./media/ExpenseEstimatesMapping.jpg)](./media/ExpenseEstimatesMapping.jpg)
