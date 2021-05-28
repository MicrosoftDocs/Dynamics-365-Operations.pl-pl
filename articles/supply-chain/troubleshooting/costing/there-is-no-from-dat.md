---
title: Brak wartości Od dnia na karcie Aktywne ceny na stronie Cena pozycji
description: Brak wartości Od dnia na karcie Aktywne ceny na stronie Cena pozycji.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3dd13f6a3e5ce3c894e96f420358d337f2e43dba
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026828"
---
# <a name="there-is-no-from-date-value-on-the-active-prices-tab-of-the-item-price-page"></a>Brak wartości Od dnia na karcie Aktywne ceny na stronie Cena pozycji

Numer artykułu z bazy wiedzy: 4613548

## <a name="symptoms"></a>Objawy

Brak wartości **Od dnia** na karcie **Aktywne ceny** na stronie **Cena pozycji**.

## <a name="resolution"></a>Rozdzielczość

Wartość **Od dnia** (data wejścia w życie) ustawiona dla ceny oczekującej nie jest przeniesiona do aktywnej ceny.

Rekord kosztu towaru początkowo jest wprowadzany ze stanem *Oczekujący* oraz zamierzoną datą wprowadzenia. Aktywacja rekordu kosztu towaru aktualizuje stan (do wartości *Aktywny*)i datę wprowadzenia (do daty aktywacji). Dlatego data aktywacji aktywnej ceny jest zawsze rzeczywistą datą aktywacji.

Aby uzyskać więcej informacji, zobacz temat [Omówienie wersji wyceny](../../cost-management/costing-versions.md).
