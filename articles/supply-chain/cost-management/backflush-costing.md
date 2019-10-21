---
title: Wycena wsteczna
description: Ten temat zawiera wprowadzenie do koncepcji wyceny wstecznej używanej w produkcji oszczędnej.
author: cvocph
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanCosting, LeanCostingTimeBucket
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 272063
ms.assetid: 62a2a7da-ff79-49bf-a6e8-29460ba5252f
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: conradv
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: be4dbadaeac747953af44236156453edc596fcd5
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2019
ms.locfileid: "2018119"
---
# <a name="backflush-costing"></a>Wycena wsteczna

[!include [banner](../includes/banner.md)]

Ten temat zawiera wprowadzenie do koncepcji wyceny wstecznej używanej w produkcji oszczędnej. 

Funkcjonalność wyceny w produkcji wstecznej pozwala, aby w przepływie produkcji używać metody akumulacji kosztów znanej jako wycena wsteczna. W metodzie wyceny wstecznej zużywane materiały bezpośrednie są kumulowane na koncie kosztów pracy w toku (PWT) przepływu produkcji. Jest używana grupa modeli magazynu z kosztem standardowym. Produkty przyjmowane z przepływu produkcji są odejmowane od PWT według ich kosztu standardowego. Główna różnica między wyceną wsteczną a kosztem standardowym polega na tym, że w wycenie wstecznej odchylenia nie są obliczane dla poszczególnych kart Kanban ani wyrobów gotowych. Zamiast tego odchylenia są obliczane dla przepływu produkcji w okresie. Ta metoda wprowadza mechanizm zgłaszania zużycia materiałów rzeczywiście zgodnego z koncepcją produkcji oszczędnej. Dedykowane pobrane ilości materiału nie są zgłaszane względem karty Kanban ani zlecenia produkcyjnego. Zamiast tego pełne partie lub jednostki załadunkowe są umieszczane w przepływie produkcji. Po zarejestrowaniu partii lub jednostek załadunkowych jako pustych są one deklarowane jako zużyte. Może być wykorzystywane zaawansowane zużycie, zależnie od [konfiguracji przepływu produkcji](../production-control/lean-manufacturing-modeling-lean-organization.md). Aby można było stosować zaawansowane zużycie, organizacje muszą włączyć możliwość znikania materiałów w PWT przepływu produkcji. Okresowa wycena wsteczna określa efektywną wartość PWT na koniec okresu. To ustalenie bazuje na jednostkach załadunkowych w systemie Kanban i stanie zadania w systemie Kanban. Odchylenia między wartościami efektywnymi a rzeczywistymi wartościami PWT według grup kosztów i towarów są księgowane i wykazywane jako odchylenia.

## <a name="configuring-backflush-costing"></a>Konfigurowanie wyceny wstecznej
Aby umożliwić kalkulację kosztów (wycenę), należy wykonać następujące czynności konfiguracyjne:

