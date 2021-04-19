---
title: Parametry produkcji w module Wykonywanie produkcji
description: Ten temat zawiera informacje o ustawieniach parametrów produkcji w module Wykonywanie produkcji.
author: johanhoffmann
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 30bbcd0365fada4554dc2f7d12b40abc9b22ac63
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814615"
---
# <a name="production-parameters-in-manufacturing-execution"></a>Parametry produkcji w module Wykonywanie produkcji

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje o ustawieniach parametrów produkcji w module Wykonywanie produkcji.

Moduł **Wykonywanie produkcji** jest przeznaczony głównie dla firm produkcyjnych. Może być używany do rejestrowania zużycia czasu i towarów w zadaniach produkcyjnych lub projektach. Przed rozpoczęciem używania modułu Wykonywanie produkcji do rejestrowania zadań należy skonfigurować różne parametry produkcji określające, jak i kiedy rejestracje są księgowane w trakcie procesu produkcji. Ustawienia parametrów produkcji wpływają na zarządzanie zapasami, zarządzanie produkcją i obliczanie kosztów.

Zanim pracownicy przystąpią do rejestrowania zużycia w zadaniach produkcyjnych, musisz dokładnie przeanalizować wszystkie ustawienia na stronie **Parametry produkcji**. Kliknij kolejno opcje **Kontrola produkcji** &gt; **Ustawienia** &gt; **Wykonywanie produkcji** &gt; **Ustawienia domyślne zlecenia produkcyjnego**. Jeśli firma używa funkcji wielooddziałowości, można skonfigurować różne parametry produkcji dla każdego oddziału. Parametry integracji z modułem **Produkcja** konfiguruje się na następujących kartach na stronie **Parametry produkcji**:

- **Ogólne** — ogólne parametry zadań produkcyjnych w module Wykonywanie produkcji.
- **Rozpoczęcie** — parametry używane w momencie rozpoczęcia operacji produkcyjnych.
- **Operacje** — parametry stosowane do zadań lub operacji produkcyjnych oraz informacje zwrotne o operacjach w trakcie procesu produkcji.
- **Zgłoszenie wyrobów gotowych** — parametry używane, gdy towary są zgłaszane jako gotowe w ostatniej operacji zlecenia produkcyjnego.
- **Weryfikacja ilości** — parametry służące do sprawdzania poprawności ilości startowych i podawanych w informacjach zwrotnych dla zleceń produkcyjnych.

## <a name="types-of-production-jobs"></a>Typy zadań produkcji
Na karcie **Operacje** wybiera się typy zadań produkcyjnych, które wymagają rejestracji na stronie **Rejestracja zadania**.

Na ogół pracownicy dokonują rejestracji w przypadku zadań przezbrajania lub przetwarzania. Jeśli jednak używane jest planowanie zadań, można wybrać inne typy zadań, które również wymagają rejestracji podczas przetwarzania zleceń produkcyjnych. Na przykład można wymagać rejestrowania dla zadań transportu.

> [!IMPORTANT]
> Upewnij się, że zostały wybrane wszystkie odpowiednie typy zadań. W przeciwnym wypadku zadania mogą być niedostępne dla rejestracji na stronie **Rejestracja zadania**. Wybrane opcje powinny odpowiadać opcjom wybranym w kolumnie **Zarządzanie zadaniami** na karcie **Ustawienia** na stronie **Grupy marszrut** strony (**Kontrola produkcji** &gt; **Ustawienia** &gt; **Marszruty** &gt; **Grupy marszrut**).

Jeśli zaznaczona jest opcja **Zarządzanie zadaniami** w grupie marszrut, ten typ zadania na zleceniu produkcyjnym zostanie zgłoszony jako gotowy, gdy zadanie zostanie zgłoszone jako gotowe w module Wykonywanie produkcji. Kiedy wszystkie typy zadań, dla których wybrano opcję **Zarządzanie zadaniami**, zostaną zgłoszone jako gotowe dla operacji, moduł Wykonywanie produkcji zgłosi operacją jako zakończoną.

> [!NOTE]
> Niektóre typy zadań mogą być zgłaszane ręcznie poprzez arkusze produkcji. W takim przypadku zaznacz opcję **Zarządzanie zadaniami** dla typu zadania, ale nie wybieraj typu zadania dla rejestracji na karcie **Operacje** na stronie **Parametry produkcji** w module Wykonywanie produkcji.

## <a name="bom-consumption-and-picking-list-journals"></a>Arkusze zużycia BOM i list pobrania
Ważna jest spójna konfiguracja zużycia list składowych (BOM), ponieważ pomaga to zagwarantować efektywne zarządzanie zapasami. Na przykład jeśli parametry zużycia BOM nie są poprawnie skonfigurowane w module Wykonywanie produkcji, materiały mogą być odejmowane z zapasów dwa razy albo wcale.

