---
title: Ocenianie wszystkich akcji dla dyrektyw lokalizacji wielu jednostek SKU
description: Dodano nową funkcję w celu oceniania wszystkich akcji dla wielu dyrektyw lokalizacji jednostek SKU. Ta strona zawiera informacje dotyczące sposobu jej włączania.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 45995ed6f051cdf6be2b2985ff0e2cb1decf4cf0
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477291"
---
# <a name="multiple-sku-option-doesnt-evaluate-multiple-location-directive-actions"></a>Opcja wielu SKU nie ocenia wielu akcji dyrektyw lokalizacji

## <a name="symptoms"></a>Objawy

Dyrektywy lokalizacji typu zlecenia pracy *Zamówienia sprzedaży* i typu pracy *Odłożenie* nie oceniają wielu działań dyrektywy lokalizacji, gdy wybrana jest opcja **Wiele jednostek SKU**. Sprawdzana jest tylko akcja dyrektywy pierwszej lokalizacji.

## <a name="resolution"></a>Rozwiązanie

Nowa funkcja *Oceń wszystkie akcje dla dyrektyw lokalizacji dla wielu jednostek SKU* została dodana w wersji 10.0.15 (zobacz [4579866 KB](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)). Ta funkcja ocenia wszystkie akcje dyrektyw lokalizacji w wielu jednostkach SKU. Jeśli ta funkcja jest wymagana, należy skorzystać [Zarządzanie funkcjami](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview), aby ją włączyć.
