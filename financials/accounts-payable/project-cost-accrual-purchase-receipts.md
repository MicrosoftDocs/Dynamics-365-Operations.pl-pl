---
title: "Naliczanie kosztu projektu na przyjęcia zakupu"
description: "W tym temacie opisano sposób naliczonych kosztów projektu od zakupu przyjęć mogą być śledzone w programie Microsoft Dynamics 365 dla operacji."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 266984
ms.assetid: 61e7d2a3-5aab-4113-bccc-213f932885d2
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 27a0a71095dce46c0119b32a92f8c4dce0f42e43
ms.lasthandoff: 03/31/2017


---

# <a name="project-cost-accrual-on-purchase-receipts"></a>Naliczanie kosztu projektu na przyjęcia zakupu

W tym temacie opisano sposób naliczonych kosztów projektu od zakupu przyjęć mogą być śledzone w programie Microsoft Dynamics 365 dla operacji. 

Faktury dla projektu często przychodzą później niż towary i usługi są dostarczane, które mogą mieć znaczący wpływ na projekt kluczowych wskaźników wydajności (KPI). Ważne można było śledzić te transakcje w obu finansowych i projektu sprawozdania.

Następujący przykład ilustruje to. 

Contoso konsultacji został uruchomiony nowy projekt wdrożenia chmury. Zamówienie zakupu jest tworzone na zakup komputera dla projektu. Komputer będzie kosztować $1500 i usług instalacji będzie kosztować $150. Dostawca jest pobierana i instalowana komputerze, ale faktura nie osiągnęła jeszcze Contoso konsultacji. Menedżer projektu chce Zobacz naliczania kosztów projektu o $1650, zanim faktura zostanie dostarczona. Koszt ten powinien również znaleźć odzwierciedlenie w sprawozdaniu finansowym spółki miesiąc zakończenia. 

Naliczony koszt musi być rejestrowana na poziomie finansowego i na poziomie projektu dla celów sprawozdawczości. W usłudze Dynamics 365 dla operacji finansowych aktualizację dokumentu przyjęcia produktów mogą być śledzone dla kategorii towarów i zamówień. 

W przypadku towarów na **Rozrachunki z dostawcami Parametry** strony, kliknij **Księgowanie dokumentów dostawy w księdze** opcji.
[![accruals1](./media/accruals1-1024x409.png)](./media/accruals1.png) 

Dla kategorii zaopatrzenia na **Reguła kategorii** strony, kliknij **zakup** zasady, a następnie wybierz **naliczania kosztów zakupu po otrzymaniu** dla każdej kategorii zaopatrzenia.
[![accruals2](./media/accruals2-1024x569.png)](./media/accruals2.png) 

**Koszty, zapis przeciwstawny dokumentu dostawy zakupu** i **naliczania zakupu** kont w **ustawienia księgowania** będzie używana, gdy księgowane są załączniki, które są związane z dokumentu przyjęcia produktów.
[![accruals3](./media/accruals3-1024x429.png)](./media/accruals3.png) 

Przy użyciu tego samego scenariusza, zobaczmy, jak księgowanie dokumentu przyjęcia produktów wpłynie na księgi głównej i informacji o projekcie. 

**Krok 1:** Utwórz i Potwierdź nowe zamówienie zakupu dla projektu do rejestrowania zakup komputera dla usług $1500 i instalacji dla $150.
[![accruals4](./media/accruals4-1024x497.png)](./media/accruals4.png) 

Po potwierdzeniu zamówienia zakupu tworzone są transakcje koszt ustalony dla projektu. 
[![accruals5](./media/accruals5-1024x219.png)](./media/accruals5.png) 

> [!NOTE]
> Transakcje kosztu ustalonego będą miały **źródło transakcji** pole ustawione na **zamówienia zakupu**. Tworzenie i potwierdzenie zamówienia zakupu nie tworzy transakcje dla projektu. 

**Krok 2:** dostarczenie towarów i usług i dostawy nie jest zarejestrowany. 

Księgowanie dokumentu przyjęcia produktów generować i Księgowanie załącznika w księdze. Załącznik po stronie debetowej kosztów zakupu, niezafakturowane konto i konto naliczeń zakupu. 
[![accruals6](./media/accruals6-1024x214.png)](./media/accruals6.png)

> [!NOTE]
> Księgowanie dokumentu przyjęcia produktów użyje ustawień księgowania dla kategorii zaopatrzenia i produktów, a nie ustawień księgowania dla kategorii projektu. W celu właściwego uwzględnienia wpływu finansowego naliczenia zakupu, ta konfiguracja musi być skoordynowana. 

Umożliwia mapowanie kategorii zaopatrzenia do kategorii projektów na **kategorii zaopatrzenia** strony.
[![accruals7](./media/accruals7-1024x390.png)](./media/accruals7.png)

**Krok 3:** utworzyć fakturę od dostawcy wersji roboczej. 

W usłudze Dynamics 365 dla operacji Księgowanie dokumentu przyjęcia produktów nie wpływa na informacje o projekcie. Jako rozwiązanie alternatywne można wygenerować fakturę od dostawcy projekt bezpośrednio po zaksięgowaniu przyjęcia zakupu. Przejdź do **zamówienia zakupu** strony &gt;**kartę faktura**&gt;**Generuj**&gt;**faktury**. Tworzy dokument oczekuje na fakturę, która aktualizuje informacje o projekcie. 

Tworzenie faktury dostawcy projektu spowoduje wygenerowanie oczekujące transakcje projektu. 
[![accruals8](./media/accruals8-1024x225.png)](./media/accruals8.png) 

W **ustalony koszt** stronę, rekordy utworzone w kroku 1 zostanie zamknięty i zostanie utworzone nowe rekordy do odzwierciedlają zaangażowanie kosztów pochodzących z faktura oczekująca. **Źródło transakcji** w polu Koszt ustalony zostanie ustawione na wartość **faktury od dostawcy**.
[![accruals9](./media/accruals9-1024x200.png)](./media/accruals9.png)

Faktura od dostawcy pozostaną w stanie oczekiwania do momentu nadejścia fakturę od dostawcy rzeczywista.