-   **Konfigurowanie kont PWT dla grupy produkcji i przepływu produkcji.** Konta PWT dla przepływu produkcji określa się w grupie produkcji. Aparat przepływu produkcji wyceny wstecznej oblicza odchylenia jako różnicę w wartości PWT przed i po wykonaniu wyceny wstecznej dla każdego przepływu produkcji. Dlatego też zaleca się utworzenie konta PWT dla każdego przepływu produkcji.
-   **Przypisywanie kategorii kosztu do grupy zasobów.** Należy przypisać kategorię kosztu do kategorii czasu procesu komórki roboczej. Aby określić odchylenia według działań, należy utworzyć kategorię kosztu dla każdej komórki roboczej. Kategorie kosztów dla konfiguracji i ilości nie są brane pod uwagę przy wycenie w produkcji oszczędnej. Konta PWT grup zasobów są ignorowane w wyceny wstecznej. W przypadku działań podwykonawczych nie są potrzebne żadne kategorie kosztów. Zamiast tego jest używana grupa kosztów przypisana do aktywnej usługi.
-   **Przypisywanie grup kosztów.** Aby umożliwić segmentację udziałów kosztów w przepływie produkcji, należy przypisać grupy kosztów według typów grup kosztów:
    -   **Grupa kosztów Materiały bezpośrednie** — Materiały bezpośrednie wymagają grupy kosztów, która identyfikuje kategorię materiałów dla wyceny. Ta grupa kosztów umożliwia zagregowany widok kosztu, PWT i odchyleń dla poszczególnych materiałów bezpośrednich.
    -   **Grupa kosztów Produkcja bezpośrednia** — Grupa kosztów Produkcja bezpośrednia rejestruje udział kosztów bezpośrednich zasobów operacyjnych w przepływie produkcji. Ta grupa kosztów umożliwia zagregowany widok kosztu, PWT i odchyleń dla poszczególnych kosztów produkcji bezpośrednich.
    -   **Grupa kosztów Pośrednie** — Grupa kosztów Pośrednie jest wymagana w celu obliczenia udziału kosztów pośrednich w przepływie produkcji. Ta grupa kosztów umożliwia zagregowany widok kosztu, PWT i odchyleń dla poszczególnych kosztów pośrednich.
    -   **Grupa kosztów Outsourcing bezpośredni** — Grupa kosztów dla usług umożliwia zagregowany widok przypisanych kosztów i PWT oraz określa odchylenia kosztów usług podwykonawczych.
    -   **Grupa kosztów wyrobu gotowego** — Wyroby gotowe wymagają grupy kosztów, która określa kategorię produktów dla wyceny. Ta grupa kosztów umożliwia zagregowany widok kosztu, PWT i odchyleń dla poszczególnych kategorii produktów. Koszty standardowe produktów są obliczane poprzez obliczanie kosztów oparte liście składowej (BOM) oraz przepływie produkcji i regułach Kanban lub marszruty.

### <a name="costing-sheet"></a>Arkusz wyceny

Arkusz wyceny modeluje strukturę kosztów firmy i jest tworzony przez grupy kosztów w celu klasyfikowania kosztu. Arkusz wyceny przybiera różne formy. Pokazuje informacje o kosztach zgodnie ze strukturą, którą w nim zaprojektowano. W arkuszu wyceny definiuje się również formułę używaną do obliczania kosztu pośredniego. Formuła obliczania może być oparta na ilościach, wadze, objętości lub wartości.

-   **Definiowanie wersji wyceny.** W wersji wyceny firma określa, jak powinno się odbywać zarządzanie kosztem. Wersja wyceny może zawierać zestaw rekordów kosztów standardowych lub zestaw rekordów kosztów planowanych, w zależności od typu wyceny przypisanego do wersji wyceny. Wersja wyceny używana do wyceny w produkcji oszczędnej musi się opierać na koszcie standardowym.
-   **Przypisywanie grupy modeli zapasów dla zwolnionych produktów.** Wszystkie produkty związane z przepływem produkcji muszą być przypisane do grupy modeli zapasów o typie **Koszt standardowy**. Koszt standardowy jest zarządzany według oddziału i daty aktywacji. Dla produktów głównych grupę modeli zapasów można wybrać, gdy koszty jest zarządzany według wariantu lub produktu głównego.
-   **Z definicji usługi podwykonawcze są usługami nienależącymi do zapasów.** Działania podwykonawcze nie mają grupy modeli zapasów. Aby poprawnie wycenić działanie podwykonawcze, należy się upewnić, że działanie usługi należy do grupy modeli zapasów, która w zasadzie zapasów ma atrybut **Produkt magazynowany = Fałsz**.

W przypadku produktów wyjściowych obliczanie kosztów oparte na przepływie produkcji wymaga zdefiniowania kosztu standardowego dla usług związanych z działaniami podwykonawczymi. Grupa kosztów przypisana do usług służy do określania odchyleń kosztów w działaniu podwykonawczym.

