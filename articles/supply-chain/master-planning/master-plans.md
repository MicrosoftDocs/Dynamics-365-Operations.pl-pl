---
title: Plany główne
description: Istnieje możliwość korzystania z różnych planów głównych w celu obsługiwania codziennych operacji w firmie, symulowania różnych strategii planowania, które mają być monitorowane, oraz wdrażania polityki firmy, na przykład dotyczącej wydajności lub zadowolenia klientów.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqParameters, ReqPlanSched
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 7911
ms.assetid: a116b7de-3d6d-4321-87ba-5a5d99c2f64e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: df9585cfe2bc7ccc60dc69741994785869ba71b1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "325050"
---
# <a name="master-plans"></a>Plany główne

[!include [banner](../includes/banner.md)]

Istnieje możliwość korzystania z różnych planów głównych w celu obsługiwania codziennych operacji w firmie, symulowania różnych strategii planowania, które mają być monitorowane, oraz wdrażania polityki firmy, na przykład dotyczącej wydajności lub zadowolenia klientów. 

Można skonfigurować plany główne na stronie **Plany główne**.

Istnieją dwa typy planów:
-   **Plan statyczny** — w obliczeniach planowania głównego używane są aktualne dane w celu wygenerowania planu zapotrzebowania netto. Plan pozostaje niezmieniony do kolejnego uruchomienia planowania głównego. Jest to plan operacyjny, z którego mogą korzystać różne osoby związane z firmą, takie jak nabywca lub pracownik z działu planowania produkcji, aby uprościć proces decydowania i przeprowadzać codzienne czynności i działania.
-   **Plan dynamiczny** — Ten plan rozpoczyna się od tego samego planu zapotrzebowania netto, jaki został wygenerowany w planowaniu głównym. Plan dynamiczny można jednak aktualizować po każdej zmianie danych głównych. Może się tak stać na przykład po utworzeniu nowego zamówienia sprzedaży. Ta funkcjonalność umożliwia monitorowanie zmieniającej się sieci zamówień i dostępności towarów bez zakłócania planu statycznego, którego używają inni użytkownicy w swoich procesach roboczych.

Firma może wybrać korzystanie z planu dynamicznego lub używanie planu statycznego i dynamicznego. Ponadto można skonfigurować dowolny plan główny, który będzie uwzględniał określoną strategię lub zagadnienie. Przykłady są następujące:
-   Definiowanie wyższych poziomów zapasów w celu uniknięcia wyczerpania zapasów.
-   Określanie dłuższych marginesów bezpieczeństwa w celu ochrony przed dostawcami, na których nie można polegać.

Istnieje również możliwość uruchomienia planu dynamicznego, który będzie aktualizowany nowymi zapotrzebowaniami przy każdym uruchomieniu planowania głównego. Te ustawienia można zdefiniować na stronie **Parametry planowania głównego**.



<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Ustawienia zapotrzebowania](coverage-settings.md)

[Oddzielanie planowania taktycznego i operacyjnego w planowaniu głównym](http://blogs.msdn.com/b/axmfg/archive/2012/10/12/separating-tactical-and-operative-planning-for-master-scheduling.aspx)

[Planowanie główne: Używać planów głównych statycznego i dynamicznego czy tylko jednego planu?](https://community.dynamics.com/ax/b/msdynaxlessonslearned/archive/2014/01/16/master-planning-use-a-static-and-dynamic-master-plan-or-use-one-plan)



