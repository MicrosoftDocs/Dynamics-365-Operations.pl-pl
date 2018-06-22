---
title: "Synchronizowanie wartości rzeczywistych z programu Project Service Automation do arkusza integracji projektu w celu zaksięgowania w programie Finance and Operations"
description: "Ten temat zawiera opis szablonów i podstawowych zadań, które są używane do synchronizowania danych rzeczywistych projektu bezpośrednio między programem Microsoft Dynamics 365 for Project Service Automation a programem Microsoft Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 05/21/2018
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
ms.openlocfilehash: 85ff049852e0b00623f47a12fb66e2c9bb9c4151
ms.contentlocale: pl-pl
ms.lasthandoff: 05/29/2018

---
# <a name="synchronize-project-actuals-from-project-service-automation-directly-to-the-project-integration-journal-for-posting-in-finance-and-operations"></a>Synchronizowanie wartości rzeczywistych z programu Project Service Automation do arkusza integracji projektu w celu zaksięgowania w programie Finance and Operations

Ten temat zawiera opis szablonów i podstawowych zadań, które są używane do synchronizowania danych rzeczywistych projektu bezpośrednio między programem Microsoft Dynamics 365 for Project Service Automation a programem Microsoft Dynamics 365 for Finance and Operations.

Szablon synchronizuje transakcje z rozwiązania Project Service Automation do tabeli tymczasowej w rozwiązaniu Finance and Operations. Po zakończeniu synchronizacji trzeba wykonać import z tabeli tymczasowej do arkusza integracji.

> [!NOTE]
> Funkcja integrowania wartości rzeczywistych projektu jest dostępna w programie Dynamics 365 for Finance and Operations w wersji 8.01.

> [!NOTE]
> Jeśli wprowadzasz kwoty podatku w transakcjach dotyczących czasu lub wydatków w module Project Service Automation, należy zainstalować aktualizację Update 7 dla programu Project Service Automation. Jeśli nie zainstalowano tej aktualizacji, wartości rzeczywiste podatków nie będą łączone z powiązanymi wartościami rzeczywistymi czasu lub wydatków i nie będą synchronizowane z aplikacją Finance and Operations. Aby uzyskać więcej informacji, skontaktuj się z pomocą techniczną.


## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Przepływ danych z programu Project Service Automation do Finance and Operations

Rozwiązanie integracji rozwiązania Project Service Automation z rozwiązaniem Finance and Operations korzysta z funkcji integracji danych do synchronizowania danych między wystąpieniami rozwiązania Project Service Automation oraz rozwiązania Finance and Operations. Szablony integracji, które są dostępne z funkcji integracji danych, umożliwiają przepływ danych dotyczących wartości rzeczywistych projektu z rozwiązania Project Service Automation do rozwiązania Finance and Operations.

Na poniższej ilustracji przedstawiono, w jaki sposób dane są synchronizowane pomiędzy rozwiązaniami Project Service Automation oraz Finance and Operations.

[![Przepływ danych w integracji programu Project Service Automation z programem Finance and Operations](./media/ProjectActualsFlow.jpg)](./media/ProjectActualsFlow.jpg)


## <a name="templates-and-tasks"></a>Szablony i zadania

Aby uzyskać dostęp do dostępnych szablonów w Microsoft PowerApps Admin Center, wybierz **Projekty** i w prawym górnym rogu wybierz **Nowy projekt**, aby wybierać szablony publiczne.

Następujący szablon i zadania podrzędne służą do synchronizowania wartości rzeczywistych projektu z rozwiązania Project Service Automation do rozwiązania Finance and Operations:

-  **Nazwa szablonu w narzędziu Integracja danych:** Wartości rzeczywiste projektu (PSA do Fin and Ops)

-  **Nazwa zadania w projekcie:** 
    - Wartości rzeczywiste 
    - Połączenia transakcji

## <a name="entity-set"></a>Zestaw jednostek

