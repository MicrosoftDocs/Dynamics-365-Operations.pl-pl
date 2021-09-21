---
title: Nie można usunąć zwolnionego produktu
description: Zwolniony produkt i wszystkie jego warianty można usunąć tylko w przypadku, gdy zwolniony produkt nie ma żadnych powiązanych transakcji.
author: SmithaNataraj
ms.date: 06/11/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 2f03d45a36401314a4b02ff354fabb474568c48b
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477340"
---
# <a name="you-cant-delete-a-released-product"></a>Nie można usunąć zwolnionego produktu

## <a name="symptoms"></a>Objawy

Zwolniony produkt i wszystkie jego warianty można usunąć tylko w przypadku, gdy zwolniony produkt nie ma żadnych powiązanych transakcji.

## <a name="resolution"></a>Rozwiązanie

Aby usunąć zwolniony produkt lub produkt główny, należy wykonać następujące kroki.

1. Zamknij wszystkie otwarte transakcji dla towarów.
1. Zmniejsz ilość zapasów do 0 (zera).
1. Przeprowadź zamknięcie zapasów.
1. Usuń wszystkie warianty produktu dla produktu głównego, który chcesz usunąć.