## <a name="cost-calculation-for-lean-manufacturing"></a>Obliczanie kosztów w produkcji oszczędnej
W przypadku produktów dostarczanych z przepływu produkcji obliczanie BOM musi się opierać na wersji marszruty lub przepływie produkcji. W obliczaniu BOM są obliczane koszt produktu oraz pokrewny podział na zasoby i materiały niezbędne w celu wytworzenia produktu. Potrącenie z konta PWT dla przepływu produkcji jest wykonywane za pomocą podziału produktu według towarów i grup kosztów.

### <a name="calculation-that-is-based-on-the-production-flow"></a>Obliczanie oparte na przepływie produkcji

Lean manufacturing dla Dynamics 365 Supply Chain Management nie zależy od marszrut. Obliczanie kosztów dla produktów dostarczanych z przepływu produkcji może być oparte na samym przepływie produkcji. Zanim będzie możliwe obliczanie, należy utworzyć regułę Kanban dostarczającą produkt z przepływu produkcji. Jeśli produkt może być dostarczany z wielu przepływów produkcji w tym samym oddziale w dniu obliczania, można wybrać przepływ produkcji dla obliczania BOM. Na stronie **Domyślny przepływ produkcji** można skonfigurować domyślny przepływ produkcji dla każdego towaru. Jeśli istnieje wiele reguł Kanban dla tego samego produktu w przepływie produkcji aktywnym w dniu obliczania, aparat obliczania wybiera pierwszą regułę Kanban aktywną dla obliczenia.

### <a name="calculation-that-is-based-on-the-route"></a>Obliczanie oparte na marszrucie

Obliczanie oparte na marszrucie jest tak samo poprawne, jak obliczanie oparte na przepływie produkcji. Jednak w obliczaniu opartym na marszrucie nie jest używana funkcja wyceny w produkcji oszczędnej. Marszruta powinna wykorzystywać zapotrzebowania na zasoby dla grup zasobów. W celu uniknięcia systematycznych odchyleń należy również używać tych samych komórek roboczych lub przynajmniej tych samych kategorii kosztów. Tu również należy unikać stosowania kategorii kosztów dla konfiguracji i ilości. Nie umożliwiają one obliczania kosztu w bardziej szczegółowym podziale, niż wycena wsteczna kosztów w produkcji oszczędnej. Aby ustalić, której opcji (przepływu produkcji lub marszruty) należy użyć do obliczania kosztu, trzeba wziąć pod uwagę wyniki podziału kosztów. Lepszą opcją jest wersja bliższa rzeczywistości i ogólnie generująca mniej odchyleń. W środowisku produkcji oszczędnej, gdzie produkt jest dostarczany przez jeden przepływ produkcji i jedną regułę Kanban, prawdopodobnie dokładniejsze będzie obliczenie oparte na przepływie produkcji. Dla produktu, który może być dostarczany z produkcji oszczędnej i zleceń produkcyjnych w tym samym oddziale albo który może mieć wiele przepływów produkcji lub wiele reguł Kanban w tym samym przepływie, obliczenie może być dokładniejsze, jeśli bazuje na wersji marszruty utworzonej specjalnie dla obliczania kosztów, a nie dla produkcji. Obliczanie przepływu produkcji musi być używane do obliczania produktów obejmujących podwykonawstwo. Modele kosztów podwykonawstwa za pośrednictwem zleceń produkcyjnych i podwykonawstwa w lean manufacturing korzystają z dwóch różnych podejść. W produkcji oszczędnej wprowadzono nowy typ grupy kosztów **Outsourcing bezpośredni** przeznaczony do liczenia usług podwykonawczych.