| Project Service Automation      | Finance and Operations                                      |
|---------------------------------|-------------------------------------------------------------|
| Wartości rzeczywiste                         | Jednostka integracji wartości rzeczywistych projektu                      |
| Połączenia transakcji         | Jednostka integracji relacji transakcji projektu    |

## <a name="entity-flow"></a>Przepływ jednostek

Zarządzanie wartościami rzeczywistymi projektu odbywa się w module Project Service Automation i są one synchronizowane z programem Finance and Operations w arkuszu integracji projektu. Księgowanie zostanie zastosowane na podstawie domyślnych wymiarów finansowych i ustawień księgowania.

## <a name="preconditions"></a>Warunki wstępne

Zanim będzie możliwa synchronizacja wartości rzeczywistych, należy skonfigurować parametry integracji z programem Project Service Automation oraz zsynchronizować projekty, zadania w projektach i kategorie transakcji wydatkowych w projektach.

## <a name="power-query"></a>Zapytanie zaawansowane

Należy użyć programu Microsoft Power Query w szablonie wartości rzeczywistych projektu w celu:
- Przekształć **typ transakcji** aplikacji Project Service Automation na prawidłowy **typ transakcji** w aplikacji Finance and Operations. Szablon Wartości rzeczywiste projektu (PSA do Fin and Ops) ma już to przekształcenie zdefiniowane.
- Przekształć **typ fakturowania** w aplikacji Project Service Automation na prawidłowy **typ fakturowania** w aplikacji Finance and Operations. Szablon Wartości rzeczywiste projektu (PSA do Fin and Ops) ma już to przekształcenie zdefiniowane. Typ fakturowania jest następnie mapowany na **właściwość wiersza** na podstawie konfiguracji w formularzu parametrów integracji Dynamics 365 for Project Service Automation.
- Wyfiltruj konkretne **jednostki organizacyjne zasobów**, które mają być synchronizowane z tym szablonem.
- Jeśli **wartości rzeczywiste czasu międzyfirmowego lub wydatków międzyfirmowych** będą synchronizowane z programem Finance and Operations, należy przekształcić **jednostkę organizacyjną umowy** na prawidłową **firmę** w programie Finance and Operations. Szablon Wartości rzeczywiste projektu (PSA do Fin and Ops) zawiera kolumnę warunkową opartą na danych demonstracyjnych. Należy zaktualizować ostatnią wstawioną kolumnę warunków do właściwych firm. W przeciwnym razie może zostać zgłoszony błąd integracji lub zaimportowane niepoprawne rzeczywiste transakcje do programu Finance and Operations.
- Jeśli **wartości rzeczywiste czasu międzyfirmowego lub wydatków międzyfirmowych** nie będą synchronizowane z programem Finance and Operations, należy usunąć ostatnio wstawioną kolumnę warunku z szablonu. W przeciwnym razie może zostać zgłoszony błąd integracji lub zaimportowane niepoprawne rzeczywiste transakcje do programu Finance and Operations.

### <a name="contract-organizational-unit"></a>Jednostka organizacyjna umowy
Aby zaktualizować wstawioną kolumnę warunku do szablonu, kliknij strzałkę **Mapuj**, aby otworzyć mapowanie. Wybierz opcję otwarcia okna Zaawansowane zapytania i filtrowanie.
- Jeśli używasz domyślnego szablonu Microsoft Project dla wartości rzeczywistych (PSA do Fin and Ops), w sekcji **Zastosowane kroki** zaznacz ostatni element na liście **Wstawiony warunek**. We wpisie **Funkcja** zastąp tekst **USSI** nazwą **firmy**, która powinna być używana w integracji. W razie potrzeby dodaj więcej warunków do elementu **Funkcja** i zaktualizuj warunek **else** z firmy **USMF** na inną firmę w polu **Firma**.
- W przypadku tworzenia nowego szablonu należy dodać tę kolumnę w celu obsługi międzyfirmowego czasu i wydatków. Wybierz opcję **Dodaj kolumnę warunkową** i nazwij kolumnę, np. LegalEntity. Wprowadź warunek dla kolumny, gdzie jeśli parametr msdyn_contractorganizationalunitid.msdyn_name ma wartość <organizational unit>, to <enter the Legal entity>; w przeciwnym razie null.

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Poniższa ilustracja przedstawia przykład mapowania zadań szablonu w integracji danych. Mapowanie pokazuje informacje z pola, które zostanie zsynchronizowane z rozwiązania Finance and Operations do rozwiązania Project Service Automation.

