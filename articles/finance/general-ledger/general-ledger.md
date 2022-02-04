---
# required metadata
title: Księga główna i omówienieraportów finansowych
description: Moduł Księga główna służy do definiowania rekordów finansowych dla firmy i zarządzania nimi.
author: ShylaThompson
ms.date: 08/14/2020
ms.topic: overview
ms.prod: null
ms.technology: null
ms.search.form: GeneralJournalEntryWorkspace
audience: Application User
ms.reviewer: roschlom
ms.custom:
  - '65431'
  - intro-internal
ms.assetid: d2c604df-daae-42cd-82d9-c80e3dee4a60
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: '2016-02-28'
ms.dyn365.ops.version: AX 7.0.0
---

# <a name="general-ledger-home-page"></a>Strona główna księgi głównej

[!include [banner](../includes/banner.md)]

Moduł Księga główna służy do definiowania rekordów finansowych dla firmy i zarządzania nimi. Księga główna to rejestr zapisów debetowych i kredytowych. Te wpisy są sklasyfikowane przy użyciu kont wymienionych w planie kont. 

 - [Planowanie planu kont](plan-chart-of-accounts.md)
 - [Typy kont głównych](main-account-types.md)

Można przeprowadzić alokację lub dystrybucję kwot pieniężnych do jednego lub kilku kont albo do kombinacji kont i wymiarów opartych na regułach alokacji. Istnieją dwa typy alokacji: stałe i zmienne. Można również rozliczać transakcje między kontami księgowymi i przeszacować kwoty w walucie. Na koniec roku obrachunkowego należy wygenerować transakcje zamknięcia i przygotować konta do nowego roku obrachunkowego. Funkcja konsolidacji umożliwia połączenie wyników finansowych dla kilku oddziałów firmy w jedne wyniku dla skonsolidowanej organizacji. Oddziały mogą znajdować się w tej samej bazie danych lub w oddzielnych bazach danych.

- [Omówienie konsolidacji i eliminacji](../budgeting/consolidation-elimination-overview.md)
- [Salda kont księgi głównej](general-ledger-account-balances.md)
- [Wymiary finansowe](financial-dimensions.md)

[![Proces biznesowy.](./media/GL-process.PNG)](./media/GL-process.PNG)

## <a name="sales-tax"></a>Podatek
Każda firma zbiera i płaci podatki w różnych urzędach. Przepisy i stawki różnią się w zależności od kraju/regionu, województwa, powiatu i miasta.
Ponadto reguły muszą być aktualizowane okresowo, jeśli zmieniają się wymagania urzędów skarbowych. Kody podatków zawierają podstawowe informacje o wysokości podatków pobranych i odprowadzonych do urzędu skarbowego. Podczas konfigurowania kodów podatków można zdefiniować kwoty lub wartości procentowe, które muszą zostać pobrane. Można również zdefiniować różne metody, za pomocą których te kwoty lub wartości procentowe są stosowane do kwoty transakcji. Tematy w tej sekcji zawierają informacje o sposobie ustawiania kodów podatków dla metod i stawek wymaganych przez urzędy skarbowe.

 - [Omówienie podatku](indirect-taxes-overview.md)
 - [Stawki podatku na podstawie pól Podstawa limitu i Metoda obliczania](marginal-base-field.md)
 - [Reguły płatności podatku i zaokrąglania](round-sales-tax-payments.md)


## <a name="additional-resources"></a>Dodatkowe zasoby

#### <a name="whats-new-and-in-development"></a>Nowe i opracowywane funkcje

Przejdź do [planów wydań Microsoft Dynamics 365](/dynamics365/release-plans/), aby zobaczyć, jakie nowe funkcje zostały zaplanowane. 

#### <a name="financial-reporting"></a>Raporty finansowe
Przejdź do tematu [Omówienie Financial reporting](../../fin-ops-core/dev-itpro/analytics/financial-reporting-intro.md), aby uzyskać informacje o raportach finansowych.

#### <a name="blogs"></a>Blogi

Opinie, wiadomości i inne informacje możesz znaleźć w [blogu usługi Microsoft Dynamics 365](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise) oraz [Microsoft Dynamics 365 Finance i Operacje - Blog rozwiązania Financials](https://community.dynamics.com/365/financeandoperations/b/financials).

[Microsoft Dynamics Operations](https://community.dynamics.com/partner/b/operationspartnercommunityblog) zapewnia Microsoft Dynamics, jeden zasób, w którym mogą dowiedzieć się, co nowego, poza tym zyskuje na popularności w Dynamics 365.

### <a name="videos"></a>Filmy

Obejrzyj filmy instruktażowe w [kanale YouTube rozwiązania Microsoft Dynamics 365](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).

#### <a name="community-blogs"></a>Blogi społeczności

- [Co należy wiedzieć o księdze w Dynamics 365 for Finance and Operations](https://financefunction.tech/2018/04/29/what-you-should-know-about-ledger-in-dynamics-365-for-finance-and-operations)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]