---
title: Usunięte lub wycofane funkcje w aplikacji Dynamics 365 Supply Chain Management
description: W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia w Dynamics 365 Supply Chain Management.
author: kamaybac
manager: tfehr
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: d4d2805e36f132660152370cbeee856862ad6faa
ms.sourcegitcommit: 069ed5789517b550065e5e2317658fec4027359e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/07/2020
ms.locfileid: "4689540"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-supply-chain-management"></a>Usunięte lub wycofane funkcje w aplikacji Dynamics 365 Supply Chain Management

[!include [banner](../includes/banner.md)]

Ten temat zostanie zaktualizowany, jeśli w systemie Dynamics 365 Supply Chain Management zostaną udokumentowane nowe lub wycofane funkcje.

- *Usunięta* funkcja nie jest już dostępna w produkcie.
- *Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.

Ta lista ma na celu ułatwienie uwzględnienia usuniętych i przestarzałych funkcji we własnym planowaniu.

> [!NOTE]
> Szczegółowe informacje o obiektów w rozwiązaniu aplikacjach Finance and Operations można znaleźć w temacie [Raporty dotyczące odwołań technicznych](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Można porównać różne wersje tych raportów, aby dowiedzieć się więcej o obiektach, które zostały zmienione lub usunięte w poszczególnych wersjach aplikacji Finance and Operations.

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10015-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Supply Chain Management 10.0.15

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Wsparcie Internet Explorer 11 dla Dynamics 365 jest przestarzałe

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Począwszy od grudnia 2020 r., obsługa Microsoft Internet Explorer 11 dla wszystkich produktów Dynamics 365 jest przestarzała, a Internet Explorer 11 nie będzie obsługiwany po sierpniu 2021 r.<br><br>Będzie to miało wpływ na klientów, którzy używają produktów Dynamics 365 zaprojektowanych do używania za pośrednictwem interfejsu Internet Explorer 11. Po sierpniu 2021, Internet Explorer 11 nie będzie obsługiwany przez produkty Dynamics 365. |
| **Zamieniona przez inną funkcję?**   | Zaleca się, aby klienci przeszli na Microsoft Edge.|
| **Powiązane obszary produktów**         | Wszystkie produkty Dynamics 365 |
| **Opcja wdrażania**              | Wszyscy|
| **Stan**                         | Wycofane. Internet Explorer 11 nie będzie obsługiwany po sierpniu 2021.|

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-manufacturing-scenarios"></a>Użycie wbudowanego aparatu planowania głównego Supply Chain Management na potrzeby scenariuszy dotyczących produkcji

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Aby zwiększyć wydajność i zminimalizować obciążenie pracą bazy danych SQL podczas przebiegów planowania głównego, aparat planowania głównego aplikacji Supply Chain Management jest zastępowany przez optymalizację planowania. Optymalizacja planowania umożliwia szybkie przebiegi planowania, które można wykonywać nawet w godzinach pracy. Pozwala to planistom na natychmiastowe reagowanie na zmiany wprowadzone w parametrach popytu lub planowania. |
| **Zamieniona przez inną funkcję?**   | Tak, optymalizacja planowania zastąpi istniejący wbudowany aparat planowania głównego aplikacji Supply Chain Management. |
| **Powiązane obszary produktów**         | Supply Chain Management — planowanie główne |
| **Opcja wdrażania**              | Tylko chmura. Optymalizacja planowania nie jest obsługiwana w przypadku wdrożeń lokalnych. |
| **Stan**                         | Wycofane. Do 1 października 2021 r. scenariusze produkcji nie będą już obsługiwane za pomocą wbudowanego aparatu planowania głównego aplikacji Dynamics 365 Supply Chain Management. W scenariuszach produkcji klienci muszą korzystać z optymalizacji planowania podczas obliczeń planowania głównego. Aby uzyskać więcej informacji, zobacz temat [Dokumentacja dotycząca optymalizacji planowania](https://go.microsoft.com/fwlink/?linkid=2105830). Klienci z wdrożeniami lokalnymi aplikacji Dynamics 365 Supply Chain Management będą mogli nadal korzystać z aparatu planowania głównego aplikacji Supply Chain Management w scenariuszach produkcji po październiku 2021 r. Nie będą jednak wprowadzane dodatkowe ulepszenia funkcji. |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10011-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Supply Chain Management 10.0.11

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios"></a>Użycie wbudowanego aparatu planowania głównego Supply Chain Management na potrzeby scenariuszy dotyczących dystrybucji

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Aby zwiększyć wydajność i zminimalizować obciążenie pracą bazy danych SQL podczas przebiegów planowania głównego, aparat planowania głównego aplikacji Supply Chain Management jest zastępowany przez optymalizację planowania. Optymalizacja planowania umożliwia szybkie przebiegi planowania, które można wykonywać nawet w godzinach pracy. Pozwala to planistom na natychmiastowe reagowanie na zmiany wprowadzone w parametrach popytu lub planowania. |
| **Zamieniona przez inną funkcję?**   | Tak, optymalizacja planowania zastąpi istniejący wbudowany aparat planowania głównego aplikacji Supply Chain Management. |
| **Powiązane obszary produktów**         | Supply Chain Management — planowanie główne |
| **Opcja wdrażania**              | Tylko chmura. Optymalizacja planowania nie jest obsługiwana w przypadku wdrożeń lokalnych. |
| **Stan**                         | Wycofane. Do 1 kwietniu 2021 r. scenariusze dystrybucji nie będą już obsługiwane za pomocą wbudowanego aparatu planowania głównego aplikacji Dynamics 365 Supply Chain Management. W scenariuszach dystrybucji klienci muszą korzystać z optymalizacji planowania podczas obliczeń planowania głównego. Aby uzyskać więcej informacji, zobacz temat [Dokumentacja dotycząca optymalizacji planowania](https://go.microsoft.com/fwlink/?linkid=2105830). Klienci z wdrożeniami lokalnymi aplikacji Dynamics 365 Supply Chain Management będą mogli nadal korzystać z aparatu planowania głównego aplikacji Supply Chain Management w scenariuszach dystrybucji po kwietniu 2021 r. Nie będą jednak wprowadzane dodatkowe ulepszenia funkcji. |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Poprzednie oświadczenia o usuniętych lub wycofanych funkcjach

Aby dowiedzieć się więcej o funkcjach, które zostały usunięte lub wycofane w poprzednich wersjach, zobacz temat [Usunięte lub wycofane funkcje w poprzednich wersjach](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).
