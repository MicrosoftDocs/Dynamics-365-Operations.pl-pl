---
title: "Obsługa zamówień planowanych"
description: "Ten artykuł zawiera informacje o metodach zarządzania zamówienia planowanymi. Opisano w nim sposób aktualizowania stanów zamówień planowanych i ich potwierdzania oraz odfiltrowywania zamówień planowanych, które mają taki sam stan jak wybrane zamówienie planowane."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 94f6f28ec4b255930f84a27eb5394503ff59e4c0
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="maintain-planned-orders"></a>Obsługa zamówień planowanych

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera informacje o metodach zarządzania zamówienia planowanymi. Opisano w nim sposób aktualizowania stanów zamówień planowanych i ich potwierdzania oraz odfiltrowywania zamówień planowanych, które mają taki sam stan jak wybrane zamówienie planowane.

Można zarządzać planowanymi zamówieniami z obszaru roboczego **Planowanie główne**, listy **Zamówienie planowane** lub list **Planowane zamówienia zakupu**, **Planowane zlecenia produkcyjne** i **Planowane przeniesienie**. Pole **Stan** pomaga w śledzeniu postępu zamówień. Używane są następujące wartości:

-   Zamówienia planowane generowane podczas planowania głównego mają stan **Nieprzetworzone**.
-   Jeżeli nie chcesz ustalać zamówienia planowanego, możesz nadać mu stan **Zakończone**.
-   Aby ustalić zamówienie planowane, nadaj mu stan **Zatwierdzone**. Ten stan oznacza, że użytkownik zatwierdza ustalanie zamówienia planowanego, ale nie jest ono jeszcze ustalone.

**Uwaga:** zatwierdzone zamówienie planowane jest przesyłane w aktualnym stanie do kolejnego obliczenia planu głównego. Aby ustalić zamówienia planowane, należy kolejno kliknąć opcję **Akceptuj**. Można ustalić następujące zamówienia planowane:

-   Wybrane zamówienie planowane.
-   Wiele zamówień planowanych.
-   Zamówienia planowane generowane przez rozłożenie ze strony **Rozkładanie**. Kliknij opcję **Zamówienia planowane**, wybierz zamówienie planowane, a następnie kliknij opcję **Akceptuj**.

Po ustaleniu zamówienie planowane zostanie przesunięte do sekcji zamówień w odpowiednim module. **Uwaga:** Zamówienie planowane o określonym statusie można kliknąć prawym przyciskiem myszy i odfiltrować inne zamówienia planowane o takim samym statusie. Ta funkcja jest przydatna, jeśli na przykład chcesz filtrować wszystkie zamówienia planowane, które mają stan **Zatwierdzone**, tak aby można je było następnie ustalić.

<a name="see-also"></a>Informacje dodatkowe
--------

[Plany główne](master-plans.md)




