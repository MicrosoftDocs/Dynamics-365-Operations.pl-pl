---
title: Planowanie główne generuje planowane zamówienia na produkty fantomu
description: Planowane zamówienia są generowane na produkty pozorne po uruchomieniu planowania głównego.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: anderso
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: f3170bcb723e2d7483258bb0ecf786e62f2aa3d196745074c2ac554bc212ec55
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742011"
---
# <a name="master-planning-generates-planned-orders-for-phantom-products"></a>Planowanie główne generuje planowane zamówienia na produkty fantomu

Numer artykułu z bazy wiedzy: 4614729

## <a name="symptoms"></a>Objawy

Planowane zamówienia są generowane na produkty pozorne po uruchomieniu planowania głównego.

## <a name="resolution"></a>Rozdzielczość

Ustawienie opcji **Fantom** dla zwolnionych produktów określa domyślny typ wiersza w BOM. Jeśli w ustawieniach opcji **Fantom** jest ustawiona wartość *Tak*, system nadal będzie tworzyć planowane zamówienia dla towaru, ale opcja **Zapotrzebowanie pochodne bezpośrednie** dla każdego planowanego zamówienia będzie mieć wartość *Tak*. W związku planowane zlecenie produkcyjne nie można jej samodzielnie określić. Będzie ona natomiast zawsze uwzględniana automatycznie podczas procesów języdzyka produkcyjnego. Ponadto wiersze BOM planowanego zamówienia fantomu zostaną uwzględnione w BOM nadrzędnego zlecenia produkcyjnego.
