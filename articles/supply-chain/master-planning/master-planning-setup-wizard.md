---
title: Kreator konfiguracji planowania głównego
description: W tym temacie opisano różne ważne strategie i parametry używane do konfigurowania planowania głównego.
author: t-benebo
manager: AnnBe
ms.date: 08/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-05-31
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: 0310ac55d35421d8ad9080739fc5a393660ce520
ms.sourcegitcommit: 261dc882710f29303b14f9be8a26d71d85d25345
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2019
ms.locfileid: "1999541"
---
# <a name="master-planning-setup-wizard"></a>Kreator konfiguracji planowania głównego

[!include [banner](../includes/banner.md)]

Ten temat zawiera przewodnik **Kreatora konfiguracji planowania głównego**. Wyjaśnia, jak są obliczane są sugestie parametrów, i zawiera przykłady pokazujące, jak różne firmy konfigurują planowanie główne na podstawie ich potrzeb biznesowych.

## <a name="specific-requirements-of-your-company"></a>Szczególne wymagania Twojej firmy

Na pierwszej stronie kreatora znajdują się pytania o konkretne wymagania firmy. Odpowiedzi na te pytania nie muszą być dokładne, ale należy podać przybliżoną liczbę elementów i planowanych zleceń dla firmy. Na podstawie odpowiedzi konfigurowane są parametry odnoszące się do Twojej firmy, nie tylko do wybranego planu głównego. W poniższych sekcjach opisano parametry, które są obliczane i formuły, które są używane.

### <a name="number-of-threads"></a>Liczba wątków

- **Jeśli produkujesz dowolne z tych elementów:** Liczba wątków = Liczba zamówień planowanych ÷ 1000
- **Jeśli nie produkujesz żadnych z tych elementów:** Liczba wątków = Liczba elementów ÷ 1000

Jeśli liczba obliczanych wątków przekracza 75 procent dostępnej liczby wątków, stosowane jest ograniczenie 75 procent liczby wątków dostępnych dla każdego klienta. (Liczba dostępnych wątków zostanie ustalona dla każdego klienta).

