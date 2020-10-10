---
title: Zaplanuj zlecenia pracy
description: W tym temacie opisano planowanie zleceń pracy w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderSchdulePreviewPart, EntAssetWorkOrderScheduleExclusively, EntAssetWorkOrderSchduleInfoPart, EntAssetWorkOrderScheduleListPage, EntAssetWorkOrderSchedule, EntAssetWorkOrderScheduleDelete
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 095ff2697a7cc8486afc6e77fd7d06f761e74e75
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/25/2020
ms.locfileid: "3888912"
---
# <a name="schedule-work-orders"></a>Zaplanuj zlecenia pracy

[!include [banner](../../includes/banner.md)]

 

W tym temacie opisano planowanie zleceń pracy w module Zarządzanie składnikami majątku. 

Wymagana liczba godzin dla zlecenia pracy jest definiowana przez sumę prognozowanych godzin pomniejszoną o zaksięgowane godziny. Jeśli jest wymagane więcej czasu, prognoza musi zostać odpowiednio skorygowana. W **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy** można wyświetlać lub edytować prognozy w zleceniu, wybierając zlecenie pracy i klikając przycisk **Prognoza** na karcie **Zlecenie pracy**. Jeśli zostały utworzone i oszacowane zlecenia pracy, następny krok do wykonania zleceń pracy polega na przydzieleniu wymaganych pracowników i narzędzi konserwacyjnych.

Można planować tylko w przypadku zleceń pracy o stanie cyklu życia, który umożliwia planowanie. Zezwalaj na planowanie w **Zarządzanie składnikami majątku** > **Ustawienia** > **Zlecenia pracy** > **Stany cyklu życia** > **Ogólne** skrócona karta > **Zezwalaj na planowanie** przycisk przełączania.

1. Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy**.

2. Wybierz zlecenia pracy, które chcesz zaplanować. Na przykład, listę można posortować według **Bieżący stan cyklu życia**.

3. Na karcie **Ogólne** kliknij przycisk **Zaplanuj**.

4. W oknie dialogowym **Planowanie zlecenia pracy** można dodawać wybory dotyczące oczekiwanej daty rozpoczęcia i poziomu usług (jeśli jest to wymagane). Jeśli proces planowania powinien uwzględniać ograniczenia zdolności produkcyjnych dotyczące zasobów, które są już zaplanowane dla innych zadań, należy upewnić się, że przyciski przełączania **Składnik majątku**, **Narzędzie** i **Pracownik** są ustawione na wartość „Tak”.

    [!NOTE]
    W przypadku ustawienia przycisków **Składnik majątku**, **Narzędzie** i **Pracownik** na wartość „Nie", zostaną zignorowane istniejące rezerwacje. W dzienniku informacyjnym zostanie wyświetlona lista nakładających się harmonogramów zleceń pracy, a w razie potrzeby można kliknąć opcję, aby otworzyć zlecenie pracy i ponownie zaplanować.

5. Aby wyświetlić szczegółowe informacje o procesie planowania, wybierz wartość „tak” w przycisku przełączania **Pełne**. Oznacza to, że w dzienniku informacyjnym zostaną wyświetlone szczegółowe informacje o obliczonych wynikach zlecenia pracy i pracowników konserwacji.

6. Kliknij przycisk **OK**, aby rozpocząć proces planowania.

7. Po zakończeniu planowania w dzienniku informacyjnym zostanie wyświetlona liczba zaplanowanych zleceń pracy, a także bardziej szczegółowe informacje, jeśli dla przycisku przełącznika **Pełne** ustawiono wartość „tak”.

>[!NOTE]
>Zlecenia pracy są planowane w jednym cyklu dla zlecenia pracy, a nie na zadanie zlecenia pracy. Można również otworzyć okno dialogowe **Planowanie zlecenia pracy** bezpośrednio w **Zarządzanie składnikami majątku** > **Okresowe** > **Zlecenia pracy** > **Planowanie zlecenia pracy**. Wybierz odpowiednie opcje i kliknij **OK**, aby rozpocząć planowanie zleceń pracy. Planowanie zleceń pracy można skonfigurować jako zadanie wsadowe w oknie dialogowym **Planowanie zleceń pracy** > karta skrócona **Uruchom w tle**.

*Przykład:* na poniższym rysunku formuła wstawiona w **Oczekiwane rozpoczęcie** będzie generować Planowanie zleceń pracy dla wszystkich zleceń pracy z oczekiwaną datą rozpoczęcia w tygodniu od teraz do później. Ta formuła może być przydatna w przypadku regularnego uruchamiania planowania zlecenia pracy, ale należy się upewnić, że zlecenia pracy zaplanowane na następne 5-6 dni nie zostaną ponownie zaplanowane.

![Rysunek 1](media/03-work-order-scheduling.png)

