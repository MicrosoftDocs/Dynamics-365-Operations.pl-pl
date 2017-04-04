---
title: Grupy kont konsolidacji i dodatkowych kont konsolidacji
description: "Ten temat zawiera informacje dotyczące grup kont konsolidacji i dodatkowych kont konsolidacji i wyjaśnia, jak są używane w programie Microsoft Dynamics 365 dla operacji."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265544
ms.assetid: 71c31df7-b655-46a8-8844-4f92a8bd71b0
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 9f4d7fdd8cfa7a540fce219f6ae4792e57dfbe44
ms.openlocfilehash: f9c5aaa389c9c2f85d1ab91cbf3d2222cbebef55
ms.lasthandoff: 03/31/2017


---

# <a name="consolidation-account-groups-and-additional-consolidation-accounts"></a>Grupy kont konsolidacji i dodatkowych kont konsolidacji

Ten temat zawiera informacje dotyczące grup kont konsolidacji i dodatkowych kont konsolidacji i wyjaśnia, jak są używane w programie Microsoft Dynamics 365 dla operacji.

<a name="consolidation-account-groups"></a>Grupy kont konsolidacji
----------------------------

Grupy kont konsolidacji pozwalają tworzyć grupy kont, które chcesz użyć do konsolidowania danych. W większości przypadków grupy kont konsolidacji reprezentuje instrukcją planu kont lub mapuje konta do grupy, która jest zdefiniowana w siedzibie firmy. Konsolidację można znaleźć grupy kont w **instalacji** obszaru **konsolidacje** modułu. Po dodaniu nowej grupy należy wprowadzić identyfikator unikatowy dla grupy kont i nazwy.

## <a name="additional-consolidation-accounts"></a>Dodatkowe konta konsolidacji
Dodatkowe konta konsolidacji umożliwiają przypisywanie konta z istniejącego planu kont do grupy kont konsolidacji. Następnie można określić wartość konta konsolidacji i nazwę. 

Można znaleźć dodatkowe konta konsolidacji w **instalacji** obszaru **konsolidacje** modułu. Podczas tworzenia nowego konta konsolidacji, należy określić następujące informacje:

-   **Konto główne** — jest to pole wyszukiwania, które zawiera wszystkie konta główne, oparte na plan kont, które wybrano na stronie. Należy wybrać konto, nazwa jest automatycznie wprowadzana w **nazwy konta głównego** pole.
-   **Grupa kont konsolidacji** — to pole służy do określania grupy, aby przypisać konto do. Jeśli można skonsolidować na dwa różne sposoby, należy dodać tego samego konta dla wszystkich grup kont konsolidacji cztery.
-   **Konto konsolidacji** — wprowadź wartość Konto konsolidacji. Ta wartość nie musi być konta z planu kont. To może być dowolną wartością, które wymagają.
-   **Nazwa konta konsolidacji** — wprowadź nazwę konta, jaka ma się pojawiać w zapytaniach i raportach.
-   **Poziom SAT** — to pole służy do zgłaszania organom podatkowym meksykański wyciągów z konta. 

Po zakończeniu tworzenia sieci grup kont konsolidacji i dodatkowych kont konsolidacji, można zaznaczyć grupę w procesie online Konsoliduj.



