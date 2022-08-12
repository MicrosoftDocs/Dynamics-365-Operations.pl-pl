---
title: Wizualizacja i wykonanie pracy grupowej
description: W tym artykule opisano, jak monitorować punkty rozłączenia, strefy buforowe, planowane zamówienia i historię Planowania Zapotrzebowania materiałowego kierowanego popytem (DDMRP).
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: EcoResProductDetailsExtended, ReqDDMRPWorkspace, ReqDecouplingPointsStatusByNetFlow, ReqDecouplingPointStatusByOnHand, ReqPlannedOrderForm, ReqItemDecoupledLeadTime
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: e3afdd10860494b3cfe73a113a0e4e8fb07682a1
ms.sourcegitcommit: 529fc10074b06f4c4dc52f2b4dc1f159c36e8dbc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/22/2022
ms.locfileid: "9186707"
---
# <a name="visual-and-collaborative-execution"></a>Wizualizacja i wykonanie pracy grupowej

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

W tym artykule opisano, jak monitorować punkty rozłączenia, strefy buforowe, planowane zamówienia i historię Planowania Zapotrzebowania materiałowego kierowanego popytem (DDMRP).

## <a name="visually-track-buffers-and-quantities-for-a-selected-item"></a>Wizualne śledzenie buforów i ilości dla wybranego elementu

W Microsoft Dynamics 365 Supply Chain Management można wizualnie śledzić, jak zmieniają się w czasie bufory, ilości na stanie i poziomy przepływu netto dla dowolnego wybranego wydanego produktu. Wykonaj poniższe kroki, aby otworzyć i przejrzeć wykresy.

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Wybierz uwolniony element, który jest ustawiony jako punkt rozłączenia. (Aby uzyskać więcej informacji, zobacz [Pozycjonowanie zapasów](ddmrp-inventory-positioning.md)).
1. W okienku akcji otwórz kartę **Plan** i wybierz pozycję **Objęcie przedmiotu**.
1. Na stronie **Zapotrzebowanie na towary** wybierz rekord zapotrzebowania na towar, który powoduje utworzenie punktu dekodowania. (W tym rekordzie pojawi się nazwa grupy pokrycia, która została utworzona w celu utworzenia punktów rozłączenia).
1. Wybierz zakładkę **Dostępne**. Zakładka ta zawiera wykres, który pokazuje, jak zmieniały się ilości towaru w magazynie w czasie, a także wartość poziomu towaru w magazynie, który został zarejestrowany dla danego okresu przy każdym uruchomieniu optymalizacji planowania. Zakładka zawiera również tabelę, która pokazuje, do której z poniższych kategorii należy każdy zarejestrowany poziom na stanie:

    - **Krytycznie niska** — Mniej niż połowa minimum dla tego okresu.
    - **Niska** — Między połową minimum a minimum.
    - **Średnia ilość dostępna** – Pomiędzy minimum a minimum plus zielona strefa.
    - **Wyższe niż średnia** – wyższe niż średnia.

    ![Historyczne poziomy "dostępne" w zakładce "Dostępne".](media/ddmrp-on-hand-graph.png "Historyczne poziomy &quot;dostępne&quot; w zakładce &quot;Dostępne&quot;")

    > [!NOTE]
    > Kolory używane na karcie **Dostępne** zapasy reprezentują różne zakresy niż podobne kolory używane na karcie **Wartości buforowe**.

1. Aby wyświetlić zmiany wartości buforowych w czasie oraz porównanie z poziomami zapasów i przepływu netto, wybierz kartę **Wartości buforowe**.

    ![Historyczne poziomy przepływu na rękę i netto na karcie Wartości buforowe.](media/ddmrp-buffer-values-graph.png "Historyczne poziomy przepływu na rękę i netto na karcie Wartości buforowe")

## <a name="track-the-status-and-planned-orders-for-all-decoupling-points"></a>Śledź status i planowane zamówienia dla wszystkich punktów odłączania