Typ zlecenia pracy powiązanego ze zleceniami pracy może skonfigurować planowanie dla jednego konserwatora (**Zarządzanie składnikami majątku** > **Ustawienia** > **Zlecenia pracy** > **Typy zleceń pracy** > **Jeden konserwator** przycisk przełączania jest ustawiony na wartość „tak”). Oznacza to, że jeśli typ zlecenia pracy jest używany w zleceniu pracy przycisk przełączania **Jeden konserwator** jest automatycznie ustawiany na wartość „tak” na stronie szczegółowej **wszystkie zlecenia pracy** > w widoku **Nagłowek** > skrócona kart **Zaplanuj**. Podczas planowania zleceń pracy wszystkie zadania zlecenia pracy utworzone w zleceniu pracy będą następnie planowane dla tego samego konserwatora. W razie potrzeby można edytować zaznaczenie na przycisku przełączania **Jeden konserwator** w **Wszystkie zlecenia pracy**, aby umożliwić planowanie kilku pracowników lub jednego pracownika w zadaniach zlecenia.

Proces planowania w module Zarządzanie składnikami majątku obejmuje kilka czynników w obliczeniu planowania:

- Obliczanie wyników dla zleceń i pracowników konserwacji. Wyniki dla pracowników obsługi zleceń i czynności konserwacyjnych są ustawiane w **Parametry zarządzania składnikami majątku**. 
- Sprawdzanie, czy są odpowiednie kwalifikacje, czyli kwalifikacje i certyfikaty wymagane do wykonania zadania. Umiejętności i certyfikaty są ustawiane dla pracowników obsługi technicznej w module **zasoby ludzkie** (**Zasoby ludzkie** > **Pracownicy** > **Pracownicy** > wybierz pracownika na liście > karta **Pracownicy** > sekcja **Kompetencje** > przyciski **Umiejętności** i **Certyfikaty**). Ponadto można dodawać kwalifikacje i certyfikaty do typów zadań serwisowych i branży zadań konserwacji. Przeczytaj więcej o kompetencjach i typach prac konserwacyjnych w [Kategorie typów zadań obsługi i typy zadań serwisowych, warianty typu zadań obsługi, handel zadaniami konserwacyjnymi oraz listy kontrolne konserwacji](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).  

## <a name="scores-used-in-work-order-scheduling"></a>Wyniki używane w planowaniu zleceń pracy

Obliczanie wyników zadania zlecenia zależy od oczekiwanej daty rozpoczęcia i poziomu usług zlecenia produkcyjnego.

Obliczanie **daty rozpoczęcia**: w przypadku każdej przyszłej daty obliczonej od oczekiwanej daty początkowej wynik jest odejmowany i mnożony przez wynik, który wynosi „10” w poniższych przykładach.

Obliczanie **krytyczności**: wynik krytyczności pomnożony przez krytyczną wartość w zleceniu produkcyjnym.

**Obliczanie poziomu usług**: wyniki poziomu usług podzielone przez poziom usług w zleceniu produkcyjnym.

W poniższych przykładach wynik krytyczny wynosi „2”, a wyniki poziomu usług to „5” i „100”.

**Przykład 1:**

| Identyfikator zlecenia pracy | Oczekiwana data rozpoczęcia | Krytyczność zlecenia pracy | Poziom usługi zlecenia pracy | Obliczenie               | Punktacja      |
|---------------|---------------------|------------------------|--------------------------|---------------------------|------------|
| WO-00010816   | Jutro            | 2                      | 20              | (-1 \* 10) + (2 \* 2) + 5 / 20     | \- 5.75    |
| WO-00010817   | Dwa dni od teraz   | 2                      | 20              | (-2 \* 10) + (2 \* 2) + 5 / 20     | \- 15.75   |
| WO-00010818   | Dwa dni od teraz   | 3                      | 5               | (-2 \* 10) + (2 \* 3) + 5 / 5      | \- 13      |

Zlecenia pracy będą planowane w następującej kolejności: WO-000108**16**, WO-000108**18**, WO-000108**17**.

**Przykład 2:**

| Identyfikator zlecenia pracy | Oczekiwana data rozpoczęcia | Krytyczność zlecenia pracy | Poziom usługi zlecenia pracy | Obliczenie                 | Punktacja    |
|---------------|---------------------|------------------------|---------------------|----------------------------------|----------|
| WO-00010816   | Jutro            | 2                      | 20                  | (-1 \* 10) + (2 \* 2) + 100 / 20 | \- 1     |
| WO-00010817   | Dwa dni od teraz   | 2                      | 20                  | (-2 \* 10) + (2 \* 2) + 100 / 20 | \- 11    |
| WO-00010818   | Dwa dni od teraz   | 3                      | 5                   | (-2 \* 10) + (2 \* 3) + 100 / 5  | 6        |

Jeśli wynik poziomu usług jest zwiększany do wartości „100” zamiast „5”, zlecenie planowane będzie na:WO-000108**18**, WO-000108**16**, WO-000108**17**.

Wyniki oceny dotyczące obliczania, które pracownicy obsługi powinni pracować w zleceniach pracy, są ustawiane jako numery, które są dodawane do każdego obliczenia pracownika obsługi podczas planowania zlecenia pracy. Pracownik obsługi z najwyższym wynikiem jest wybrany w zleceniu pracy. Poniżej znajduje się krótki opis wyników pracownika konserwacji:

