---
title: Bezpośrednie pochodne zamówienia firmowe są przetwarzane w przepływie pracy w przeglądzie
description: Bezpośrednio wyprowadzone zamówienia potwierdzone są przetwarzane przez przepływ pracy, który ma stan W trakcie przeglądu.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: d20f1c1d6e8fc83dd996b04bf0321a41f7b39290f306d1ac9f4fcd17514832e6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6721182"
---
# <a name="directly-derived-firmed-orders-are-processed-by-an-in-review-workflow"></a>Bezpośrednie pochodne zamówienia firmowe są przetwarzane w przepływie pracy w przeglądzie

Numer artykułu z bazy wiedzy: 4612450

## <a name="symptoms"></a>Objawy

Bezpośrednio wyprowadzone zamówienia potwierdzone są przetwarzane przez przepływ pracy, który ma stan *W trakcie przeglądu*.

## <a name="resolution"></a>Rozdzielczość

Gdy włączone jest śledzenie zmian, do zatwierdzonych zamówień pochodnych (zamówienia podwykonawstwa) przypisywany jest status *W trakcie przeglądu*. W związku z tym, jeśli zamówienie zakupu jest pochodne (zamówienie zakupu dla podumowy), jest przesyłane tylko do przepływu pracy. Jeśli zamówienie zakupu jest zaakceptowane planowane zamówienie zakupu, jest ono automatycznie zatwierdzane w celu zapewnienia, że aparat planowania nie będzie tworzyć nowych zamówień planowanych, dopóki zamówienie zakupu ma nadal stan *Wersja robocza*.