## <a name="material-consumption"></a>Zużycie materiału
Gdy materiał jest zużywany z zapasów do PWT, koszt materiału jest dodawany do PWT według jego rzeczywistego kosztu standardowego dla grupy kosztów. Ta operacja odbywa się zgodnie z następującymi warunkami:

-   Wydania za pomocą kart Kanban są księgowane dla wierszy pobrania Kanban powodujących aktualizację magazynu.
-   Są wykonywane zadania przeniesienia, które aktualizują zapasy podczas pobrania, ale nie przyjęcia (przeniesienie materiału z zapasów do PWT).

## <a name="receiving-products-from-the-production-flow"></a>Przyjmowanie produktów z przepływu produkcji
Produkty są przyjmowane z przepływu produkcji zgodnie z następującymi warunkami:

-   Są wykonywane zadania przetwarzania z atrybutem **Aktualizuj zapasy po przyjęciu** ustawionym na **Tak**.
-   Są wykonywane zadania przeniesienia, które aktualizują zapasy na podstawie przyjęcia, ale mają atrybut **Aktualizuj zapasy po pobraniu** ustawiony na **Nie** (przeniesienie z PWT do zapasów). Ta opcja pozwala przyjmować dowolne produkty z przepływu produkcji niezależnie od konfiguracji BOM i marszruty. Proces naśladuje fizyczne przepływy. Ta opcja jest szczególnie przydatna do przyjmowania produktów ubocznych, produktów towarzyszących lub odpadków z przepływu produkcji oraz do odpowiedniego korygowania salda kosztów PWT przepływu produkcji.

Produkty przyjmowane z przepływu produkcji są odejmowane od PWT.

## <a name="products-in-wip"></a>Produkty w PWT
Model PWT lean manufacturing pozwala używać stanów jednostek załadunkowych w systemie Kanban do zarządzania materiałami, półproduktami i wyrobami gotowymi będącymi częścią PWT.

-   **Przypisano** — Karta Kanban może zawierać zużywany materiał, który jest wykazywany w PWT.
-   **Przyjęto** — Jeśli karta Kanban odnosi się do ostatniego działania, które ma atrybut **Aktualizuj zapasy po przyjęciu** ustawiony na **Nie**, reprezentuje pełną jednostkę załadunkową produktu lub półproduktu, który nie jest rejestrowany w zapasach.

Należy zauważyć, że materiał w PWT nie jest widoczny w przeglądach dostępnych zapasów. Jednak jest widoczna w przeglądach ilości na kartach Kanban.

## <a name="consuming-products-in-wip"></a>Zużywanie produktów w PWT
Produkty w PWT są zużywane podczas opróżniania odnośnych jednostek załadunkowych systemu Kanban. Sygnał pustej karty Kanban nie wywołuje aktywnej transakcji wyceny, ale jest brany pod uwagę podczas następnej sesji wyceny wstecznej. Opróżnione jednostki załadunkowe systemu Kanban nie są już są wykazywane jako dostępne zapasy i w efekcie są obliczane jako zużyte w okresie.

### <a name="automatic-empty-registration"></a>Automatyczna rejestracja pustych

Dla zaplanowanych zadań w systemie Kanban i kart Kanban zdarzeń można ustawić automatyczne rejestrowanie pustych w regule Kanban:

-   **Podczas odbierania magazynowych jednostek obsługi** — Domyślnie dla zaplanowanych zadań w systemie Kanban materiał jest deklarowany jako zużyty z chwilą ukończenia ostatniego zadania Kanban. Dla kart Kanban ze stałą ilością ta opcja jest zalecana tylko w przypadku kart Kanban przypisanych pojedynczym pojemnikom, ponieważ zwraca kartę do źródła popytu, gdy tylko karta Kanban jest odbierana w ostatecznym miejscu docelowym.
-   **Podczas rejestrowania wymagania źródłowego** — Ta opcja jest dostępna tylko dla kart Kanban zdarzeń i jest to dla nich opcja domyślna. W związku z PWT ta opcja jest przydatna do porządkowania PWT, ponieważ karty Kanban dla składników w PWT są automatycznie opróżniane, a zatem zużywane z PWT podczas przygotowywania nadrzędnej karty Kanban.

