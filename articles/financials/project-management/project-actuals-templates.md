---
title: Synchronizowanie wartości rzeczywistych bezpośrednio z programu Project Service Automation do arkusza integracji projektu w celu zaksięgowania w programie Finance and Operations
description: W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania wartości rzeczywistych projektu bezpośrednio z Microsoft Dynamics 365 for Project Service Automation do Microsoft Dynamics 365 for Finance and Operations.
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
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: 0a965e8de596decf39a15977e6df8a6aa9dd35b0
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571107"
---
# <a name="synchronize-project-actuals-directly-from-project-service-automation-to-the-project-integration-journal-for-posting-in-finance-and-operations"></a>Synchronizowanie wartości rzeczywistych bezpośrednio z programu Project Service Automation do arkusza integracji projektu w celu zaksięgowania w programie Finance and Operations

[!include[banner](../includes/banner.md)]

W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania wartości rzeczywistych projektu bezpośrednio z Microsoft Dynamics 365 for Project Service Automation do Microsoft Dynamics 365 for Finance and Operations.

Szablon synchronizuje transakcje z rozwiązania Project Service Automation do tabeli tymczasowej w rozwiązaniu Finance and Operations. Po zakończeniu synchronizacji **koniecznie trzeba** wykonać import danych z tabeli tymczasowej do arkusza integracji.

> [!NOTE]
> - Funkcja integrowania wartości rzeczywistych projektu jest dostępna w programie Microsoft Dynamics 365 for Finance and Operations w wersji 8.0.1 i nowszych.
> - Jeśli używasz programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition 7.3.0, po zainstalowaniu aktualizacji KB 4132657 i 4132660 możesz używać szablonów, aby integrować zadania projektu, kategorie transakcji wydatkowych, szacunki godzin, szacunki wydatków i wartości rzeczywiste oraz konfigurować blokowanie funkcji. Jeśli należy zresetować zasady podziału księgowań, zalecamy dodatkowo zainstalować aktualizację KB 4131710.
> - Jeśli używasz programu Finance and Operations w wersji 7.3.0 i przenosisz transakcje opłat z programu Project Service Automation, należy zainstalować aktualizację KB 4345320, aby te opłaty były uwzględniane w fakturze projektu.
> - Jeśli wprowadzasz kwoty podatku w transakcjach dotyczących czasu lub wydatków w module Project Service Automation, należy zainstalować aktualizację Update 7 dla programu Project Service Automation. W przeciwnym razie wartości rzeczywiste podatków nie będą łączone z powiązanymi wartościami rzeczywistymi czasu lub wydatków i nie będą synchronizowane z aplikacją Finance and Operations. Aby uzyskać więcej informacji, skontaktuj się z pomocą techniczną.

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Przepływ danych z programu Project Service Automation do Finance and Operations

Rozwiązanie integracji rozwiązania Project Service Automation z rozwiązaniem Finance and Operations korzysta z funkcji integracji danych do synchronizowania danych między wystąpieniami rozwiązania Project Service Automation oraz rozwiązania Finance and Operations. Szablony integracji, które są dostępne z funkcji integracji danych, umożliwiają przepływ danych dotyczących wartości rzeczywistych projektu z rozwiązania Project Service Automation do rozwiązania Finance and Operations.

Na poniższej ilustracji przedstawiono, w jaki sposób dane są synchronizowane pomiędzy rozwiązaniami Project Service Automation oraz Finance and Operations.

[![Przepływ danych w integracji programu Project Service Automation z programem Finance and Operations](./media/ProjectActualsFlow.jpg)](./media/ProjectActualsFlow.jpg)

## <a name="project-actuals-from-project-service-automation"></a>Wartości rzeczywiste projektu z programu Project Service Automation

### <a name="template-and-tasks"></a>Szablon i zadania

Aby przejść do dostępnych szablonów, w centrum administracyjnym usługi Microsoft PowerApps wybierz opcję **Projekty** i w prawym górnym rogu wybierz opcję **Nowy projekt**, aby wybrać spośród szablonów publicznych.

Następujący szablon i zadania podrzędne służą do synchronizowania wartości rzeczywistych projektu z rozwiązania Project Service Automation do rozwiązania Finance and Operations:

