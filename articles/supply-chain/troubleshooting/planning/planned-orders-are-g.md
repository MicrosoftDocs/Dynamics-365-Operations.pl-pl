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
ms.openlocfilehash: 1ea4bdb3729d163126234e02524cef331051cd48
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026820"
---
# <a name="master-planning-generates-planned-orders-for-phantom-products"></a>Planowanie główne generuje planowane zamówienia na produkty fantomu

Numer artykułu z bazy wiedzy: 4614729

## <a name="symptoms"></a>Objawy

Planowane zamówienia są generowane na produkty pozorne po uruchomieniu planowania głównego.

## <a name="resolution"></a>Rozdzielczość

Ustawienie opcji **Fantom** dla zwolnionych produktów określa domyślny typ wiersza w BOM. Jeśli w ustawieniach opcji **Fantom** jest ustawiona wartość *Tak*, system nadal będzie tworzyć planowane zamówienia dla towaru, ale opcja **Zapotrzebowanie pochodne bezpośrednie** dla każdego planowanego zamówienia będzie mieć wartość *Tak*. W związku planowane zlecenie produkcyjne nie można jej samodzielnie określić. Będzie ona natomiast zawsze uwzględniana automatycznie podczas procesów języdzyka produkcyjnego. Ponadto wiersze BOM planowanego zamówienia fantomu zostaną uwzględnione w BOM nadrzędnego zlecenia produkcyjnego.
