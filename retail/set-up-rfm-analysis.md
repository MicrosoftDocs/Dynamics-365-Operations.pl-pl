---
title: "Ustaw analizę RFM"
description: "W tym temacie omówiono konfigurowanie analizy ostatniego zakupu, częstotliwości i wartości pieniężnej (RFM) dla odbiorców."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 78943
ms.assetid: 8ff9aac3-5ada-4150-85fd-18901c926d53
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: b95d2c4d7d78e8c5ed8d3a04efdd2f8dfe8393ba
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-rfm-analysis"></a>Ustaw analizę RFM

[!include[banner](includes/banner.md)]


W tym temacie omówiono konfigurowanie analizy ostatniego zakupu, częstotliwości i wartości pieniężnej (RFM) dla odbiorców.

Analiza RFM (wg daty ostatniego zakupu, częstotliwości i wartości pieniężnej) to narzędzie marketingowe, które organizacja może używać do oceny danych generowanych przez zakupy. Po skonfigurowaniu analizy RFM, do odbiorców przypisywana jest obliczona punktacja RFM według wykonanych zakupów. Punktacja RFM może być trzycyfrową oceną lub sumę liczbową, zależnie od sposobu skonfigurowania analizy RFM przez organizację. Jeśli w firmie jest używana trzycyfrowa ocena wyniku, pierwsza cyfra oznacza ocenę odbiorcy według daty ostatniego zakupu. Druga wartość to ocena częstotliwości odbiorcy (tj. jak często odbiorca dokonuje zakupów od organizacji). Trzecia cyfra to ocena wartości pieniężnej odbiorcy (tj. ile pieniędzy odbiorca wydaje, gdy kupuje towary w Twojej firmie). Załóżmy, że w Twojej firmie używana jest skala ocen od 1 do 5, gdzie 5 oznacza najwyższą ocenę. W tym przypadku jeśli odbiorca otrzymał ocenę 535, można z tego wywnioskować następujące fakty:

-   **Ocena daty ostatniego zakupu 5** — ostatni zakup dokonany przez odbiorcę miał miejsce niedawno.
-   **Ocena częstotliwości 3** — odbiorca kupuje produkty od organizacji z średnią częstotliwością.
-   **Ocena wartości pieniężnej 5** — gdy odbiorca dokonuje zakupu, wydaje znaczną kwotę pieniędzy.

Jeśli organizacja używa sum liczbowych do określania wyniku, poszczególne wyniki są sumowane. Jeśli weźmiemy jeszcze raz ten sam przykład, odbiorca otrzymuje ocenę 13 (5 + 3 + 5).




