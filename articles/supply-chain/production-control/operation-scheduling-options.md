---
title: Opcje planowania operacji
description: W tym artykule opisano opcje planowania operacji. Funkcji planowania operacji można używać, aby przedstawić ogólne oszacowanie procesu produkcji w wybranym okresie.
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdSchedule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 198123
ms.assetid: d680d7be-da64-4132-89fe-ad2fa59afb77
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d2f4d1e74855a0a8f73030c222c3f2fe27ce58a2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907269"
---
# <a name="operations-scheduling-options"></a>Opcje planowania operacji

[!include [banner](../includes/banner.md)]

W tym artykule opisano opcje planowania operacji. Funkcji planowania operacji można używać, aby przedstawić ogólne oszacowanie procesu produkcji w wybranym okresie.

Funkcja planowania operacji oblicza dla zlecenia produkcyjnego następujące informacje:

-   Daty rozpoczęcia i zakończenia są ustawiane dla zlecenia produkcyjnego i każdej operacji.
-   Zasoby są przypisywane do operacji.

Różne ustawienia określają sposób obliczania harmonogramów produkcji. Te ustawienia definiuje się na stronie **Planowanie operacji**. Poniżej opisano dostępne opcje planowania.

## <a name="operations-scheduling"></a>Planowanie operacji
### <a name="scheduling-direction"></a>Kierunek planowania

Kierunek ma zasadnicze znaczenie w procesie planowania. Produkcję można planować w przód lub wstecz od dowolnej daty, zależnie od wymagań w zakresie synchronizacji i planowania.

-   **Planowanie w przód** — Można zaplanować rozpoczęcie produkcji jak najszybciej. Produkcja może się rozpocząć dziś, jutro lub dowolnego określonego dnia w przyszłości. Rozpoczęcie produkcji jest planowane na najbliższy możliwy dzień, a produkcja jest tak planowana w czasie, aby zakończyła się w możliwie najbliższym terminie.
-   **Planowanie wstecz** — Można zaplanować rozpoczęcie produkcji jak najpóźniej. Harmonogram jest oparty na terminie, w którym produkcja musi zostać zakończona, i następuje odliczanie w tył do możliwie najpóźniejszej daty rozpoczęcia produkcji, tak aby ten termin został dotrzymany.

Dostępne są następujące opcje:

-   **W przód od dzisiaj** — Planowanie w przód od daty bieżącej. (Data bieżąca to data systemowa).
-   **W przód od planowanego rozpoczęcia** — Planowanie w przód od poprzedniej daty rozpoczęcia. Jeśli planowanie nie było wcześniej przeprowadzane, planowanie odbywa się do przodu od bieżącej daty.
-   **W przód od daty planowania** — Planowanie w przód od daty określonej w polu **Data planowania**. Jeśli nie określisz daty planowania, planowanie odbywa się do przodu od bieżącej daty.
-   **Wstecz od daty dostawy** — Planowanie wstecz od daty dostawy określonej w zleceniu produkcyjnym. Jeśli data dostawy nie została określona, po wybraniu tej opcji datą dostawy będzie data bieżąca.
-   **Wstecz od planowanego zakończenia** — Planowanie wstecz od poprzednio obliczonej daty zakończenia. Jeśli planowanie nie było wcześniej przeprowadzane, datą zakończenia jest bieżąca data.
-   **Wstecz od daty planowania** — Planowanie wstecz od daty określonej w polu **Data planowania**. Jeśli data planowania nie zostanie określona, będzie używana data bieżąca. Planowanie wstecz od daty planowania jest obliczane dla zlecenia produkcyjnego podczas ostatniego obliczania wartości zapotrzebowania. Jeśli dla zlecenia produkcyjnego nie zostanie określona data, będzie używana bieżąca data systemowa.
-   **Wstecz od daty prognozy** — Planowanie wstecz od daty prognozy obliczonej dla zlecenia produkcyjnego podczas ostatniego obliczania wartości zapotrzebowania. Jeśli dla zlecenia produkcyjnego nie zostanie określona data prognozy, będzie używana bieżąca data systemowa.
-   **Zaplanowana jako ostatnia** — Wybrana data i kierunek planowania są zapisywane na potrzeby planowania operacji i planowania zadań. W związku z tym opcję można wybrać dla kolejnego planowania. Jeśli zlecenie produkcyjne nie było wcześniej planowane, planowanie przebiega wstecz od bieżącej daty systemowej.
-   **W przód od jutra** — Planowanie w przód od dnia następującego po dacie bieżącej.
-   **W przód od poprzedniego zadania** — Ta funkcja jest stosowana tylko w przypadku planowania zadań. Po wybraniu tej opcji na potrzeby planowania operacji zlecenie produkcyjne jest planowane w przód od daty bieżącej. W przypadku planowania zadań planowanie dotyczy jednego zadania, a wszystkie inne zadania dotyczące produkcji są planowane na podstawie tego zadania.
-   **Wstecz od poprzedniego zadania** — Ta opcja jest stosowana tylko w przypadku planowania zadań. Po wybraniu tej opcji dla planowania operacji zlecenia są planowane wstecz od daty bieżącej. W przypadku planowania zadań planowanie dotyczy jednego zadania, a wszystkie inne zadania dotyczące produkcji są planowane na podstawie tego zadania.

