---
title: "Plany główne"
description: "Używać różnych planów głównych do obsługi codziennych operacji roboczych w firmie, symulowanie różnych strategii planowania, które mają być monitorowane i wykonywania zasad firmy, takie jak zasady dotyczące wewnętrznej satysfakcji wydajności lub klienta."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqParameters, ReqPlanSched
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 7911
ms.assetid: a116b7de-3d6d-4321-87ba-5a5d99c2f64e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 29bb560c11e63938bea73ed8471c27563b546f8f
ms.lasthandoff: 03/31/2017


---

# <a name="master-plans"></a>Plany główne

Używać różnych planów głównych do obsługi codziennych operacji roboczych w firmie, symulowanie różnych strategii planowania, które mają być monitorowane i wykonywania zasad firmy, takie jak zasady dotyczące wewnętrznej satysfakcji wydajności lub klienta. 

Można skonfigurować plany główne na stronie **Plany główne**.

Istnieją dwa typy planów:
-   **Plan statyczny** — w obliczeniach planowania głównego używane są aktualne dane w celu wygenerowania planu zapotrzebowania netto. Plan pozostaje niezmieniony do kolejnego uruchomienia planowania głównego. Jest to plan operacyjny, z którego mogą korzystać różne osoby związane z firmą, takie jak nabywca lub pracownik z działu planowania produkcji, aby uprościć proces decydowania i przeprowadzać codzienne czynności i działania.
-   **Plan dynamiczny** — Ten plan rozpoczyna się od tego samego planu zapotrzebowania netto, jaki został wygenerowany w planowaniu głównym. Plan dynamiczny można jednak aktualizować po każdej zmianie danych głównych. Może się tak stać na przykład po utworzeniu nowego zamówienia sprzedaży. Ta funkcjonalność umożliwia monitorowanie zmieniającej się sieci zamówień i dostępności towarów bez zakłócania planu statycznego, którego używają inni użytkownicy w swoich procesach roboczych.

Firma może wybrać korzystanie z planu dynamicznego lub używanie planu statycznego i dynamicznego. Ponadto można skonfigurować dowolny plan główny, który będzie uwzględniał określoną strategię lub zagadnienie. Przykłady są następujące:
-   Definiowanie wyższych poziomów zapasów w celu uniknięcia wyczerpania zapasów.
-   Określanie dłuższych marginesów bezpieczeństwa w celu ochrony przed dostawcami, na których nie można polegać.

Istnieje również możliwość uruchomienia planu dynamicznego, który będzie aktualizowany nowymi zapotrzebowaniami przy każdym uruchomieniu planowania głównego. Te ustawienia można zdefiniować na stronie **Parametry planowania głównego**.



<a name="see-also"></a>Informacje dodatkowe
--------

[Ustawienia zapotrzebowania](coverage-settings.md)

[Oddzielenie taktyczne i operacyjne planowania dla planowania głównego](http://blogs.msdn.com/b/axmfg/archive/2012/10/12/separating-tactical-and-operative-planning-for-master-scheduling.aspx)

[Planowanie instalacji wzorcowej: Użyć statycznego i dynamicznego planu głównego lub jeden plan?](https://community.dynamics.com/ax/b/msdynaxlessonslearned/archive/2014/01/16/master-planning-use-a-static-and-dynamic-master-plan-or-use-one-plan)