| Wynik konserwatora| Opis |
|---|---|
| Odpowiedzialny pracownik | Jeśli pracownik konserwacji został wybrany jako pracownik odpowiedzialny za zlecenie pracy, zostanie dodana Punktacja. |
| Odpowiedzialna grupa konserwatorów | Jeśli pracownik konserwacji jest częścią grupy konerwatorów odpowiedzialnych za zlecenie pracy, zostanie dodana Punktacja. |
| Preferowany konserwator         | Jeśli pracownik konserwacji został wybrany jako pracownik preferowany za składnik majątku, zostanie dodana Punktacja. |
| Grupa preferowanych konserwatorów   | Jeśli pracownik konserwacji został wybrany jako część grupy konserwatorów preferowanych za składnik majątku, zostanie dodana Punktacja.  |
| Lokalizacja  | Jeśli firma korzysta z lokalizacji czynności konserwacyjnych, konserwatorzy otrzymują pełną punktację, jeśli znajdują się w lokalizacji czynności konserwacyjnych związanej z składnikiem majątku. Jeśli funkcjonalna czynności konserwacyjnych składnika majątku ma nadrzędną lokalizację, pracownicy w tej lokalizacji czynności konserwacyjnych otrzymują 1/2 wyniku. Jeśli ta lokalizacja ma również element nadrzędny, konserwatorzy w tej lokalizacji otrzymują 1/3 wyniku itd. Jeśli ta lokalizacja ma również element nadrzędny, konserwatorzy w tej lokalizacji otrzymują 1/4 wyniku itd. Jeśli Twoja firma korzysta z lokalizacji składnika majątku, której nie zalecamy, lokalizacja, obszar i strefa są używane do obliczania wyników lokalizacji. Pracownicy otrzymują pełny wynik, jeśli znajdują się w lokalizacji i obszarze oraz strefie związanych ze składnikiem majątku. Jeśli lokalizacja pracownika jest zgodna tylko z lokalizacją i obszarem, wynik oceny dla konserwatora wynosi 2/3 pełnego wyniku. Jeśli lokalizacja konserwatora jest zgodna tylko z lokalizacją i obszarem, wynik oceny dla konserwatora wynosi 1/3 pełnego wyniku. |
| Data rozpoczęcia pracownika  | Dla każdego dnia, w którym planowana data rozpoczęcia jest późniejsza niż oczekiwana data rozpoczęcia, wynik jest odejmowany.  |

>[!NOTE]
>Jeśli wynik jest określony jako „0”, ten wynik nie jest obliczany. Jest to przydatne, jeśli na przykład nie chcesz dołączać odpowiedzialnego pracownika w planowaniu.

## <a name="competencies-used-in-work-order-scheduling"></a>Kompetencje używane w planowaniu zleceń pracy

W przypadku zadań konserwacyjnych można skonfigurować wymagania dotyczące typów zadań konserwacji (**Zarządzanie składnikami majątku** > **Ustawienia** > **Zadania** > **Typy zadań konserwacji**) i typy zawodów konserwacji (**Zarządzanie składnikami majątku** > **Ustawienia** > **Zadania** > **Zawody zadań konserwacji**). 

Typy zadań konserwacji i zawody zadań konserwacji są wybierane w zadaniach zleceń pracy. Jeśli kwalifikacje lub certyfikaty zostały wybrane w ramach zadania obsługi typu lub w rodzaju pracy związanej z konserwacją, a w zamówieniu pracy jest używany typ zadania konserwacji lub zawód konserwatora, to pracownicy obsługi technicznej z dopasowanymi umiejętnościami i certyfikatami są planowani na pracę nad zlecenia pracy.

<a name="gantt"></a>

## <a name="work-with-scheduled-work-orders-using-a-gantt-chart"></a>Praca z zaplanowanymi zleceniami roboczymi za pomocą wykresu Gantta

**Wykres Gantta zaplanowanych zleceń pracy** zawiera graficzny interfejs, w którym można przeglądać i ponownie planować zlecenia pracy.

Aby wyświetlić wykres Gantta i pracować z nim, należy:

1. Przejdź do **Zarządzanie składnikami majątku > Zlecenia pracy > Wykres Gantta zaplanowanych zleceń pracy**.

1. Korzystając z list rozwijanych i pól w sekcji **Ustawienia**, można określić, która lokalizacja czynności konserwacyjnych, zakres czasu i skala czasu mają być pokazywane na wykresie Gantta.

1. Wybierz opcję **Zastosuj**.

    - Aktualizacja wykresu Gantta powoduje wyświetlenie zaplanowanych zleceń pracy spełniających Twoje ustawienia. Każde zlecenie jest reprezentowane przez niebieski prostokąt.
    - Aby ponownie zaplanować wyświetlone zlecenie pracy, zaznacz opcję i przeciągnij je do odpowiedniej nowej daty i godziny.

1. W przypadku wprowadzenia jakichkolwiek zmian wybierz opcję **Zapisz** w okienku akcji, aby je zapisać.
