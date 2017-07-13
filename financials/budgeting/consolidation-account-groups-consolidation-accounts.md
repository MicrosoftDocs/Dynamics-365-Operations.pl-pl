---
title: Grupy kont konsolidacji i dodatkowe konta konsolidacji
description: "Ten temat zawiera informacje o grupach kont konsolidacji i dodatkowych kontach konsolidacji oraz wyjaśnia, jak są one używane w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition."
author: RobinARH
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 265544
ms.assetid: 71c31df7-b655-46a8-8844-4f92a8bd71b0
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 835669de01deb1ba0dcc5752d9d6d8f498e6ff7d
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# Grupy kont konsolidacji i dodatkowe konta konsolidacji
<a id="consolidation-account-groups-and-additional-consolidation-accounts" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Ten temat zawiera informacje o grupach kont konsolidacji i dodatkowych kontach konsolidacji oraz wyjaśnia, jak są one używane w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition.

Grupy kont konsolidacji
<a id="consolidation-account-groups" class="xliff"></a>
----------------------------

Grupy kont konsolidacji pozwalają tworzyć grupy kont, które mają użyć do konsolidowania danych. W większości przypadków grupa kont konsolidacji reprezentuje urzędowy plan kont lub mapuje konta na grupę zdefiniowaną przez centralę firmy. Grupy kont konsolidacji są podane w module **Konsolidacje** w obszarze **Ustawienia**. Podczas dodawania nowej grupy wprowadzasz unikatowy identyfikator i nazwę grupy kont.

## Dodatkowe konta konsolidacji
<a id="additional-consolidation-accounts" class="xliff"></a>
Funkcja dodatkowych kont konsolidacji umożliwia przypisanie konta z istniejącego planu kont do grupy kont konsolidacji. Następnie można określić wartość i nazwę konta konsolidacji. 

Dodatkowe konta konsolidacji są podane w module **Konsolidacje** w obszarze **Ustawienia**. Podczas tworzenia nowego konta konsolidacji należy określić następujące informacje:

-   **Konto główne** — To pole jest odnośnikiem, który pokazuje wszystkie konta główne oparte na plan kont wybranym na stronie. Po wybraniu konta nazwa jest automatycznie wprowadzana w polu **Nazwa konta głównego**.
-   **Grupa kont konsolidacji** — To pole służy określaniu grupy, do której ma zostać przypisane konto. Jeśli konsolidujesz na dwa różne sposoby, należy dodać to samo konto do wszystkich czterech grup kont konsolidacji.
-   **Konto konsolidacji** — Wprowadź wartość konta konsolidacji. Ta wartość nie musi określać konta z planu kont. To może być dowolne inne konto.
-   **Nazwa konta konsolidacji** — Wprowadź nazwę konta w postaci, w jakiej ma być wyświetlana w zapytaniach i raportach.
-   **Poziom SAT** — To pole służy do zgłaszania wyciągów z kont meksykańskiemu urzędowi skarbowemu. 

Po zakończeniu tworzenia grup kont konsolidacji i dodatkowych kont konsolidacji można wybrać grupę w procesie konsolidacji online.