### <a name="scheduling-date"></a>Data planowania

Ta data jest używana dla kierunków planowania **W przód od daty planowania** i **Wstecz od daty planowania**. Planowanie odbywa się wstecz lub w przód od tej daty. Aby uzyskać więcej informacji, zobacz poprzedni punkt „Kierunek planowania”.

### <a name="recalculate-bom-levels"></a>Przeliczanie poziomów BOM

Po wybraniu opcji **Przeliczanie poziomów BOM** poziomy wybranej listy składowej (BOM) zostaną obliczone ponownie w celu zagwarantowania odpowiedniej kolejności planowania.

## <a name="limitations"></a>Ograniczenia
### <a name="finite-capacity"></a>Ograniczone zdolności produkcyjne

Planowanie zależy od dostępności zasobów wymaganych do realizacji produkcji. Jeśli brakuje wystarczających zdolności produkcyjnych, może dojść do opóźnienia, a nawet zatrzymania wypełniania zleceń produkcyjnych. Jeżeli do operacji planowania są stosowane ograniczone zdolności produkcyjne, pod uwagę są brane istniejące rezerwacje zdolności produkcyjnych dokonane dla zasobów i te zdolności są wyświetlane jako niedostępne. Zlecenie produkcyjne jest planowanie na podstawie dostępności zdolności produkcyjnych wymaganych zasobów. Funkcja planowania operacji wykorzystuje podaną kolejność operacji w celu określania porządku operacji w marszrucie produkcji. Planowanie operacji powoduje rezerwowanie zdolności produkcyjnych w grupie zasobów na podstawie czasów trwania operacji zdefiniowanych w marszrucie produkcji. Zdolności produkcyjne grupy zasobów są sumą dostępnych zdolności produkcyjnych wszystkich zasobów należących do grupy.

### <a name="finite-material"></a>Ograniczone materiały

Planowanie zależy również od dostępności materiałów wymaganych do produkcji. Niewystarczająca dostępność składników może prowadzić do opóźnień w produkcji. Planowanie może się również opierać na użyciu materiałów. Wystarczy określić materiały, które muszą być dostępne do produkcji, zamiast materiałów, które nie są newralgiczne. Ten typ planowania nosi nazwę planowania z ograniczonymi materiałami. Po określeniu ograniczonych materiałów produkcja jest planowana na podstawie tego, czy materiały są dostępne. **Uwaga:** Gdy optymalizacja odbywa się zarówno według zdolności produkcyjnych, jak i według materiałów, produkcja jest obliczana tak, aby spełniała oba ograniczenia. Pod uwagę jest brana dostępność zdolności produkcyjnych i materiałów, a rozpoczynanie operacji zlecenia produkcyjnego można zaplanować dopiero na moment, gdy zdolności produkcyjne i materiały są dostępne w tym samym czasie i w wymaganych ilościach. Zaznacz to pole wyboru, jeśli podczas planowania materiały powinny być uznawane za ograniczone. Jeśli materiały są ograniczone, uwzględniane będzie zapotrzebowanie na materiały dla wybranego okresu. Oznacza to, że planowanie uwzględnia daty prognoz obliczane dla towarów. Podczas planowania następuje rezerwacja surowców oraz rozłożenie bieżącej produkcji. W przypadku kilku procesów planowania tylko podczas pierwszego z nich uruchamiane jest rozłożenie i tworzone są rezerwacje. W przypadku wprowadzenia zmian w BOM produkcji lub marszrucie produkcji rozłożenie zostaje uruchomione podczas następnego planowania. Rozkładanie jest przeprowadzane przy założeniu, że materiały są wymagane w tym samym dniu. Ze względu na to, że produkcja nie jest planowana podczas rozkładania planu głównego, najdokładniej oszacowaną datą dostępności towarów będzie data bieżąca. Następnie w ramach rozkładania następuje sprawdzenie, czy towary są dostępne. Jeśli towary są dostępne, można zaspokoić zapotrzebowanie produkcji. Jeśli w bieżącym dniu towary nie są dostępne, generowane jest planowane zamówienie, a następnie wybierane jest przesunięcie dla tego zamówienia. Jeśli dla planowanego zamówienia wybrano opcję automatycznego akceptowania, zostanie ono automatycznie zaakceptowane na potrzeby zakupu lub produkcji. Stan produkcji zmienia się automatycznie na stan określony w polu **Wymagany stan produkcji** w oknie dialogowym **Grupy zapotrzebowania**. Jeśli pole wyboru zostało wyczyszczone, materiały są zawsze traktowane jako dostępne. Dlatego w planowaniu nie jest brane pod uwagę to, czy materiały są dostępne w czasie zapotrzebowania.