Aby uzyskać więcej informacji, zobacz temat [Liczba wątków](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/master-planning/master-planning-performance#number-of-threads).

### <a name="bundle-size"></a>Rozmiar pakietu

Rozmiar pakietu zostanie ustawiony na **1**. Ta wartość jest często najlepszą wartością, ponieważ pomaga poprawić wydajność planowania głównego.

Aby uzyskać więcej informacji, zobacz temat [Liczba zadań w pakiecie zadań wątku](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/master-planning/master-planning-performance#number-of-tasks-in-helper-task-bundle).

### <a name="firming-bundle-size"></a>Rozmiar pakietu akceptacji

- **Jeśli produkujesz dowolny z tych elementów:** Rozmiar pakietu akceptacji zostanie ustawiony na większą z tych dwóch wartości: **10** i obliczenie pakietu
- **Jeśli nie produkujesz żadnego z tych elementów:** Rozmiar pakietu akceptacji zostanie ustawiony na większą z tych dwóch wartości: **50** i obliczenie pakietu

Obliczanie pakietu = (Liczba zamówień planowanych × (Horyzont czasowy akceptacji ÷ Horyzont czasowy zapotrzebowania) ÷ Liczba wątków) ÷ 10

### <a name="cache-size"></a>Rozmiar pamięci podręcznej

Rozmiar pamięci podręcznej zostanie ustawiony na **Maksymalny**. Ta wartość jest często najlepszą wartością, ponieważ pomaga poprawić wydajność planowania głównego.

Aby uzyskać więcej informacji, zobacz [Przydzielanie czasu do zadań w pakiecie zadań](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/allocate-time-jobs-job-bundle).

### <a name="manufacturing-setup"></a>Konfiguracja produkcji

Jeśli produkujesz towary, strona **Konfiguracja produkcji** pojawi się później w kreatorze.

## <a name="scope-of-the-current-plan"></a>Zakres bieżącego planu

Na stronie **Zakres bieżącego planu** odpowiadasz na pytania pokazujące, jak daleko w przyszłości różne wymagania zostaną uwzględnione i obliczone w planowaniu głównym. Każde pytanie dotyczy tego, czy chcesz użyć funkcji i jak chcesz ją skonfigurować.

Na przykład w odniesieniu do funkcji planu prognozy kreator zapyta: „Czy chcesz użyć planu prognozy w planowaniu głównym, tak aby planowane zamówienia były sugerowane do spełnienia prognozowanego popytu?”

Dostępne są następujące opcje:

- **Nie** — planowanie główne nie sugeruje planowanych zamówień do spełnienia prognozy. Na karcie **Horyzonty czasowe** strony **Plany główne** (**Planowanie główne \> Ustawienia \> Plany \> Plany główne**) kreator ustawi opcję **Plan prognozy (horyzont czasowy)** na **Tak** i ustawi liczbę dni na **0** (zero). Ta konfiguracja zastąpi horyzont czasowy określony w grupie zapotrzebowania. Ponieważ liczba dni jest równa **0** (zero), funkcja nie będzie używana.
- **Tak, zgodnie z definicją w tym planie głównym** — pole staje się dostępne, gdzie można wprowadzić liczbę dni, przez które planowanie główne zasugeruje planowane zamówienia do spełnienia prognozowanego popytu. Kreator ustawi opcję **Plan prognozy (horyzont czasowy)** na **Tak** i ustawi liczbę dni wprowadzaną w polu **Plan wg prognozy** na karcie **Horyzonty czasowe** strony **Plany główne**. Ta konfiguracja zastąpi wartości, które są ustawiane w grupach zapotrzebowania.
- **Tak, zgodnie z definicją w zasięgu** – Kreator ustawi opcję **Horyzont czasowy planu wg prognozy** na **Nie**. Ogrodzenia czasowe określone w grupie zapotrzebowania zostaną użyte do określenia czasu zaplanowania prognozy.

Pozostałe pytania na tej stronie i odpowiedzi na nie podążają tym samym schematem:

- **Nie** — opcja **Plan prognozy (horyzont czasowy)** będzie ustawiona na wartość**Tak**, a liczba dni będzie równa **0** (zero).
- **Tak, zgodnie z definicją tego planu głównego** – opcja **Plan prognozy (horyzont czasowy)** jest ustawiona na **Tak**. Zostanie użyta wprowadzona liczba dni i zastąpi wartości ustawione w grupach zapotrzebowania.
- **Tak, zgodnie z definicją w grupie zapotrzebowania** – opcja **Plan prognozy (horyzont czasowy)** będzie ustawiona na **Nie**.

Aby uzyskać więcej informacji o planowaniu zadań, zobacz temat [Planowanie zadań](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/job-scheduling).

## <a name="scheduling-options"></a>Opcje planowania

Strona **Opcje planowania** pojawia się tylko wtedy, gdy udzielono odpowiedzi **Tak** na pytanie „Czy produkujesz dowolne z planowanych towarów?” na pierwszej stronie kreatora.

Odpowiedź na pierwsze pytanie na tej stronie („Czy trzeba zaplanować operacje podzielone na poszczególne zadania?”) określa metodę planowania na karcie **Ogólne** na stronie **Plany główne**.

- **Tak** – zostanie użyte planowanie zadań.
- **Nie** — zostanie użyty harmonogram operacji.

Aby uzyskać więcej informacji, zobacz tematy [Planowanie operacji](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/operations-scheduling) i [Planowanie zadań](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/job-scheduling).

## <a name="updates-of-demand-and-supply"></a>Aktualizacje popytu i podaży

Pytania na stronie **Aktualizacje popytu i podaży** są związane z akceptowaniem, wiadomościami akcji i opóźnieniami.

Konfiguracja planowania głównego zostanie zaktualizowana na podstawie odpowiedzi, zgodnie z tym samym schematem, który jest opisany w poprzedniej sekcji:

- **Nie** — opcja **Plan prognozy** na stronie **Plany główne** będzie ustawiona na wartość **Tak**, a liczba dni będzie równa **0** (zero).
- **Tak, zgodnie z definicją tego planu głównego** – opcja **Horyzont czasowy** będzie ustawiona na wartość **Tak**. Zostanie użyta wprowadzona liczba dni i zastąpi wartości ustawione w grupach zapotrzebowania.
- **Tak, zgodnie z definicją w grupie zapotrzebowania** – opcja **Horyzont czasowy** będzie ustawiona na wartość **Nie**.

W przypadku obliczonych opóźnień odpowiedzi na pytania w kreatorze zaktualizują odpowiednie parametry na karcie **Obliczone opóźnienia** na stronie **Plany główne**.

## <a name="summary-of-your-changes"></a>Podsumowanie zmian

Ostatnia strona kreatora pokazuje zmiany, które są zalecane na podstawie udzielonych odpowiedzi. Pokazuje zarówno wartość w ustawieniach (**Bieżąca konfiguracja**), jak i wartość, którą zaleca kreator (**Nowa konfiguracja**).

Można również modyfikować parametry w nowej konfiguracji. Parametry są podzielone na parametry, które odnoszą się do firmy i parametry, które mają zastosowanie tylko do wybranego planu głównego. Aby wyświetlić wszystkie parametry instalacji, które można zmienić za pomocą kreatora, wybierz **Pokaż wszystkie parametry** u dołu strony. Następnie można zmienić parametry.

Na koniec po wybraniu opcji **Zakończ** zostanie zastosowana nowa konfiguracja. W przypadku wybrania opcji**Anuluj** nie są stosowane żadne zmiany.

## <a name="examples"></a>Przykłady

W tej sekcji opisano konfigurację dwóch firm fikcyjnych, aby pokazać, jak konfiguracja może się zmienić w zależności od potrzeb każdej firmy.

### <a name="example-1-contoso-manufacturer"></a>Przykład 1: Contoso Manufacturer

Contoso Manufacturer jest firmą produkcyjną produkującą głośniki. Kupuje ona różne surowce i komponenty od różnych dostawców, które są następnie wykorzystywane do produkcji finalnych głośników. Oto niektóre cechy łańcucha dostaw i produkcji:

- Finalne towary, które produkuje firma, mają strukturę listy składowej (BOM).
- Wszystkie elementy i komponenty końcowe są planowane przez planowanie główne. Ręczne planowanie nie jest wykonywane.
- Trasa operacji jest zdefiniowana dla produkcji każdego elementu końcowego.
- Zakład produkcyjny produkuje produkty końcowe. Posiada określoną liczbę frezarek i wiertarek, które są używane do obróbki komponentów. Poszczególne komponenty muszą być przetwarzane przez te maszyny.
- Jest wielu dostawców. Średni czas realizacji wynosi jeden tydzień. Grupa elementów od tego samego dostawcy będzie miała czas realizacji siedmiu tygodni.

W kreatorze są wprowadzane następujące wartości dla Contoso Manufacturer:

- **Zapotrzebowanie:**

    - **Pytanie:** „Czy chcesz określić liczbę dni horyzontu planowania?”
    - **Odpowiedź:** „Tak, zgodnie z definicją w grupach zapotrzebowania”.

    Ponieważ czas realizacji dla elementów jest bardzo różny, Contoso nie musi planować wszystkich elementów dla tego samego okresu w przyszłości. Tworzone są grupy zapotrzebowania dla elementów. Elementy, które mają podobny czas realizacji są przypisane do tej samej grupy zapotrzebowania. Horyzont planowania dla każdej grupy zapotrzebowania (tj. horyzont czasowy zapotrzebowania) jest w przybliżeniu czas realizacji plus margines jednego tygodnia. Planowanie główne następnie sprawdza, czy elementy są planowane z wyprzedzeniem, w oparciu o ich czas realizacji.

    W związku z tym w tym przykładzie zostaną utworzone dwie grupy zapotrzebowania. Jeden grupa zapotrzebowania będzie mieć horyzont czasowy zapotrzebowania dwóch tygodni, a druga będzie mieć horyzont czasowy zapotrzebowania ośmiu tygodni.

    Jeśli jako odpowiedź wybrano opcję **Tak, zgodnie z definicją w tym planie głównym**, liczba dni, które są wprowadzane, powinny przekraczać najdłuższy czas realizacji wszystkich elementów. Jednak, ponieważ wiele elementów nie musi być planowanych z tak dalekim wyprzedzeniem, wiele planowanych zleceń będzie obliczanych, ale nigdy nie będzie używanych. Z tego powodu czas trwania planowania głównego zwiększy się.

- **Planowanie:**

    - **Pytanie:** „Czy trzeba zaplanować operacje podzielone na poszczególne zadania?”
    - **Odpowiedź:** „Tak”.

    Firma Contoso Manufacturing musi zaplanować i ustawić harmonogram poszczególnych zadań, które będą wykonywane na wydziale produkcyjnym. W związku z tym będzie używać planowania zadań.

- **Zdolności produkcyjne:**

    - **Pytanie:** „Czy chcesz zaplanować korzystanie ze zdolności produkcyjnych zasobów?”
    - **Odpowiedź:** „Tak, zgodnie z definicją w planie głównym”. Wprowadzana jest wartość **10 dni**.

    Liczba frezarek i wiertarek jest ograniczona. Planowanie produkcji musi uwzględniać to ograniczenie i zorganizować zadania w czasie zgodnie z tą dostępnością. Innymi słowy zaplanowane zadania zostaną ponownie zaplanowane na podstawie ograniczeń zasobów. Planowanie będzie używać czasu realizacji oprócz okresu, który jest zdefiniowany. (Planowane zlecenia produkcyjne mogą się nakładać). Ponieważ czas realizacji produkcji dla towarów wynosi siedem dni, zdolności produkcyjne zasobów dla planowania głównego będą brane pod uwagę w okresie 10 dni.

- **Harmonogram:**

    - **Pytanie:** „Czy chcesz ustawiać kolejność planowanych zamówień przy użyciu wartości sekwencji produktu?”
    - **Odpowiedź:** „Tak, zgodnie z definicją w grupach zapotrzebowania”.

    Trasa jest zdefiniowana dla produkcji każdego elementu końcowego. Dlatego planowanie główne zaplanuje zamówienia w czasie zgodnie ze zdefiniowanymi trasami.

- **Rozłożenie:**

    - **Pytanie:** „Czy chcesz zaplanować zamówienia dla wszystkich elementów na liście składowej (BOM) (plan dla elementu nadrzędnego i wszystkich elementów podrzędnych)?”
    - **Odpowiedź:** „Tak, zgodnie z definicją w grupach zapotrzebowania”.

    Wszystkie elementy, które są używane do produkcji, muszą być planowane. Ponieważ elementy mają bardzo różne czasy realizacji, planowanie główne będzie miało lepszą wydajność, gdy używane są grupy zapotrzebowania. Znów, można wprowadzić margines jednego tygodnia, a rozłożenie może być wykonane w tym samym czasie, co zapotrzebowanie.

### <a name="example-2-contoso-retailer"></a>Przykład 2: Contoso Retailer

Contoso Retailer to firma dystrybucyjna w branży mody. Używa planowania głównego do obliczania, kiedy należy umieścić zamówienia zakupu, na podstawie prognozowanej sprzedaży. Oto niektóre cechy charakterystyczne procesów tej firmy:

- Contoso Retailer używa prognozy popytu do przewidywania sprzedaży. Zamówienia zakupu będą planowane zgodnie z prognozą.
- Sklepy sieci sprzedaży używają zapotrzebowania do uzupełniania zapasów.
- Czas realizacji z magazynu głównego do każdego sklepu wynosi około dwóch tygodni dla wszystkich towarów.

W kreatorze są wprowadzane następujące wartości dla Contoso Retailer:

- **Prognoza popytu:**

    - **Pytanie:** „Czy chcesz użyć planu prognozy w planowaniu głównym, aby planowane zamówienia były sugerowane do spełniania prognozowanego popytu?”
    - **Odpowiedź:** „Tak, zgodnie z definicją w planie głównym”.

    Firma Contoso uwzględniła prognozę popytu, aby przewidzieć swoją sprzedaż. Dlatego planowanie główne musi zalecać planowane zamówienia celem spełnienia prognozy.

- **Akceptacja:**

    - **Pytanie:** „Czy chcesz, aby planowanie główne automatycznie akceptowało zaplanowane zamówienia w dokumentach zamówienia, na przykład w zamówieniach produkcyjnych lub zakupu?”
    - **Odpowiedź:** „Tak, zgodnie z definicją w planie głównym”. Wprowadzana jest wartość **1 dzień**.

    Ponieważ Contoso Retailer będzie tworzyć zamówienia zakupu bezpośrednio z planowanych zamówień zakupu, jest to przydatne, jeśli planowane zamówienia zakupu są automatycznie ustalane. Ponieważ planowanie główne jest uruchamiane każdego dnia, jednodniowy horyzont czasowy akceptacji automatycznie zaakceptuje wszystkie zlecenia, które są wymagane na następny dzień.

- **Zatwierdzone zapotrzebowania:**

    - **Pytanie:** „Czy chcesz uwzględnić popyt z zatwierdzonych zapotrzebowań do uzupełniania zapasów w sklepach?”
    - **Odpowiedź:** „Tak, zgodnie z definicją w planie głównym”. Wprowadzana jest wartość **1 dzień**.

    Contoso używa zatwierdzonych zapotrzebowań ze sklepów sieci sprzedaży, aby tworzyć planowane zamówienia zakupu w celu uzupełnienia tych magazynów. Ponieważ planowanie główne jest uruchamiane każdego dnia, zapotrzebowania z ostatniego dnia zostaną uwzględnione w planowaniu.
