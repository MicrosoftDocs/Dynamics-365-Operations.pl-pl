---
title: "Planowanie główne — strona główna"
description: "Planowanie główne umożliwia firmom określanie i bilansowanie przyszłego zapotrzebowania na surowce i zdolności produkcyjne do realizacji celów firmy."
author: YuyuScheller
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 18ed011fa1c1aa35b4a401d51bffc6af19395577
ms.openlocfilehash: 030579ac73d6333ac4ed55433b9679a58247c088
ms.contentlocale: pl-pl
ms.lasthandoff: 02/13/2018

---

# <a name="master-planning-home-page"></a>Planowanie główne — strona główna

[!include [banner](../includes/banner.md)]

Zgodnie z zamysłem planowanie główne umożliwia firmom określanie i bilansowanie przyszłego zapotrzebowania na surowce i zdolności produkcyjne do realizacji celów firmy. Funkcja planowania głównego przeprowadza ocenę następujących elementów: 

-  Jakie surowce i zdolności produkcyjne są obecnie dostępne? 
-  Jakie surowce i zdolności produkcyjne są wymagane do realizacji produkcji? Na przykład, co trzeba wyprodukować, zakupić, przenieść lub odłożyć jako zapas bezpieczeństwa przed ukończeniem produkcji.

Planowanie główne wykorzystuje te informacje do obliczania wymagań i generowania zaplanowanych zamówień.

Dostępne są trzy główne procesy planowania:

-  **Planowanie główne** — plan główny oblicza zapotrzebowania netto. Jest on oparty na rzeczywistych bieżących zamówieniach i umożliwia firmom kontrolowanie uzupełniania zapasów w perspektywie krótkoterminowej, z dnia na dzień. Jest on określany również mianem *planu zapotrzebowania netto*. Aby uzyskać więcej informacji, zobacz [Planowanie główne](master-plans.md). 

-  **Planowanie prognozy** — harmonogram prognozy oblicza zapotrzebowania brutto. Jest on oparty na przyszłych prognozach i umożliwia firmom długoterminowe planowanie materiałów i zdolności produkcyjnych. Aby uzyskać więcej informacji, zobacz [Planowanie prognozy](introduction-demand-forecasting.md). 

-  **Międzyfirmowe planowanie główne** — międzyfirmowy plan główny oblicza zapotrzebowania netto w różnych podmiotach prawnych. Łączy on popyt i dostawy między firmami nie tylko w perspektywie krótkoterminowego, ustalonego popytu i dostaw, ale także w perspektywie długoterminowej, zaplanowanej (jeszcze bez ustaleń). Aby uzyskać więcej informacji, zobacz [Międzyfirmowe planowanie główne](https://mbspartner.microsoft.com/AX/CourseOverview/1276) (szkolenie elektroniczne) (wymagane konto CustomerSource). 

Firmy mogą zmieniać kształt wyjściowy planu. Mogą działać w trybie odtwórczym, zmiany netto lub jednym i drugim. Plany odtwórcze aktualizują wszystkie zapotrzebowania, natomiast plany oparte na zmianie netto aktualizują plan wyłącznie w pozycjach, przy których od ostatniego planowania pojawiły się nowe zapotrzebowania.

Plany tworzone za pomocą funkcji planowania głównego obejmują krótki okres czasu, który może wynosić od jednego tygodnia do sześciu miesięcy. Moduł planowania głównego określa zapotrzebowania na dostawy (materiałów) i zdolności produkcyjne (zasoby), które będą w stanie pokryć bieżące zapotrzebowanie (zapotrzebowania netto). W większości firm okres ten jest rozszerzony tak, aby uwzględniał najdłuższy łączny czas realizacji wśród produktów do odbioru.

## <a name="learning-map"></a>Mapa szkoleń

Poniższa mapa szkoleniowa przedstawia najważniejsze koncepcje i zadania tworzące strukturę modułu planowania głównego. Kliknij łącza w sekcji [Szybkie łącza](#quick-links), aby dowiedzieć się, jak używać tego modułu.

[![Mapa szkoleniowa planowania głównego](./media/master-planning-learning-map.png)](./media/master-planning-learning-map.png)

## <a name="quick-links"></a>Szybkie łącza

|      |   |
|------|---|
|        [Plany główne](master-plans.md)       |     [Generowanie planu z ograniczeniami](./tasks/constrained-plan.md)  |
| [Tworzenie planu materiałów dla produktów towarzyszących](./tasks/create-material-plan-co-products.md)   |  [Planowanie główne a funkcjonalność wielooddziałowości](master-plan-multisite-functionality.md)  |
| [Tworzenie planu międzyfirmowego](./tasks/create-intercompany-plan.md) | [Podstawowe informacje o prognozowaniu popytu](introduction-demand-forecasting.md)  | 
|[Klucze redukcji](reduction-keys.md)| [Podstawowe informacje dotyczące planowania głównego](https://mbspartner.microsoft.com/AX/CourseOverview/1275) (szkolenie elektroniczne) (wymagane konto CustomerSource)     |
|  [Planowanie główne procesu produkcyjnego](https://mbspartner.microsoft.com/D365E/CourseOverview/1514) (szkolenie elektroniczne) (wymagane konto CustomerSource) | [Międzyfirmowe planowanie główne](https://mbspartner.microsoft.com/AX/CourseOverview/1276) (szkolenie elektroniczne) (wymagane konto CustomerSource)|
                                  
## <a name="additional-resources"></a>Dodatkowe zasoby

### <a name="roadmaps"></a>Mapy
Przejdź na stronę [Plan rozwoju usługi Microsoft Dynamics 365](https://roadmap.dynamics.com/), aby zobaczyć, jakie nowe funkcje zostały wydane, a jakie są jeszcze opracowywane.

### <a name="blogs"></a>Blogi
Opinie, wiadomości i inne informacje na temat planowania głównego oraz innych rozwiązaniach można znaleźć w [blogu zespołu ds. badań i rozwoju modułu Wytwarzanie systemu Dynamics AX](https://blogs.msdn.microsoft.com/axmfg) oraz [blogu zespołu ds. badań i rozwoju modułu Zarządzanie łańcuchem dostaw systemu Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm).

### <a name="task-guides"></a>Przewodniki zadań
Dodatkowa pomoc jest dostępna w formie przewodników po zadaniach wewnątrz rozwiązania Finance and Operations. Aby uzyskać dostęp do przewodników po zadaniach, kliknij przycisk **Pomoc** na dowolnej stronie.

### <a name="webinars"></a>Seminaria internetowe
[Korzystanie z funkcji uczenia maszynowego Azure w zakresie prognozowania popytu](https://www.youtube.com/watch?v=4nQsccdFFDA&feature=youtu.be)

### <a name="tech-conference-recordings"></a>Nagrania z konferencji technologicznej
-  [Rozszerzanie funkcji prognozowania popytu](https://www.youtube.com/watch?v=4OIKIXLiNjI&feature=youtu.be)
-  [Planowanie główne — porady i wskazówki dotyczące rozwiązywania problemów z wydajnością](https://youtu.be/7v8BPmEs9Dg)
-  [Pomocy! Zadania MRP działają zbyt wolno!](https://youtu.be/RLXybx20B5o)