Podsumowując: jednostki załadunkowe w systemie Kanban można przypisywać (= w toku), przyjmować (= pełne) lub opróżniać. Nie ma możliwości częściowego opróżniania. Dlatego aby umożliwić dokładną rejestrację zużycia, ważne jest ograniczanie ilości produktów na kartach Kanban, tak aby były mniejsze niż zużycie w okresie. Produkty przenoszone do produkcji w dużych partiach, które mogą zaspokajać popyt na kilka dni lub tygodni, nie powinny być zużywane do PWT. Zamiast tego takie produkty powinny być utrzymywane w zapasach.

## <a name="backflush-costing"></a>Wycena wsteczna
Należy okresowo uruchamiać wycenę wsteczną, aby wyceniać wartość PWT i generować stan na koniec okresu, który oblicza odchylenia kosztów materiałów, robocizny i kosztów pośrednich. Obliczone odchylenia są księgowane na kontach odchyleń. W procesie wyceny wstecznej wszystkie przepływy produkcji firmy są umieszczane w tej samej sesji przetwarzania wsadowego. Gdy wycena wsteczna jest dokonywana wsadowo, przetwarzanie może być podzielone na wiele wątków według przepływów produkcji. Okres wyceny wstecznej jest definiowany przez datę końcową. Nie można zaksięgować nowych transakcji w dniu objętym wykonaną kalkulacją wyceny wstecznej. Nigdy nie należy uruchamiać wyceny wstecznej dla bieżącego dnia, ponieważ jeszcze się nie skończył. Wycena wsteczna powoduje wykonanie następujących czynności:

1.  Ustalenie niewykorzystanych ilości w przepływie produkcji na dzień zakończenia okresu. Po wykonaniu wyceny wstecznej można w oknie dialogowym **Niewykorzystane ilości** przejrzeć niewykorzystane ilości na dzień wykonania wyceny.
2.  Obliczenie zrealizowanego zużycia netto w przepływie produkcji w okresie.
3.  Wyczyszczenie PWT ze zrealizowanego zużycia zasobów i produktów.
4.  Obliczenie odchyleń produkcji względem kosztu standardowego w okresie. **Zużyte składniki w okresie:**
    -   Aktualizacja finansowa zrealizowanych ilości netto materiałów zużytych w przepływie produkcji w okresie. System przetwarza w porządku FIFO (pierwsze na wejściu, pierwsze na wyjściu) dla poszczególnych transakcji magazynowych w celu finansowego zaktualizowania fizycznie zaktualizowanych transakcji w przepływu produkcji, aż do osiągnięcia zrealizowanych ilości netto w okresie.
    -   Transakcje są finansowo dzielone w celu zamapowania dokładnie zużytych ilości.
    -   Niewykorzystane ilości w PWT przepływu produkcji pozostają w stanie fizycznie zaktualizowanym.

    **Ilości ukończonej produkcji w okresie:**
    -   Finansowe zaktualizowanie transakcji magazynowych dla ukończonych ilości w okresie.

    **Koszt konwersji:**
    -   Zastosowane transakcje kosztów konwersji (transakcji marszruty) zarejestrowane w okresie są aktualizowane finansowo.
    -   Wszystkie koszty produkcji bezpośredniej są aktualizowane finansowo. Wszystkie zadania przetwarzania w systemie Kanban wykonane w okresie są kumulowane.
    -   Wszystkie koszty pośrednie obliczone dla materiału zużytego w okresie są obliczane i odejmowane od PWT. Pozostały koszt pośredni jest księgowany jako odchylenie.

5.  Obliczenie odchyleń produkcji względem kosztu standardowego. Odchylenie jest obliczane dla każdej grupy kosztów.





