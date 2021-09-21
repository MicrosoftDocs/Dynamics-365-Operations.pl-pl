---
title: Podczas planowania produkcji nie są rozważane marginesy bezpieczeństwa
description: Planowanie produkcji nie uwzględnia marginesów bezpieczeństwa, które są ustawione dla pokrycia pozycji dla ustalonej dostawy
author: ChristianRytt
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 738296b7570ded0a4ee806e4445204a68e6a08c8
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477287"
---
# <a name="production-scheduling-doesnt-consider-the-safety-margins"></a>Podczas planowania produkcji nie są rozważane marginesy bezpieczeństwa

## <a name="symptoms"></a>Objawy

Planowanie główne uwzględnia marginesy bezpieczeństwa. Jednak marginesy bezpieczeństwa są ignorowane podczas planowania zaplanowanych zleceń produkcyjnych.

## <a name="resolution"></a>Rozwiązanie

Marginesy są brane pod uwagę tylko podczas planowania głównego, a nie w planowaniu ręcznym. Marginesy są tak zaprojektowane, aby pełniły charakter buforu podczas fazy planowania, co umożliwia podanie pewnego „marginesu” dla właściwego procesu.

Aby uzyskać pożądany wynik, można usunąć margines. Następnie należy zaktualizować marszrutę, aby obejmowała ona żądany czas (np. jako czas oczekiwania). Zarówno planowanie główne, jak i planowanie ręczne, powinny dawać ten sam wynik.