- **Nazwa szablonu w narzędziu Integracja danych:** Wartości rzeczywiste projektu (PSA do Fin and Ops)
- **Nazwa zadania w projekcie:**

    - Wartości rzeczywiste
    - Połączenia transakcji

### <a name="entity-set"></a>Zestaw jednostek

| Project Service Automation | Finance and Operations                                   |
|----------------------------|----------------------------------------------------------|
| Wartości rzeczywiste                    | Jednostka integracji wartości rzeczywistych projektu                   |
| Połączenia transakcji    | Jednostka integracji relacji transakcji projektu |

### <a name="entity-flow"></a>Przepływ jednostek

Zarządzanie wartościami rzeczywistymi projektu odbywa się w module Project Service Automation i są one synchronizowane z arkuszem integracji projektu w programie Finance and Operations. Księgowanie zostanie zastosowane na podstawie domyślnych wymiarów finansowych i ustawień księgowania.

### <a name="prerequisites"></a>Wymagania wstępne

Zanim będzie możliwa synchronizacja wartości rzeczywistych, należy skonfigurować parametry integracji z programem Project Service Automation oraz zsynchronizować projekty, zadania w projektach i kategorie transakcji wydatkowych w projektach.

### <a name="power-query"></a>Zapytanie zaawansowane

W szablonie wartości rzeczywistych projektu należy za pomocą dodatku Microsoft Power Query dla programu Excel wykonać następujące zadania:

- Przekształcenie typu transakcji w aplikacji Project Service Automation na prawidłowy typ transakcji w aplikacji Finance and Operations. Przekształcenie jest już zdefiniowane w szablonie Wartości rzeczywiste projektu (PSA do Fin and Ops).
- Przekształcenie typu fakturowania w aplikacji Project Service Automation na prawidłowy typ fakturowania w aplikacji Finance and Operations. Przekształcenie jest już zdefiniowane w szablonie Wartości rzeczywiste projektu (PSA do Fin and Ops). Typ fakturowania jest następnie mapowany na właściwość wiersza na podstawie konfiguracji wprowadzonej na stronie **Parametry integracji aplikacji Project Service Automation**.
- Wyfiltrowanie konkretnych jednostki organizacyjnych zasobów, które muszą być synchronizowane z tym szablonem.
- Jeśli wartości rzeczywiste czasu międzyfirmowego lub wydatków międzyfirmowych będą synchronizowane z programem Finance and Operations, należy przekształcić jednostkę organizacyjną umowy na prawidłową firmę w programie Finance and Operations. W szablonie Wartości rzeczywiste projektu (PSA do Fin and Ops) jest zdefiniowana kolumna warunkowa oparta na danych demonstracyjnych. Należy zaktualizować ostatnią wstawioną kolumnę warunkową o właściwe firmy. W przeciwnym razie może zostać zgłoszony błąd integracji lub zaimportowane niepoprawne rzeczywiste transakcje do programu Finance and Operations.
- Jeśli wartości rzeczywiste czasu międzyfirmowego lub wydatków międzyfirmowych nie będą synchronizowane z programem Finance and Operations, należy usunąć ostatnio wstawioną kolumnę warunkową z szablonu. W przeciwnym razie może zostać zgłoszony błąd integracji lub zaimportowane niepoprawne rzeczywiste transakcje do programu Finance and Operations.

#### <a name="contract-organizational-unit"></a>Jednostka organizacyjna umowy
Aby zaktualizować wstawioną kolumnę warunkową w szablonie, kliknij strzałkę **Mapuj**, aby otworzyć mapowanie. Kliknij łącze **Zaawansowane zapytania i filtrowanie**, aby otworzyć aplikację Power Query.

- Jeśli używasz domyślnego szablonu Wartości rzeczywiste projektu (PSA do Fin and Ops), w aplikacji Power Query w sekcji **Zastosowane kroki** zaznacz ostatni element na liście **Wstawiony warunek**. We wpisie **Funkcja** zastąp tekst **USSI** nazwą firmy, która powinna być używana w integracji. W razie potrzeby dodaj więcej warunków do elementu **Funkcja** i zaktualizuj warunek **else** z firmy **USMF** na inną firmę.
- W przypadku tworzenia nowego szablonu należy dodać tę kolumnę w celu obsługi międzyfirmowego czasu i wydatków. Wybierz opcję **Dodaj kolumnę warunkową** i nazwij kolumnę, np. **LegalEntity**. Wprowadź warunek dla kolumny, gdzie jeśli parametr **msdyn\_contractorganizationalunitid.msdyn\_name** ma wartość \<jednostka organizacyjna\>, to \<wprowadź nazwę firmy\>; w przeciwnym razie null.

