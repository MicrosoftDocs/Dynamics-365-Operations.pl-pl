---
title: Zadania w toku są kończone podczas zgłaszania ilości częściowej dla ostatniego zadania
description: Kiedy używasz urządzenia karty pracy do zgłaszania ilości częściowej dla ostatniego zlecenia w zleceniu produkcyjnym, wszystkie poprzednie zadania, które mają stan W toku, są kończone.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 11511d4ac7524facdd0d647e9bc38fe09c282be1
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477350"
---
# <a name="previous-in-progress-jobs-are-ended-when-reporting-partial-quantity-on-last-job"></a>Poprzednie zadania w toku są kończone podczas zgłaszania ilości częściowej dla ostatniego zadania

## <a name="symptoms"></a>Objawy

Kiedy używasz urządzenia karty pracy do zgłaszania ilości częściowej dla ostatniego zlecenia w zleceniu produkcyjnym, wszystkie poprzednie zadania w tym zamówieniu, które mają stan W toku, są automatycznie kończone.

## <a name="resolution"></a>Rozwiązanie

Jest to celowe. Na stronie **Ustawienia domyślne zlecenia produkcyjnego** na karcie **Zgłoszenie wyrobów gotowych** istnieje opcja o nazwie **Znacznik końcowy trasy**. Jeśli w tym temacie jest ustawiona wartość *Tak*, arkusz karty trasy jest księgowany, gdy pracownik korzysta z terminalu karty zadań lub urządzenia karty zadań w celu zgłoszenia ostatniej operacji. Ten arkusz oznacza wszystkie operacje jako zakończone i kończy wszystkie zadania produkcyjne. Jeśli dla opcji **Znacznik końcowy trasy** jest ustawiona wartość *Tak*, system nie będzie traktować stanu zadania wybranego przez pracownika podczas raportowania ostatniej operacji. System nie bierze również pod uwagę, czy pracownik zgłasza ilość pełną czy częściową.