Na stronie **Parametry produkcji** automatyczne zużywanie BOM ustawia się w trzech etapach:

- Na początku produkcji. Ustaw ten etap na karcie **Rozpoczęcie**.
- W trakcie procesu produkcji podczas kończenia operacji. Ustaw ten etap na karcie **Operacje**.
- Podczas zgłaszania zlecenia produkcyjnego jako zakończonego. Ustaw ten etap na karcie **Zgłoszenie wyrobów gotowych**.

Dla każdego etapu w polu **Automatyczne zużycie BOM** można wybrać jedną z trzech metod pobierania towarów do zlecenia produkcyjnego:

- **Reguła rozliczania** — ta opcja jest używana w połączeniu z opcją zdefiniowaną dla BOM w module **Produkcja**. Kliknij kolejno opcje **Kontrola produkcji** &gt; **Wspólne** &gt; **Zlecenia produkcyjne** &gt; **Wszystkie zlecenia produkcyjne**. Na stronie **Wszystkie zlecenia produkcyjne** zaznacz zlecenie produkcyjne na liście, a następnie w okienku akcji kliknij opcję **BOM**. Na stronie **BOM** na karcie **Ustawienia** w polu **Reguła rozliczania** wybierz jedną z następujących opcji:

  - **Rozpoczęcie**
  - **Zakończenie**
  - **Ręcznie**
  - Puste (nie jest wybrana żadna opcja)
  - **Dostępne w lokalizacji**

    W module Wykonywanie produkcji jeśli opcja **Reguła rozliczania** zostanie wybrana w polu **Automatyczne zużycie BOM** na karcie **Rozpoczęcie**, wszystkie materiały, które w BOM mają ustawioną opcję **Rozpoczęcie**, będą odejmowane z zapasów z chwilą rozpoczęcia operacji. Opcja **Dostępne w lokalizacji** jest używana do produktów, które są włączone dla zaawansowanych procesów magazynowych. Jeśli wybierzesz tę zasadę rozliczania, materiał jest rozliczany po zakończeniu pracy magazynowej pobrania surowca. Materiał jest także rozliczany, gdy wiersz BOM używający tej zasady rozliczania jest zwalniany do magazynu, a materiał jest dostępny w lokalizacji wejściowej produkcji.

    > [!NOTE]
    > Jeżeli pole **Reguła rozliczania** jest ustawione na karcie **Początek** w module Uruchomienie produkcji, należy wybrać tę samą zasadę na karcie **Operacje** lub **Zgłoś jako gotowe**. To wymaganie pomaga zagwarantować, że materiały zostaną odjęte z zapasów na listach BOM, które używają opcji **Zakończenie** jako reguły rozliczania w zamówieniu produkcji. Jeśli ta sama reguła rozliczania nie jest zaznaczona na karcie **Operacje** lub **Zgłoszenie wyrobów gotowych**, materiały mogą być odejmowane z zapasów dwa razy.

- **Zawsze** — Po wybraniu tej opcji dla etapu materiały są zawsze odejmowane z zapasów na tym etapie. Na przykład materiały do produkcji są odejmowane po rozpoczęciu zlecenia produkcyjnego. To ustawienie wymaga, aby na kartach **Operacje** i **Zgłoszenie wyrobów gotowych** była zaznaczona opcja **Nigdy**. Wymaganie to zapobiega odejmowaniu towarów z magazynu dwa razy.
- **Nigdy** — Wybranie tej opcji dla etapu powoduje, że na tym etapie nie występuje żadne zużycie BOM. Na przykład jeśli wybierzesz opcję **Nigdy** na wszystkich trzech kartach (**Rozpoczęcie**, **Operacje** i **Zgłoszenie wyrobów gotowych**), materiały muszą zostać ręcznie odjęte z zapasów.

> [!IMPORTANT]
> Należy dokładnie przemyśleć konfigurację parametrów produkcji i upewnić się, że parametry zaznaczone na różnych kartach strony **Parametry produkcji** nie są wzajemnie sprzeczne.

Poniższe przykłady ilustrują ustawienia parametrów obsługujących różne zasady zużywania BOM. Parametry konfiguruje się na stronie **Parametry produkcji** w module Wykonywanie produkcji.

### <a name="example-1-backflushing-on-operations"></a>Przykład 1: Wstecznie rozliczanie w operacjach

Użyj poniższych ustawień, jeśli arkusze list pobrania i zużycie towarów z BOM powinny być generowane, gdy towary są zgłaszane jako gotowe w operacji.

