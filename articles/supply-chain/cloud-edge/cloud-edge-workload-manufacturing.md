---
title: Obciążenia pracą dotyczące uruchomienia produkcji dla jednostek skalowania chmury i urządzenia brzegowego
description: W tym temacie opisano, jak działa obciążenie pracą nad wykonywaniem produkcji z jednostkami skali w chmurze i urządzenia brzegowego.
author: cabeln
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: cabeln
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: da19066f647c17e934a11e4dab7cb370baabfb5c
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6352743"
---
# <a name="manufacturing-execution-workloads-for-cloud-and-edge-scale-units"></a>Obciążenia pracą dotyczące uruchomienia produkcji dla jednostek skalowania chmury i urządzenia brzegowego

[!include [banner](../includes/banner.md)]

> [!WARNING]
> Obciążenie związane z produkcją jest w tym momencie dostępne w wersji zapoznawczej.
> Nie wszystkie funkcje biznesowe są w pełni obsługiwane w podglądzie publicznym, gdy są używane jednostki skali obciążenia pracą.

W wykonaniu produkcyjnym jednostki wagowe zapewniają następujące możliwości:

- Operatorzy maszyn i kierownicy mogą uzyskać dostęp do operacyjnego planu produkcji.
- Operatorzy maszynowi mogą regularnie aktualizować plan, uruchamiając dyskretne i przetwarzające zadania produkcyjne.
- Kierownik produkcji może skorygować plan operacyjny.
- Pracownicy mogą uzyskać dostęp do modułu czas i frekwencja do zarejestrowania i wyrejestrowania się na brzegu, aby zapewnić poprawne Obliczanie wynagrodzeń pracowników.

W tym temacie opisano, jak działa obciążenie pracą nad wykonywaniem produkcji z jednostkami skali w chmurze i urządzenia brzegowego.

## <a name="the-manufacturing-lifecycle"></a>Cykl produkcyjny

Na poniższej ilustracji przedstawiono cykl produkcyjny podzielony na trzy etapy: *Planowanie*, *wykonywanie* i *finalizowanie*.

