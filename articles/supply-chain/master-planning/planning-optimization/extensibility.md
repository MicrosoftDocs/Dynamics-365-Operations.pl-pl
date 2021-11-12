---
title: Rozszerzalność optymalizacji planowania
description: W tym temacie opisano scenariusze możliwości rozszerzania, które są obsługiwane w optymalizacji planowania.
author: ChristianRytt
ms.date: 08/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-07-07
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: e18801a02ae9e904eb5bc597f9f61ed42c537ab9
ms.sourcegitcommit: 614d79cba238e466d445767a7d0a012e785a9861
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/19/2021
ms.locfileid: "7652061"
---
# <a name="planning-optimization-extensibility"></a>Rozszerzalność optymalizacji planowania

[!include [banner](../../includes/banner.md)]

W tym temacie opisano scenariusze możliwości rozszerzania, które są powiązane z planowaniem głównym i obsługiwane w optymalizacji planowania. Te możliwości wyszukiwania są dostępne od aplikacji Microsoft Dynamics 365 Supply Chain Management w wersji 10.0.13.

## <a name="custom-processing-when-master-planning-is-completed"></a>Przetwarzanie niestandardowe po ukończeniu planowania głównego

W najczęściej występującym scenariuszu możliwości rozszerzania optymalizacji planowania przetwarzanie niestandardowe jest wykonywane po zaktualizowaniu planu. Można na przykład dodać kolumnę do tabeli zamówień planowanych (`ReqPO`) lub uzyskać informacje statystyczne z wygenerowanego planu. Głównym punktem możliwości rozszerzania, który włącza te scenariusze, jest metoda `jobCompletedSuccessfully` w klasie `MpsMasterPlanningEvents`.

```X++
public static void jobCompletedSuccessfully(MpsMasterPlanningJobCompletedSuccessfullyEventArgs _args)
```

Oto przykład rozszerzenia, które ustawia niestandardowe pole `CstmOrderPriority` w planowanym zamówieniu.

```X++
[ExtensionOf(classStr(MpsMasterPlanningEvents))]
public static final class MpsMasterPlanningEvents_Cstm_Extension
{
    public static void jobCompletedSuccessfully(MpsMasterPlanningJobCompletedSuccessfullyEventArgs _args)
    {
        ttsbegin;

        var affectedPlannedOrdersQuery = _args.parmPostProcessingQueryBuilder().buildAffectedPlannedOrdersQuery();
        var affectedPlannedOrdersQueryRun = new QueryRun(affectedPlannedOrdersQuery);

        while (affectedPlannedOrdersQueryRun.next())
        {
            ReqPO reqPO = affectedPlannedOrdersQueryRun.get(tableNum(ReqPO));
            reqPO.selectForUpdate(true);
            reqPO.CstmOrderPriority = reqPO.ReqDate - systemDateGet() < 7 ? CstmPlannedOrderPriority::Urgent : CstmPlannedOrderPriority::Regular;
            reqPO.doUpdate();
        }

        ttscommit;

        next jobCompletedSuccessfully(_args);
    }

}
```

Podczas dodawania logiki niestandardowej należy wziąć pod uwagę następujące ograniczenia i najlepsze rozwiązania:

- Metoda `jobCompletedSuccessfully` jest wywoływana poza zakresem transakcji. Dlatego plan jest już widoczny dla użytkownika po uruchomieniu logiki niestandardowej. Jeśli dostosowywanie spowoduje ustawienie dodatkowych pól w zamówieniach planowanych, należy wiedzieć, że wartości tych pól ostatecznie będą spójne (innymi słowy, mogą być one nieaktualne bezpośrednio po zakończeniu planowania).
- Inne zadanie planowania głównego może się rozpocząć po wywołaniu metody `jobCompletedSuccessfully`. Nowe zadanie może mieć wpływ na pełny plan lub jego część. Nowe zadanie może zaktualizować lub usunąć te same planowane zamówienia lub transakcje zapotrzebowania, które zostały utworzone lub zaktualizowane w ramach zadania planowania obsługiwanego w metodzie `jobCompletedSuccessfully`. W przypadku rozszerzonego zdarzenia należy obsługiwać wyjątki konfliktów aktualizacji.
- W przypadku rozszerzenia tej metody należy unikać używania zakresu jednej transakcji. Pojedyncze uruchomienie planowania głównego może powodować miliony transakcji zapotrzebowania i setki tysięcy zamówień planowanych. Jeśli wszystkie te transakcje i planowane zamówienia są przetwarzane w zakresie jednej transakcji, nastąpi wiele blokad SQL i inne procesy planowania będą blokowane. Ponadto jeśli transakcja jest wstrzymana przez długi czas, w bazie danych SQL będą tworzone „rekordy widma”. Rekord będzie miał negatywny wpływ na każdy proces w systemie.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]