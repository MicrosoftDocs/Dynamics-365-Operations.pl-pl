---
title: Usunięte lub wycofane funkcje Platform
description: W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia aktualizacji platformy z aplikacji Finance and Operations.
author: sericks007
manager: AnnBe
ms.date: 02/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 66e1420c7053c0df9f42b15c55aba1a8c869f02a
ms.sourcegitcommit: 2cc3b89efdd90f8d80883b7a271d7885282ba3e8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/26/2020
ms.locfileid: "3087890"
---
# <a name="removed-or-deprecated-platform-features"></a>Usunięte lub wycofane funkcje Platform

[!include [banner](../includes/banner.md)]

W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia aktualizacji platformy z aplikacji Finance and Operations.

- *Usunięta* funkcja nie jest już dostępna w produkcie.
- *Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.

Ta lista ma na celu ułatwienie uwzględnienia usuniętych i przestarzałych funkcji we własnym planowaniu. 

> [!NOTE]
> Szczegółowe informacje o obiektów w rozwiązaniu aplikacjach Finance and Operations można znaleźć w temacie [Raporty dotyczące odwołań technicznych](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Można porównać różne wersje tych raportów, aby dowiedzieć się więcej o obiektach, które zostały zmienione lub usunięte w poszczególnych wersjach aplikacji Finance and Operations.

## <a name="platform-update-32"></a>Aktualizacja platformy Update 32

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>Okno dialogowe zmiana żądania przepływu pracy nie zawiera już listy rozwijanej wyboru użytkownika
|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Była to kwestia błędu zabezpieczeń, ponieważ żądanie zmiany może zostać wysłane do niezamierzonego użytkownika. Był to również błąd użyteczności, ponieważ zmuszał użytkownika do określenia, kto był wytwórcą przepływu pracy został i ręczny jego wybór.  |
| **Zamieniona przez inną funkcję?**   | Nie |
| **Powiązane obszary produktów**         | Przepływ pracy |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Lista rozwijana wyboru użytkownika została usunięta z okna dialogowego zmiany żądania w aktualizacji platformy 32. Żądania zmiany żądania zostaną automatycznie wysłane do inicjatora zgodnie z zamierzeniem. Aby uzyskać więcej informacji o tych funkcjach, zapoznaj się z tematem [Akcje w procesach zatwierdzania w przepływie pracy](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/workflow-actions?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json#request-change). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Poprzednie oświadczenia o usuniętych lub wycofanych funkcjach
Aby dowiedzieć się więcej o funkcjach, które zostały usunięte lub wycofane w poprzednich wersjach, zobacz temat [Usunięte lub wycofane funkcje w poprzednich wersjach](../migration-upgrade/deprecated-features.md).