| Karta                | Pole                          | Ustawienie                             |
|--------------------|--------------------------------|-------------------------------------|
| Rozpocznij              | Aktualizuj start online           | **Stan** lub **Stan + ilość** |
| Rozpocznij              | Automatyczne zużycie BOM      | **Nigdy**                           |
| Operations         | Automatyczne zużycie BOM      | **Zawsze**                          |
| Zgłoszenie wyrobów gotowych | Automatyczne zużycie BOM      | **Nigdy**                           |
| Zgłoszenie wyrobów gotowych | Aktualizuj raport zakończonych online | **Stan + ilość**               |

### <a name="example-2-backflushing-on-production"></a>Przykład 2: Wstecznie rozliczanie w produkcji

Użyj poniższych ustawień, jeśli arkusze list pobrania i zużycie towarów z BOM powinny być generowane, gdy towary są zgłaszane jako gotowe w zleceniu produkcyjnym.

| Karta                | Pole                          | Ustawienie                             |
|--------------------|--------------------------------|-------------------------------------|
| Rozpocznij              | Aktualizuj start online           | **Stan** lub **Stan + ilość** |
| Rozpocznij              | Automatyczne zużycie BOM      | **Nigdy**                           |
| Operations         | Automatyczne zużycie BOM      | **Nigdy**                           |
| Zgłoszenie wyrobów gotowych | Automatyczne zużycie BOM      | **Zawsze**                          |
| Zgłoszenie wyrobów gotowych | Aktualizuj raport zakończonych online | **Stan + ilość**               |

### <a name="example-3-flushing-principle"></a>Przykład 3: Reguła rozliczania

Użyj tych ustawień, jeśli arkusze list pobrania i zużycie towarów z BOM powinny być generowane zgodnie z regułą rozliczania ustawioną dla towarów BOM.

| Karta                | Pole                          | Ustawienie                |
|--------------------|--------------------------------|------------------------|
| Rozpocznij              | Aktualizuj start online           | **Stan + ilość**  |
| Rozpocznij              | Automatyczne zużycie BOM      | **Reguła rozliczania** |
| Operations         | Automatyczne zużycie BOM      | **Reguła rozliczania** |
| Zgłoszenie wyrobów gotowych | Automatyczne zużycie BOM      | **Nigdy**              |
| Zgłoszenie wyrobów gotowych | Aktualizuj raport zakończonych online | **Stan + ilość**  |

### <a name="example-4-deduction-of-materials-during-startup-of-a-production-order"></a>Przykład 4: Odejmowanie materiałów podczas uruchamiania zlecenia produkcyjnego

Użyj poniższych ustawień, jeśli arkusze list pobrania i zużycie towarów z BOM powinny być generowane podczas rozpoczynania produkcji.

| Karta                | Pole                          | Ustawienie                             |
|--------------------|--------------------------------|-------------------------------------|
| Rozpocznij              | Aktualizuj start online           | **Stan + ilość**               |
| Rozpocznij              | Automatyczne zużycie BOM      | **Zawsze**                          |
| Operations         | Automatyczne zużycie BOM      | **Nigdy**                           |
| Zgłoszenie wyrobów gotowych | Automatyczne zużycie BOM      | **Nigdy**                           |
| Zgłoszenie wyrobów gotowych | Aktualizuj raport zakończonych online | **Stan** lub **Stan + ilość** |

Zgodnie z opcjami opisanymi wcześniej w tej sekcji arkusze list pobrania są księgowane na różnych etapach procesu zlecenia produkcyjnego:

- W momencie rozpoczęcia operacji
- Gdy informacja zwrotna dotycząca ilości jest zgłaszana dla operacji
- Gdy towary są zgłaszane jako gotowe w ramach zlecenia produkcyjnego

### <a name="example-5-manual-bom-consumption"></a>Przykład 5: Ręczne zużywanie BOM

Jeśli materiały zawsze mają być ręcznie odejmowane z zapasów, można użyć następujących ustawień. W takim przypadku arkusze list pobrania nie są księgowane.


|        Karta         |             Pole              |         Ustawienie         |
|--------------------|--------------------------------|-------------------------|
|       Rozpocznij        |      Aktualizuj start online      | <strong>Stan</strong> |
|       Rozpocznij        |   Automatyczne zużycie BOM    | <strong>Nigdy</strong>  |
|     Operations     |   Automatyczne zużycie BOM    | <strong>Nigdy</strong>  |
| Zgłoszenie wyrobów gotowych |   Automatyczne zużycie BOM    | <strong>Nigdy</strong>  |
| Zgłoszenie wyrobów gotowych | Aktualizuj raport zakończonych online | <strong>Stan</strong> |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]