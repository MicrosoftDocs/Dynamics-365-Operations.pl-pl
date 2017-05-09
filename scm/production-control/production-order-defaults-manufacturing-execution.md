---
title: "Domyślne ustawienia zlecenia produkcyjnego w uruchomieniu produkcji"
description: 
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: JmgProdParameters
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 70073
ms.assetid: 620944ae-3e20-444a-807e-65495f160904
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: b310e799c1ef0756291c5f7ab886531e4caf1945
ms.lasthandoff: 03/31/2017


---

# <a name="production-order-defaults-in-manufacturing-execution"></a>Domyślne ustawienia zlecenia produkcyjnego w uruchomieniu produkcji

[!include[banner](../includes/banner.md)]




Zanim pracownicy przystąpią do rejestrowania produktów w zadaniach produkcyjnych, musisz dokładnie przeanalizować wszystkie ustawienia na stronie **Ustawienia domyślne zlecenia produkcyjnego**. Jeśli firma używa funkcji wielooddziałowości, można skonfigurować różne ustawienia domyślne dla zleceń produkcyjnych dla każdego oddziału. Ustawienia domyślne zamówienia do integracji z Kontrolą produkcji ustawia się na następujących kartach na stronie **Ustawienia domyślne zlecenia produkcyjnego**:

-   **Ogólne** — ogólne wartości domyślne zlecenia dla zadań produkcji w module Uruchomienie produkcji.
-   **Uruchamianie** — domyślne ustawienia zlecenia, które mają być używane przy uruchamianiu zadań lub operacji produkcyjnych.
-   **Operacje** — domyślne ustawienia zlecenia, które są stosowane do zadań lub operacji produkcyjnych oraz informacje zwrotne o operacjach w procesie produkcji.
-   **Zgłaszanie jako gotowych** — domyślne ustawienia zlecenia, które są używane, gdy towary są zgłoszone jako gotowe dla ostatniej operacji zlecenia produkcyjnego.
-   **Weryfikacja ilości** — domyślne ustawienia zlecenia dotyczące sprawdzania poprawności ilości startowych i informacji zwrotnych dla zleceń produkcyjnych.

## <a name="types-of-production-jobs"></a>Typy zadań produkcji
Na karcie **Operacje** wybiera się typy zadań produkcyjnych, które wymagają rejestracji na stronie **Rejestracja zadania**. Na ogół pracownicy dokonują rejestracji w przypadku zadań przezbrajania lub przetwarzania. Jeśli jednak używane jest planowanie zadań, można wybrać inne typy zadań, takie jak zadania transportu, które również wymagają rejestracji w chwili przetworzenia zlecenia produkcyjnego. **Ważne:** Upewnij się, że zostały wybrane wszystkie odpowiednie typy zadań. W przeciwnym wypadku zadania mogą być niedostępne dla rejestracji na stronie **Rejestracja zadania**. Dostosuj wybrane opcje do opcji wybranych w kolumnie **Zarządzanie zadaniami** na stronie **Grupy marszruty**. Jeśli wybrano opcję **Zarządzanie zadaniami** w grupie marszruty, typ zadania będzie raportowany jako zakończony na zleceniu produkcyjnym. Takie raportowanie ma miejsce, gdy zadanie jest zgłaszane jako gotowe w module Uruchomienie produkcji. Kiedy wszystkie typy zadań, dla których wybrano opcję **Zarządzanie zadaniem**, zostaną zgłoszone jako gotowe dla operacji, moduł Uruchomienie zadania również zgłosi operacją jako zakończoną. **Uwaga:** Niektóre zadania mogą być zgłoszone ręcznie poprzez arkusze produkcji. W tym przypadku zaznacz **Zadanie zarządzaniem** dla typu zadania, ale nie wybieraj typu zadania dla rejestracji na karcie **Operacje** na stronie **Ustawienia domyślne zlecenia produkcyjnego**.

## <a name="bom-consumption-and-picking-list-journals"></a>Arkusze zużycia BOM i list pobrania
Materiały można ustawić w taki sposób, żeby były one zużywane automatycznie lub ręcznie podczas produkcji. Automatyczne zużycie jest kontrolowane przez regułę usuwania ustawioną w wierszach listy składowej (BOM) i w ustawieniu pola **Automatyczne zużycie BOM** w wartości domyślnej zlecenia produkcyjnego. Automatyczne zużycie można skonfigurować tak, żeby było wykonywane podczas rozpoczynania lub zgłaszania wyrobów gotowych zlecenia produkcyjnego. Ewentualnie może ono występować na poziomie zadania podczas uruchamiania lub zakończona zadania.

### <a name="controlling-material-consumption-when-a-production-order-is-started"></a>Kontrolowanie zużycia materiału po uruchomieniu zlecenia produkcyjnego

Zużycie materiału w chwili uruchamiania zlecenia produkcyjnego jest kontrolowane przez pole **Automatyczne zużycie BOM** na karcie **Start**. Dostępne są następujące wartości:

-   **Reguła usuwania** — po uruchomieniu zlecenia produkcyjnego ilości materiałów zużywanych będzie zgodna z regułą usuwania ustawioną w wierszach BOM. W chwili uruchomienia zlecenia zużyte zostaną tylko te wiersze materiałów, które mają regułę usuwania **Start**.
-   **Zawsze** — ilość zużywanego materiału będzie zawsze proporcjonalna do ilości początkowej.
-   **Nigdy** — ilości materiałów, które nigdy nie będą zużywane.

### <a name="controlling-material-consumption-when-a-production-job-is-started-or-completed"></a>Kontrolowanie zużycia materiałów po uruchomieniu lub ukończeniu zlecenia produkcyjnego

Zużycie materiału w chwili uruchamiania lub ukończenia zadana produkcyjnego jest kontrolowane przez pole **Automatyczne zużycie BOM** na karcie **Operacje**. Dostępne są następujące wartości:

-   **Reguła usuwania** — po uruchomieniu lub ukończeniu ilości dla zdania produkcyjnego ilości materiałów zużywanych będzie zgodna z regułą usuwania ustawioną w wierszach BOM. Zużyte zostaną tylko te wiersze materiałów, które mają regułę usuwania **Start** lub **Koniec**.
-   **Zawsze** — ilość zużywanego materiału będzie zawsze proporcjonalna do ilości początkowej zadania.
-   **Nigdy** — ilości materiałów, które nigdy nie będą zużywane.

### <a name="controlling-material-consumption-when-a-production-order-is-reported-as-finished"></a>Kontrolowanie zużycia materiału po zgłoszeniu zlecenia produkcyjnego jako gotowego

Zużycie materiału w trakcie procesu zgłaszania jako gotowych dla zlecenia produkcyjnego jest kontrolowane przez pole **Automatyczne zużycie BOM** na karcie **Zgłoszenie wyrobów gotowych**. Dostępne są następujące wartości:

-   **Reguła usuwania** — po zgłoszeniu zlecenia produkcyjnego jako gotowego ilości materiałów zużywanych będzie zgodna z regułą usuwania ustawioną w wierszach BOM. Zużyte zostaną tylko te wiersze materiałów, które mają regułę usuwania **Koniec**.
-   **Zawsze** — ilość zużywanego materiału będzie zawsze proporcjonalna do ilości zgłaszanej jako gotowej.
-   **Nigdy** — ilości materiałów, które nigdy nie będą zużywane.