[![Fazy wykonania produkcji w przypadku korzystania z jednego środowiska](media/mes-phases.png „Fazy wykonywania produkcji w przypadku korzystania z jednego środowiska”.](media/mes-phases-large.png)

_Faza planu_ obejmuje definicje produktów, planowanie, tworzenie i planowanie zamówień oraz zwalnianie. Krok wydania wskazuje przejście z fazy _planu_ do fazy _wykonania_. Po zwolnieniu zlecenia produkcyjnego zadania zlecenia produkcyjnego będą widoczne w oddziale produkcyjnym i gotowe do wykonania.

Jeśli zadanie produkcji jest oznaczone jako ukończone, następuje przejście z _fazy wykonania_ do _fazy finalizowania_. W fazie _finalizowania_ rejestracje z fazy *wykonania* przechodzą przez przepływ pracy zatwierdzania, gdzie są one obliczane, zatwierdzane i przenoszone. W tym momencie zlecenie produkcyjne zostało zakończone. Z tego powodu generowana jest podstawa wynagrodzenia pracowników.

## <a name="splitting-the-execute-phase-into-a-separate-workload"></a>Dzielenie fazy wykonania na oddzielne obciążenie pracą

W poniższej ilustracji pokazano, kiedy są używane jednostki skalowania, _faza wykonania_ jest dzielona jako oddzielne obciążenie pracą.

[![Fazy wykonania produkcji w przypadku korzystania z jednostek skalowania](media/mes-phases-workloads.png „Fazy produkcji w przypadku korzystania z jednostek skalowania”.](media/mes-phases-workloads-large.png)

Obecnie model pochodzi z instalacji z jednym wystąpieniem do modelu opartego na centrum i jednostkach skali. Fazy _Planowanie_ i _Finalizacja_ są wykonywane jako operacje zaplecza w centrali, a obciążenie pracą nad produkcją jest wykonywane na jednostkach skali. Dane są przesyłane asynchronicznie między jednostkami centrum i skali.

Po zwolnieniu zlecenia produkcyjnego w centrum wszystkie dane wymagane do przetworzenia zadań produkcyjnych są przenoszone do jednostki skali. Dane te obejmują zlecenia produkcyjne, marszruty produkcji, BOM i produkty. Dane, które nie są związane ze zleceniem produkcyjnym (np. działania pośrednie, kody nieobecności i parametry produkcji) są również przenoszone z centrum do jednostki skali. Z reguły dane pochodzące z centrum i przenoszone do jednostki skali mogą być tworzone lub aktualizowane tylko w centrali. Na przykład nie można utworzyć nowego kodu nieobecności lub działania pośredniego w jednostce skali, &mdash;które mogą być używane tylko do rejestracji. Rejestracje dokonywane w jednostkach skali podczas wykonywania są następnie przenoszone do centrum, w którym są przetwarzane Zatwierdzanie czasu i obecności, zapasy i aktualizacje finansowe.

## <a name="manufacturing-execution-tasks-that-can-be-run-on-workloads"></a>Zadania modułu uruchomienie produkcji, które mogą być uruchamiane przy obciążeniu

Następujące zadania dotyczące wykonania produkcji mogą być obecnie uruchamiane przy obciążeniu, gdy używane są jednostki skali:

- Rejestrowanie, logowanie, Wyrejestrowywanie i nieobecność
- Uruchom zadanie
- Pakiety zadań
- Zgłaszanie postępu
- Raportuj odpadki
- Działanie pośrednie
- Przerwa
- Raportuj jako zakończone i odłożone (wymaga uruchomienia obciążenia wykonawczego magazynu na jednostce skalowania patrz również [Reportuj jako zakończone i odłożone na jednostce skalowania](#RAF))

## <a name="working-with-manufacturing-execution-workloads-on-the-hub"></a>Praca z obciążeniem pracą produkcyjną w centrum

Zazwyczaj procesy wymagane do uruchomienia obciążeń uruchomienia produkcji są automatycznie uruchamiane w celu zsynchronizowania centrum i wszystkich jednostek skalowania w razie potrzeby. Jeśli jednak występują problemy, można ręcznie wyzwolić przetwarzanie rejestracji wstępnych otrzymanych z obciążenia pracą i/lub sprawdzić dziennik przetwarzania rejestracji.

### <a name="manually-process-raw-registrations"></a>Ręczne przetwarzanie rejestracji wstępnych

Zadanie wsadowe w module Supply Chain Management jest uruchamiane automatycznie w celu przetworzenia wszystkich rejestracji, które zostały przyjęte na podstawie obciążeń. To zadanie tworzy wymagane arkusze produkcyjne i wpisy w dzienniku połowowym podczas przetwarzania rejestracji dla ukończonego zadania dotyczącego obciążenia pracą.

Mimo że zadanie zazwyczaj jest uruchamiane automatycznie, można je uruchomić ręcznie w dowolnym momencie, logując się do koncentratora i przechodząc do **kontroli produkcji\> Okresowe zadania \>Zarządzanie obciążeniem backoffice\> Przetwarzanie rejestracji wstępnych**.

### <a name="check-the-raw-registration-processing-log"></a>Sprawdź dziennik przetwarzania rejestracji nieprzetworzonej

Aby przejrzeć dziennik przetwarzania rejestracji, zaloguj się do centrum, a następnie przejdź do obszaru **Kontrola produkcji \> Zadania okresowe \> Zarządzanie przepływem pracy backoffice \> Dziennik przetwarzania rejestracji wstępnych**. Na stronie **Dziennik przetwarzania rejestracji wstępnych** jest wyświetlana lista przetworzonych rejestracji wstępnych oraz stan każdej rejestracji.

![Strona dziennika przetwarzania rejestracji nieprzetworzonej.](media/mes-processing-log.png "Strona dziennika przetwarzania rejestracji nieprzetworzonej")

Można pracować z dowolną rejestracją na liście, zaznaczając ją, a następnie wybierając jeden z następujących przycisków w okienku akcji:

- **Proces** — umożliwia ręczne przetworzenie wybranej rejestracji. Ta akcja może być przydatna, jeśli zadanie _Rejestracji wstępnych procesu_ nie zostało uruchomione lub nie powiodło się.
- **Anuluj** — umożliwia anulowanie wybranej rejestracji.

## <a name="working-with-manufacturing-execution-workloads-on-a-scale-unit"></a>Praca z obciążeniem pracą produkcyjną na jednostce skali

Zazwyczaj procesy wymagane do uruchomienia obciążeń uruchomienia produkcji są automatycznie uruchamiane w celu zsynchronizowania centrum i wszystkich jednostek skalowania w razie potrzeby. Jeśli jednak występują problemy, można sprawdzić historię zamówień, które zostały przetworzone na jednostkę skali, lub ręcznie uruchomić _Centrum wytwarzania na potrzeby skalowania procesora komunikatów jednostki_.

### <a name="view-the-history-of-manufacturing-jobs-that-have-been-processed-on-a-scale-unit"></a>Umożliwia wyświetlenie historii zadań produkcji, które zostały przetworzone na jednostkę skali

Aby przejrzeć historię zadań produkcji, które zostały przetworzone na jednostkę skali, należy zalogować się na jednostce skalowania i przejść do obszaru **Kontrola produkcji \> Zadania okresowe \>Zarządzanie obciążeniem backoffice  \> Historia przetwarzania zadań produkcji**. Na stronie **Historia przetwarzania zadań produkcji** jest wyświetlana historia przetwarzania zleceń produkcyjnych na jednostkę skali. Można pracować z dowolnym zleceniem produkcji na liście, zaznaczając go, a następnie wybierając jeden z następujących przycisków w okienku akcji:

- **Proces** — umożliwia ręczne przetworzenie wybranego zlecenia produkcyjnego.
- **Anuluj** — umożliwia anulowanie wybranego zlecenia produkcyjnego.

### <a name="manufacturing-hub-to-scale-unit-message-processor-job"></a>Zadanie procesora w ramach centrum produkcji dla wiadomości jednostki skalowania

_Zadanie procesora produkcyjnego w centrum produkcji_ przetwarza dane z centrum do jednostki skali. To zadanie jest uruchamiane automatycznie po wdrożeniu obciążenia pracą modułu uruchomienie produkcji. Można jednak uruchomić ją ręcznie w dowolnym momencie, przechodząc do **Kontrola produkcji \> Zadania okresowe \> Zarządzanie obciążeniem backoffice \> Zadanie procesora w ramach centrum produkcji dla wiadomości jednostki skalowania**.

<a name="RAF"></a>

## <a name="report-as-finished-and-putaway-on-a-scale-unit"></a>Zgłoś jako gotowe i odłóż na jednostce skalowania

<!-- KFM: 
This section describes how to enable the abilities to report as finished and then putaway finished items when you are using to a scale unit.

### Enable and use report as finished and putaway on a scale unit -->

W bieżącej wersji operacje raportowania jako zakończone i odłożone (dla produktów gotowych, półproduktów i produktów ubocznych) są obsługiwane przez [obciążenie wykonawcze magazynu](cloud-edge-workload-warehousing.md) (a nie przez obciążenie wykonawcze produkcji). Aby korzystać z tej funkcji w przypadku połączenia z jednostką skalowania, należy wykonać następujące czynności:

- Zainstaluj zarówno obciążenie wykonawcze magazynu, jak i obciążenie wykonawcze produkcji na swojej jednostce skalowania.
- Użyj aplikacji mobilnej Warehouse Management, aby zgłosić jako zakończone i przetworzyć pracę odłożenia. Interfejs wykonywania produkcji nie obsługuje obecnie tych procesów.

<!-- KFM: API details needed

### Customize report as finished and putaway functionality

 -->

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