### <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Poniższa ilustracja przedstawia przykład mapowania zadań szablonu w integracji danych. Mapowanie pokazuje informacje z pola, które zostanie zsynchronizowane z rozwiązania Finance and Operations do rozwiązania Project Service Automation.

[![Mapowanie szablonu](./media/ActualsMapping.jpg)](./media/ActualsMapping.jpg)

[![Mapowanie szablonu](./media/TransactionConnections.jpg)](./media/TransactionConnections.jpg)

## <a name="import-from-staging-table-after-integration-from-project-service-automation"></a>Importowanie z tabeli tymczasowej po integracji z programu Project Service Automation

Import z tymczasowej tabeli procesu okresowego należy uruchomić po synchronizacji wartości rzeczywistych z rozwiązania Project Service Automation do Finance and Operations. Ten proces importuje się transakcje projektu z tymczasowej tabeli do arkusza integracji rozwiązania Project Service Automation, gdzie stosuje się księgowanie i można zaksięgować zaimportowane transakcje. Zalecamy uruchamianie tego procesu w trybie wsadowym. Opcjonalnie można ustawić jego uruchamianie jako cykliczne zadanie wsadowe.

## <a name="update-actuals-from-finance-and-operations"></a>Aktualizowanie wartości rzeczywistych z programu Finance and Operations

### <a name="template-and-tasks"></a>Szablon i zadania

Następujący szablon i zadania podrzędne służą do synchronizowania numeru załącznika i podatków dla zaksięgowanych transakcji projektu z rozwiązania Finance and Operations do rozwiązania Project Service Automation:

- **Nazwa szablonu w narzędziu Integracja danych:** Aktualizacja wartości rzeczywistych projektu (Fin Ops do PSA)
- **Nazwa zadania w projekcie:**

    - Wartości rzeczywiste 
    - Połączenia transakcji

### <a name="entity-set"></a>Zestaw jednostek

| Finance and Operations                                   | Project Service Automation |
|----------------------------------------------------------|----------------------------|
| Jednostka integracji wartości rzeczywistych projektu                   | Wartości rzeczywiste                    |
| Jednostka integracji relacji transakcji projektu | Połączenia transakcji    |

### <a name="entity-flow"></a>Przepływ jednostek

Zarządzanie wartościami rzeczywistymi projektu odbywa się w module Project Service Automation i są one synchronizowane z arkuszem integracji projektu w programie Finance and Operations. Po zaksięgowaniu wartości rzeczywistych w programie Finance and Operations są one aktualizowane w module Project Service Automation o numer załącznika z programu Finance and Operations. Jeśli podatki zostały dodane w programie Finance and Operations, nowe wartości rzeczywiste podatków zostaną utworzone w aplikacji Project Service Automation.

### <a name="power-query"></a>Zapytanie zaawansowane

W szablonie aktualizacji wartości rzeczywistych projektu należy za pomocą narzędzia Power Query wykonać następujące zadania:

- Przekształcenie typu transakcji w aplikacji Finance and Operations na prawidłowy typ transakcji w aplikacji Project Service Automation. Przekształcenie jest już zdefiniowane w szablonie Aktualizacja wartości rzeczywistych projektu (Fin Ops do PSA).
- Przekształcenie typu fakturowania w aplikacji Finance and Operations na prawidłowy typ fakturowania w aplikacji Project Service Automation. Przekształcenie jest już zdefiniowane w szablonie Aktualizacja wartości rzeczywistych projektu (Fin Ops do PSA).

### <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Poniższa ilustracja przedstawia przykłady mapowań zadań szablonu w integracji danych. Mapowanie pokazuje informacje z pola, które zostanie zsynchronizowane z rozwiązania Finance and Operations do rozwiązania Project Service Automation.

[![Mapowanie szablonu](./media/ActualsUpdateMapping.jpg)](./media/ActualsUpdateMapping.jpg)

[![Mapowanie szablonu](./media/TransactionConnectionsUpdate.jpg)](./media/TransactionConnectionsUpdate.jpg)
