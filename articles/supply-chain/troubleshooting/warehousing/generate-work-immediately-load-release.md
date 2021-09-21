---
title: Generowane pracy pobrania natychmiast po zwolnieniu ładunku
description: Jeśli praca musi zostać wygenerowana natychmiast po zwolnieniu ładunku, należy odpowiednio skonfigurować szablon grupy czynności. Ta strona zawiera informacje o krokach.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: fdeb0b27f4d2c1a2cc9f8e0c4ba537cdce604bd2
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477326"
---
# <a name="picking-work-isnt-generated-immediately-when-outbound-load-is-released"></a>Praca pobrania nie jest generowana natychmiast po zwolnieniu ładunku wychodzącego

## <a name="symptoms"></a>Objawy

Ładunek wychodzący tworzy się za pomocą zamówienia sprzedaży lub zamówienia przeniesienia i zwalnia go do magazynu. Zauważ jednak, że żadne prace pobrania nie zostały jeszcze wygenerowane.

## <a name="resolution"></a>Rozwiązanie

Jeśli praca musi zostać wygenerowana natychmiast po zwolnieniu ładunku, należy odpowiednio skonfigurować szablon grupy czynności. W szablonie grupy czynności ustaw następujące opcje na *Tak*:

- Automatyczne tworzenie grupy czynności
- Przetwarza grupę czynności w czasie uwalniania jej do magazynu
- Automatyczne uwolnienie grupy czynności