[![Mapowanie szablonu](./media/ActualsMapping.jpg)](./media/ActualsMapping.jpg)

[![Mapowanie szablonu](./media/TransactionConnections.jpg)](./media/TransactionConnections.jpg)

## <a name="import-from-staging-table"></a>Importuj z tabeli przemieszczania

Import z tymczasowej tabeli procesu okresowego należy uruchomić po synchronizacji wartości rzeczywistych z rozwiązania Project Service Automation do Finance and Operations. Ten proces importuje się transakcje projektu z tymczasowej tabeli do arkusza integracji rozwiązania Project Service Automation, gdzie stosuje się księgowanie i można zaksięgować zaimportowane transakcje. Zalecamy uruchamianie tego procesu w trybie wsadowym. Opcjonalnie można ustawić jego uruchamianie jako cykliczne zadanie wsadowe.

## <a name="update-actuals"></a>Aktualizowanie wartości rzeczywistych

Następujący szablon i zadania podrzędne służą do synchronizowania numeru załącznika i podatków dla zaksięgowanych transakcji projektu z rozwiązania Finance and Operations do rozwiązania Project Service Automation:

-  **Nazwa szablonu w narzędziu Integracja danych:** Aktualizacja wartości rzeczywistych projektu (Fin Ops do PSA)
-  **Nazwa zadania w projekcie:** 
     - Wartości rzeczywiste 
     - Połączenia transakcji

## <a name="entity-set"></a>Zestaw jednostek

| Finance and Operations                                         | Project Service Automation        |
|----------------------------------------------------------------|-----------------------------------|
| Jednostka integracji wartości rzeczywistych projektu                         | Wartości rzeczywiste                           |
| Jednostka integracji relacji transakcji projektu       | Połączenia transakcji           |

## <a name="entity-flow"></a>Przepływ jednostek

Zarządzanie wartościami rzeczywistymi projektu odbywa się w module Project Service Automation i są one synchronizowane z programem Finance and Operations w arkuszu integracji projektu. Po zaksięgowaniu w programie Finance and Operations wartości rzeczywiste są aktualizowane w module Project Service Automation o numer załącznika z programu Finance and Operations. Jeśli podatki zostały dodane w programie Finance and Operations, nowe wartości rzeczywiste podatków zostaną utworzone w aplikacji Project Service Automation.

## <a name="power-query"></a>Zapytanie zaawansowane

Należy użyć programu Microsoft Power Query w szablonie aktualizacji wartości rzeczywistych projektu w celu:
- Przekształć **typ transakcji** Finance and Operations na prawidłowy **typ transakcji** w aplikacji Project Service Automation. Szablon Aktualizacja wartości rzeczywistych projektu (Fin Ops do PSA) ma już to przekształcenie zdefiniowane.
- Przekształć **typ fakturowania** Finance and Operations na prawidłowy **typ fakturowania** w aplikacji Project Service Automation. Szablon Aktualizacja wartości rzeczywistych projektu (Fin Ops do PSA) ma już to przekształcenie zdefiniowane.

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Poniższa ilustracja przedstawia przykłady mapowań zadań szablonu w integracji danych. Mapowanie pokazuje informacje z pola, które zostanie zsynchronizowane z rozwiązania Finance and Operations do rozwiązania Project Service Automation.

[![Mapowanie szablonu](./media/ActualsUpdateMapping.jpg)](./media/ActualsUpdateMapping.jpg)

[![Mapowanie szablonu](./media/TransactionConnectionsUpdate.jpg)](./media/TransactionConnectionsUpdate.jpg)




