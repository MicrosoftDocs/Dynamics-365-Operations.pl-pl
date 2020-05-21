---
title: Usunięte lub wycofane funkcje w aplikacji Dynamics 365 Commerce
description: W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia z Dynamics 365 Commerce.
author: josaw
manager: AnnBe
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: c47c5430a8f5d67e13c95db609a95d5ad66933ae
ms.sourcegitcommit: a8b6cd799eddaf5be9aec9ea3c2b55e2c3231652
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/05/2020
ms.locfileid: "3335283"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-commerce"></a>Usunięte lub wycofane funkcje w aplikacji Dynamics 365 Commerce

[!include [banner](../includes/banner.md)]

W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia z Dynamics 365 Commerce.

- *Usunięta* funkcja nie jest już dostępna w produkcie.
- *Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.

Ta lista ma na celu ułatwienie uwzględnienia usuniętych i przestarzałych funkcji we własnym planowaniu. 

> [!NOTE]
> Szczegółowe informacje o obiektów w rozwiązaniu aplikacjach Finance and Operations można znaleźć w temacie [Raporty dotyczące odwołań technicznych](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Można porównać różne wersje tych raportów, aby dowiedzieć się więcej o obiektach, które zostały zmienione lub usunięte w poszczególnych wersjach aplikacji Finance and Operations.

## <a name="features-removed-or-deprecated-in-the-commerce-10010-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Commerce 10.0.10
### <a name="pos-operation-803---picking-and-receiving"></a>Operacja punktu sprzedaży 803 — pobranie i przyjęcie
|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Operacje pobrania i przyjęcia są uznawane za przestarzałe z powodu zmian w projekcie nowej operacji. |
| **Zamieniona przez inną funkcję?**   | Tak. Zastępują je dwie nowe operacje punktu sprzedaży: operacja przychodząca (804) i operacja wychodząca (805).|
| **Powiązane obszary produktów**         | Aplikacja punktu sprzedaży |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Przestarzałe: od wydania 10.0.10 operacja pobrania i przyjęcia nie będzie już otrzymywać żadnych nowych aktualizacji funkcji. W przyszłych wersjach dla tej operacji będą przeprowadzane tylko krytyczne poprawki usterek. Wszystkich klientów zachęcamy do przejścia do nowych [operacji przychodzących](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) i [operacji wychodzących](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation), które będą w dalszym ciągu częścią naszego długoterminowego planu rozwoju produktu. |


## <a name="features-removed-or-deprecated-in-the-commerce-1007-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Commerce 10.0.7
### <a name="commerce-getproductavailabilities-and-getavailableinventorynearby-apis"></a>Interfejsy API rozwiązania Commerce GetProductAvailabilities i GetAvailableInventoryNearby
|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Utworzono nowe zoptymalizowane interfejsy API w celu zastąpienia interfejsów API GetProductAvailabilities i GetAvailableInventoryNearby. |
| **Zamieniona przez inną funkcję?**   | Tak: zastępowane przez interfejsy API GetEstimatedAvailability i GetEstimatedProductWarehouseAvailability. |
| **Powiązane obszary produktów**         | Zestaw SDK aplikacji handlu elektronicznego |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Przestarzałe: w przypadku wydania 10.0.7 nie będą już obsługiwane inwestycje inżynieryjne dotyczące interfejsów API GetProductAvailabilities i GetAvailableInventoryNearby. Organizacje korzystające z tych interfejsów API we wdrożeniach handlu elektronicznego należy przekonwertować na nowe interfejsy API GetEstimatedAvailability i GetEstimatedProductWarehouseAvailability oraz włączyć [funkcję obliczania zoptymalizowanej dostępności produktów](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).  |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Poprzednie oświadczenia o usuniętych lub wycofanych funkcjach
Aby dowiedzieć się więcej o funkcjach, które zostały usunięte lub wycofane w poprzednich wersjach, zobacz temat [Usunięte lub wycofane funkcje w poprzednich wersjach](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).
