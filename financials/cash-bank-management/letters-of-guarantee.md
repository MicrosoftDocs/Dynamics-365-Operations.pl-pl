---
title: "Poręczenia"
description: "Ten artykuł zawiera informacje o poręczeniach. W poręczeniu bank zgadza się zapłacić określoną kwotę pieniędzy osobie, jeśli jeden z klientów banku nie ureguluje wobec tej osoby zobowiązania pieniężnego lub innego."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BankLGGuarantee
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 18291
ms.assetid: 5c0b5e37-d51d-4a01-bb37-1882173abb9f
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: fa27a5a2b2edb73875b74572bc467cd20a3e7ec8
ms.lasthandoff: 03/31/2017


---

# <a name="letters-of-guarantee"></a>Poręczenia

Ten artykuł zawiera informacje o poręczeniach. W poręczeniu bank zgadza się zapłacić określoną kwotę pieniędzy osobie, jeśli jeden z klientów banku nie ureguluje wobec tej osoby zobowiązania pieniężnego lub innego. 

Poręczenie to zobowiązanie się banku (gwaranta) do zapłaty określonej kwoty pieniędzy określonej osobie (beneficjentowi), jeśli bank odbiorca (podmiot zabezpieczeń) nie wywiąże się z realizacji płatności lub zobowiązania względem beneficjenta. Poręczenia są niezbywalne. Dotyczą one tylko beneficjenta wskazanego w umowie. Podmiot zabezpieczeń może wnioskować o zwiększenie lub zmniejszenie wartości poręczenia, zgodnie z warunkami umowy. 

Aby zrealizować poręczenie, beneficjent musi przed upływem daty ważności przesłać oryginalne poręczenie i poinformować bank obsługujący zobowiązania podmiotu zabezpieczeń. Bank następnie wypłaca kwotę należności na konto beneficjenta zgodnie z ustaleniami określonymi w poręczeniu. Bank zatrzymuje procent płatności jako marżę. Wartość procentowa jest uzgodniona z góry i zapisana w warunkach umowy. 

Można utworzyć kod do śledzenia celu poręczenia. Można również określić przyczyny, które będą skojarzone z poręczeniem w przypadku jego anulowania. Kody celów i przyczyny podane przez bank można wyświetlać na stronach **Kody celów płatności** i **Przyczyny transakcji bankowych**. 

Na stronie **poręczenia** można wykonać następujące zadania:

-   Tworzenie poprawnych pozycji księgowania i eliminacja wprowadzania ręcznego.
-   Rejestrowanie wszystkich powiązanych transakcji pieniężnych i niepieniężnych i śledzenie sald poręczeń.
-   Rejestrowanie i śledzenie stanu i dat wygaśnięcia poręczenia.
-   Generowanie raportu, który zawiera listę banków posiadających poręczenia.

W poniższej tabeli opisano akcje, które można wykonywać w związku z poręczeniem.

| Akcja              | Cel                                                                                                                   |
|---------------------|---------------------------------------------------------------------------------------------------------------------------|
| Prześlij do banku      | Przesłanie do banku wniosku o wystawienie poręczenia.                                                                       |
| Otrzymaj z banku   | Gdy bank wyrazi zgodę na przesłany wniosek, można odebrać poręczenie.                            |
| Przekaż beneficjentowi | Po otrzymaniu poręczenia z banku można je przekazać beneficjentowi.              |
| Zwiększ wartość      | Jeśli beneficjent i podmiot zabezpieczeń wyrażą zgodę, można zwiększyć wartość pieniężną.                                                  |
| Zmniejsz wartość      | Jeśli beneficjent i podmiot zabezpieczeń wyrażą zgodę, można zmniejszyć wartość pieniężną.                                                  |
| Rozszerz              | Po przedstawieniu beneficjentowi poręczenia można wydłużyć okres ważności, jeśli jego wydłużenie jest konieczne. |
| Anuluj              | Jeśli cel poręczenia nie ma już zastosowania, można anulować umowę.                  |
| Zlikwiduj           | Kiedy beneficjent okaże w banku poręczenie, można je spłacić.                      |




