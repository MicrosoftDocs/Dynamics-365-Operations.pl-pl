---
title: Zamówienia zakupu nie odzwierciedlają ustawień języka osoby prawnej
description: Nazwa produktu w zamówieniu zakupu jest wyświetlana w wersji językowej systemu, a nie w języku określonym dla firmy, w której utworzono zamówienie zakupu
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 4deec493b5480dc570ac82876243bc31a2ae87aa
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477297"
---
# <a name="purchase-orders-dont-reflect-the-language-settings-of-the-legal-entity"></a>Zamówienia zakupu nie odzwierciedlają ustawień języka osoby prawnej


## <a name="symptoms"></a>Objawy

Nazwa produktu w zamówieniu zakupu jest wyświetlana w wersji językowej systemu, a nie w języku określonym dla firmy, w której utworzono zamówienie zakupu.

## <a name="reproduce-the-issue"></a>Odtwórz ten błąd

Poniższa procedura przedstawia jeden ze sposobów odtworzenia błędu.

1. Określ język systemowy jako *EN-US* (Język angielski Stany Zjednoczone).
1. Upewnij się, że istnieje produkt, w którym obsługiwane są języki *EN-US* i *DE* (Niemiecki) dla tłumaczeń nazw produktów.
1. Zmień język firmy na *DE*.
1. W firmie, w której jako język jest ustawiona wartość *DE*, utwórz zamówienie zakupu zawierające produkt.
1. Zauważ, że nazwa produktu nadal jest wyświetlana w języku angielskim, USA (język systemowy).

## <a name="resolution"></a>Rozwiązanie

Jest to celowe. W przypadku zamówień zakupu produkt jest zawsze pokazywany w wersji językowej systemu. Język zamówienia zakupu jest używany podczas tworzenia arkusza potwierdzeń.
