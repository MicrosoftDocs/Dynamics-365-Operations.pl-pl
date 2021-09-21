---
title: Nie można ponownie zwolnić częściowo wysłanego ładunku do magazynu
description: We wcześniejszych wersjach nie można ponownie zwolnić częściowo wysłanego ładunku przy użyciu pewnych funkcji z niekompletnymi rezerwacjami. Ten problem został rozwiązany.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0380e1963a38f2be55b31e06b3845f935661eed2
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477325"
---
# <a name="cant-re-release-a-partially-shipped-load-to-the-warehouse"></a>Nie można ponownie zwolnić częściowo wysłanego ładunku do magazynu

## <a name="symptoms"></a>Objawy

Nie można zwolnić częściowo wysłanego ładunku do magazynu. Po wydaniu do magazynu pojawia się komunikat „Operacja zakończona”, ale nic się nie dzieje i nie jest tworzona praca dla pozostałej ilości. Ten problem występuje, gdy używasz funkcji transportu ładunku i istnieje niekompletna rezerwacja.

## <a name="resolution"></a>Rozwiązanie

[KB problem 470069](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) („Częściowo wysłane ładunki można ponownie pogrupować w grupy czynności i ponownie przetworzyć”) został naprawiony w [wydaniu 10.0.15](/dynamics365/supply-chain/get-started/whats-new-scm-10-0-15).
