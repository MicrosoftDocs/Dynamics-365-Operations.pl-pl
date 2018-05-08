---
title: "Księga główna i strona główna raportów finansowych"
description: "Moduł Księga główna służy do definiowania rekordów finansowych dla firmy i zarządzania nimi."
author: twheeloc
manager: AnnBe
ms.date: 08/31/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: GeneralJournalEntryWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 65431
ms.assetid: d2c604df-daae-42cd-82d9-c80e3dee4a60
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 2177110dc16528de7eddedb0667faae553a36b12
ms.contentlocale: pl-pl
ms.lasthandoff: 02/07/2018

---

# <a name="general-ledger"></a>Księga główna 

[!include [banner](../includes/banner.md)]

Moduł Księga główna służy do definiowania rekordów finansowych dla firmy i zarządzania nimi. Księga główna to rejestr zapisów debetowych i kredytowych. Te wpisy są sklasyfikowane przy użyciu kont wymienionych w planie kont. 

 - [Planowanie planu kont](plan-chart-of-accounts.md)
 - [Typy kont głównych](main-account-types.md)

Można przeprowadzić alokację lub dystrybucję kwot pieniężnych do jednego lub kilku kont albo do kombinacji kont i wymiarów opartych na regułach alokacji. Istnieją dwa typy alokacji: stałe i zmienne. Można również rozliczać transakcje między kontami księgowymi i przeszacować kwoty w walucie. Na koniec roku obrachunkowego należy wygenerować transakcje zamknięcia i przygotować konta do nowego roku obrachunkowego. Funkcja konsolidacji umożliwia połączenie wyników finansowych dla kilku oddziałów firmy w jedne wyniku dla skonsolidowanej organizacji. Oddziały mogą znajdować się w tej samej bazie danych programu Microsoft Dynamics 365 for Finance and Operations lub w oddzielnych bazach danych.

- [Omówienie konsolidacji i eliminacji](../budgeting/consolidation-elimination-overview.md)
- [Salda głównego konta księgowego](general-ledger-account-balances.md)
- [Wymiary finansowe](financial-dimensions.md)

[![Proces biznesowy](./media/GL-process.PNG)](./media/GL-process.PNG)

## <a name="sales-tax"></a>Podatek
Każda firma zbiera i płaci podatki w różnych urzędach. Przepisy i stawki różnią się w zależności od kraju/regionu, województwa, powiatu i miasta.
Ponadto reguły muszą być aktualizowane okresowo, jeśli zmieniają się wymagania urzędów skarbowych. Kody podatków zawierają podstawowe informacje o wysokości podatków pobranych i odprowadzonych do urzędu skarbowego. Podczas konfigurowania kodów podatków można zdefiniować kwoty lub wartości procentowe, które muszą zostać pobrane. Można również zdefiniować różne metody, za pomocą których te kwoty lub wartości procentowe są stosowane do kwoty transakcji. Tematy w tej sekcji zawierają informacje o sposobie ustawiania kodów podatków dla metod i stawek wymaganych przez urzędy skarbowe.

 - [Omówienie podatku](indirect-taxes-overview.md)
 - [Stawki podatku na podstawie pól Podstawa limitu i Metoda obliczania](marginal-base-field.md)
 - [Reguły płatności podatku i zaokrąglania](round-sales-tax-payments.md)


## <a name="additional-resources"></a>Dodatkowe zasoby

### <a name="whats-new-and-in-development"></a>Nowe i opracowywane funkcje

Przejdź na stronę [Plan rozwoju usługi Microsoft Dynamics 365](https://roadmap.dynamics.com/), aby zobaczyć, jakie nowe funkcje zostały wydane, a jakie są jeszcze opracowywane. 

### <a name="blogs"></a>Blogi

Opinie, wiadomości i inne informacje dotyczące modułu Rozrachunki z dostawcami możesz znaleźć w [blogu usługi Microsoft Dynamics 365](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise).

Wiele wpisów dotyczących modułu Księga główna jest dostępnych w [blogu zespołu produktu Microsoft Dynamics AX](https://blogs.msdn.microsoft.com/dax/). Mimo że część z tych wpisów została napisana dla poprzedniej wersji modułu Księga główna, to w obecnej wersji są również używane te same pojęcia i podobne procedury.

Blog [społeczności partnerów zajmujących się oprogramowaniem Microsoft Dynamics Operations](https://community.dynamics.com/partner/b/operationspartnercommunityblog) stanowi doskonały zasób dla partnerów zajmujących się oprogramowaniem Microsoft Dynamics, który zawiera informacje o nowościach i popularnych rozwiązaniach działu MBS Operations.

### <a name="task-guides"></a>Przewodniki zadań
Dodatkowa pomoc jest dostępna w formie przewodników po zadaniach wewnątrz rozwiązania Finance and Operations. Aby uzyskać dostęp do przewodników po zadaniach, kliknij przycisk Pomoc na dowolnej stronie.

### <a name="videos"></a>Filmy

Obejrzyj filmy instruktażowe w [kanale YouTube rozwiązania Microsoft Dynamics 365](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).


