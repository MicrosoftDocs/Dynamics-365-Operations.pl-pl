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
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: fdfa460fedcf9c3a0999d5f35eeb683b871aabfe
ms.contentlocale: pl-pl
ms.lasthandoff: 04/25/2017


---

# <a name="letters-of-guarantee"></a>Poręczenia

[!include[banner](../includes/banner.md)]


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