### <a name="finite-property"></a>Ograniczone właściwości

Zaznacz to pole wyboru, jeśli planowanie zadań ma uwzględniać wymagania dotyczące właściwości.

### <a name="keep-production-unit"></a>Zachowaj jednostkę produkcyjną

Określ, czy aparat planowania ma planować tylko zasoby, które już są określone w jednostce produkcyjnej.

### <a name="keep-warehouse-from-resource"></a>Zachowaj magazyn z zasobu

Określ, czy aparat planowania ma planować tylko zasoby, które są skojarzone z magazynem wejściowym określonym w zasobie.

## <a name="references"></a>Odwołania
### <a name="schedule-references"></a>Odwołania do planu

Jeżeli odwołania są zależne od zleceń produkcyjnych, są nazywane produkcjami podrzędnymi. Produkcje podrzędne można planować w ramach planowania zlecenia produkcyjnego. Zaznacz to pole wyboru, jeśli planowanie produkcji podrzędnych ma być oparte na planowaniu produkcji głównej. Względem produkcji głównej produkcje nadrzędne są planowane w przód, a produkcje podrzędne — wstecz. Odwołania do zlecenia produkcyjnego można wyświetlić w polu **Poziom odwołania** na stronie **Zlecenia produkcyjne**.

### <a name="synchronize-references"></a>Synchronizacja odwołań

Odwołania można zsynchronizować ze zleceniem produkcyjnym. Jeśli ta opcja jest wybrana, zmiany harmonogramu zlecenia produkcyjnego powodują przesunięcie i dopasowanie dat produkcji podrzędnych. Jeżeli zlecenie produkcyjne ma co najmniej jedną produkcję podrzędną, warto zaplanować te produkcje podrzędne razem z produkcją główną. W takim przypadku produkcję główną będzie można rozpocząć dopiero po zakończeniu powiązanych produkcji podrzędnych. W związku z tym zaznacz to pole wyboru, jeśli planowanie produkcji podrzędnych ma być oparte na godzinach rozpoczęcia i zakończenia wybranej produkcji. To pole wyboru można zaznaczyć tylko wtedy, gdy jest również zaznaczone pole wyboru **Odwołania do planu**.

## <a name="cancellation"></a>Anulowanie
### <a name="cancel-queue-time"></a>Anulowanie czasu oczekiwania

Zaznacz to pole wyboru, aby wykluczyć czas oczekiwania z planowania.

### <a name="cancel-setup"></a>Anulowanie czasu przezbrajania

Zaznacz to pole wyboru, aby wykluczyć czas przezbrajania z planowania.

### <a name="cancel-process"></a>Anulowanie czasu procesu

Zaznacz to pole wyboru, aby wykluczyć czas procesu z planowania.

### <a name="cancel-overlap"></a>Anulowanie nakładania

Zaznacz to pole wyboru, aby wykluczyć czas nakładania z planowania.

### <a name="cancel-transport"></a>Anulowanie transportu

Zaznacz to pole wyboru, aby wykluczyć czas w drodze z planowania.

## <a name="set-default"></a>Ustaw domyślne
Bieżące wartości można zapisać jako domyślne. Dostępne są dwie opcje:

-   Ustaw jako moje domyślne
-   Ustaw jako domyślne dla wszystkich


## <a name="additional-resources"></a>Dodatkowe zasoby

[Planowanie operacji](operations-scheduling.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]