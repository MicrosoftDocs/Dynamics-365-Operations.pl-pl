---
title: Planowanie główne planuje więcej niż dostępne zdolności produkcyjne
description: Wydaje się, że planowanie główne nie uwzględnia ograniczeń zdolności produkcyjnej i obejmuje planowanie większe niż dostępna zdolność produkcyjna
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
ms.openlocfilehash: 48b3d179bb923ff6f6cc5b6be291408b3eb34d98
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477322"
---
# <a name="master-planning-is-scheduling-more-than-the-available-capacity"></a>Planowanie główne planuje więcej niż dostępne zdolności produkcyjne

## <a name="symptoms"></a>Objawy

Wydaje się, że planowanie główne nie uwzględnia ograniczeń zdolności produkcyjnej i obejmuje planowanie większe niż dostępna zdolność produkcyjna.

W przypadku korzystania z planowania operacji w przypadku, gdy wydajność jest ograniczona, a trasa określa mieszankę wymagań zarówno dla grupy zasobów, jak i dla poszczególnych zasobów, istnieje niewielka szansa na przepełnienie rezerwacji ze względu na sposób, w jaki algorytm sprawdza poprawność pod kątem konfliktów pojemności. Taka rezerwacja ponad możliwości może wystąpić podczas używania pomocników w celu uruchomienia planowania głównego. Najprawdopodobniej dzieje się tak, jeśli istnieje wiele zadań o stosunkowo krótkim czasie wykonywania.

## <a name="resolution"></a>Rozwiązanie

Jeśli konieczne jest, aby w planowaniu operacji nie dochodziło do przepełnienia rezerwacji, można uczynić planowanie jednowątkową częścią planowania głównego, włączając opcję **Dokładne ograniczone zdolności produkcyjne do planowania operacji** na stronie **Parametry planowania głównego**. Ta opcja jest domyślnie niedostępna. Musisz ręcznie dodać ją do strony, używając funkcji personalizacji. W przypadku korzystania z tej opcji planowanie będzie działać wolniej z powodu braku równoległego przetwarzania.
