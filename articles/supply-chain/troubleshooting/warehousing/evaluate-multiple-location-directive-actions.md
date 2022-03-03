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
ms.openlocfilehash: 2d5f7cf548eb6c18d9700c73ef084f197b78542e
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/09/2022
ms.locfileid: "8102970"
---
# <a name="multiple-sku-option-doesnt-evaluate-multiple-location-directive-actions"></a>Opcja wielu SKU nie ocenia wielu akcji dyrektyw lokalizacji

## <a name="symptoms"></a>Objawy

Dyrektywy lokalizacji typu zlecenia pracy *Zamówienia sprzedaży* i typu pracy *Odłożenie* nie oceniają wielu działań dyrektywy lokalizacji, gdy wybrana jest opcja **Wiele jednostek SKU**. Sprawdzana jest tylko akcja dyrektywy pierwszej lokalizacji.

## <a name="resolution"></a>Rozwiązanie

Nowa funkcja *Oceń wszystkie akcje dla dyrektyw lokalizacji dla wielu jednostek SKU* została dodana w wersji 10.0.15 (zobacz [4579866 KB](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)). Ta funkcja ocenia wszystkie akcje dyrektyw lokalizacji w wielu jednostkach SKU. Od wersji 10.0.21 Supply Chain Management version ta funkcja jest domyślnie włączona.  Od wersji 10.0.25 Supply Chain Management ta funkcja jest obowiązkowa i nie można jej wyłączyć. Administratorzy mogą skorzystać ze strony [Zarządzania funkcją](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją lub wyłączyć w razie potrzeby.