Obszar roboczy **MRP zależne od popytu** zawiera kilka narzędzi, a także kluczowe wskaźniki wydajności (KPI) oraz przeglądy stanu pozycji punktu rozłącznego i związanych z nimi planowanych zamówień. Aby go otworzyć, przejdź do usługi **Planowanie główne \> Obszary robocze \> MRP sterowane zapotrzebowaniem**.

![Obszar roboczy MRP oparte na popycie.](media/ddmrp-workspace.png "Obszar roboczy MRP oparte na popycie")

## <a name="get-overviews-of-decoupling-points-and-planned-orders"></a>Uzyskaj przegląd punktów rozłączenia i planowanych zleceń

Oprócz obszaru roboczego **MRP oparte na popycie**, Supply Chain Management udostępnia kilka stron, na których można zobaczyć informacje o konfiguracji DDMRP, punktach odłączenia i planowanych zamówieniach. Niektóre z tych stron mają również wygodne przyciski na panelu akcji, które pozwalają zarządzać buforami, uruchamiać planowanie główne i otwierać inne powiązane widoki.

- Aby zobaczyć status punktów sprzężenia według poziomu przepływu netto, przejdź do strony **Planowanie główne \> Planowanie główne \> DDMRP \> Status punktów sprzężenia według przepływu netto**.
- Aby wyświetlić status punktów rozdzielania według stanu zapasów na stanie, przejdź do strony **Planowanie główne \> Planowanie główne \> DDMRP \> Status punktów rozdzielania według stanu na stanie**.
- Aby wyświetlić planowane zamówienia dla punktów odłączenia, przejdź do strony **Planowanie główne \> Planowanie główne \> DDMRP \> Planowane zamówienia dla punktów odłączenia**.
- Aby wyświetlić czasy realizacji w trybie rozłącznym, przejdź do strony **Planowanie główne \> Planowanie główne \> DDMRP \> Czas realizacji w trybie rozłącznym**.

## <a name="clean-up-decoupling-point-buffer-values"></a>Wyczyść wartości bufora punktu odłączania

Z czasem twój system zgromadzi dużą ilość danych historycznych związanych z bieżącymi obliczeniami buforów. Te dane historyczne spowodują wzrost objętości danych i mogą wpłynąć na wydajność systemu. Dlatego zalecamy, abyś od czasu do czasu czyścił stare wartości bufora punktu odłączania.

> [!WARNING]
> Uruchomienie tego zadania spowoduje usunięcie historycznych ustawień wartości bufora oraz historycznych informacji dotyczących przepływu dostępnych zapasów/netto. Tej zmiany nie można wycofać.

Wykonaj poniższe kroki, aby wyczyścić wartości bufora punktu odłączenia.

1. Przejdź do **Planowanie główne \> Planowanie główne \> DDMRP \> Wyczyść wartości bufora punktu odłączenia**.
1. W oknie dialogowym **Wyczyść wartości bufora punktu odłączenia** ustaw następujące pola:

    - **Usuń rekordy starsze niż (dni)** - Określ wiek najmłodszych rekordów, które mają być zachowane, w dniach. Wszystkie starsze niż ta wartość rekordy wartości buforu punktów oczyszczania zostaną usunięte.
    - **Plan główny** — Wybierz plan główny, który zawiera elementy, których powinno dotyczyć oczyszczanie. Czyszczenie będzie dotyczyło wszystkich elementów planu po zastosowaniu ustawień **Filtra**, które określisz w tym oknie dialogowym.

1. Aby ograniczyć zestaw rekordów, na których ma być uruchomione to zadanie wsadowe, na karcie **Rekordy do uwzględnienia** wybierz **Filtr**, aby otworzyć okno dialogowe **Zapytanie**. To okno dialogowe działa tak samo jak w przypadku innych typów [zadań w tle](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) w Supply Chain Management.
1. Na skróconej karcie **Uruchom w tle** określ sposób, kiedy i jak często powinno być wykonywane oczyszczanie. Pola działają w ten sam sposób, jak działają w przypadku innych typów [zadań w tle](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) w module Supply Chain Management.
1. Wybierz **OK**, aby dodać nowe zadanie do kolejki zadań do wykonania.
