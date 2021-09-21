---
title: Nie można przenieść numeru identyfikacyjnego, jeśli jest dozwolone puste wydanie i puste przyjęcie
description: Nie można przenieść numeru identyfikacyjnego, jeśli numer seryjny ma dozwolone puste wydanie i puste przyjęcie. Zostanie to naprawione przez użycie opcjonalnego pola numeru seryjnego.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0047f79aa417c8fc910447505f07963d014f54e7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477300"
---
# <a name="cant-move-license-plate-if-serial-number-has-blank-issue-and-blank-receipt-allowed"></a>Nie można przenieść numeru identyfikacyjnego, jeśli numer seryjny ma dozwolony pusty rozchód i pusty przychód

## <a name="symptoms"></a>Objawy

Nie można przenieść numeru identyfikacyjnego za pomocą elementu menu **przesunięcia**, jeśli numer seryjny zawiera ustawienia *Dozwolone puste wydanie* i *Dozwolone puste przyjęcie* dla grupy wymiarów śledzenia, i jeśli w tej samej lokalizacji znajduje się wiele numerów identyfikacyjnych, z których niektóre mają numery seryjne, a niektóre nie.

## <a name="resolution"></a>Rozwiązanie

Ten problem zostanie rozwiązany przez wprowdzane zmiany [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687). Wprowadzenie tych zmian powoduje, że pole **numeru seryjnego** będzie opcjonalne, jeśli są dozwolone puste przyjęcie i puste wydanie.
