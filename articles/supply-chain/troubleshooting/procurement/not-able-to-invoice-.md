---
title: Nie można zafakturć zamówienia sprzedaży dla odbiorcy
description: Po włączeniu opcji Automatyczne księguj fakturę nie można już zafakturowania oryginalnego zamówienia sprzedaży i zamówienia zakupu z oryginalną dostawą bezpośrednią.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: SalesEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ab18a2a1dec4b70c55a55637b087c6b11023aa40
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026809"
---
# <a name="you-cant-invoice-a-customer-facing-sales-order"></a>Nie można zafakturć zamówienia sprzedaży dla odbiorcy

Numer artykułu z bazy wiedzy: 4611793

## <a name="symptoms"></a>Objawy

Po włączeniu opcji **Automatyczne księgowanie faktury** na stronie **Międzyfirmowe** dla dostawcy nie można już fakturować oryginalnego zamówienia sprzedaży i oryginalnego zamówienia zakupu z dostawą bezpośrednią.

## <a name="resolution"></a>Rozdzielczość

Zachowanie synchronizacji dla faktur międzyfirmowych i faktur z zamówieniem dostawy bezpośredniej jest kontrolowane i wymuszane przez parametry opisane w sekcji [Konfigurowanie parametrów w celu zaksięgowania zamówienia międzyfirmowego](/dynamicsax-2012/appuser-itpro/set-up-parameters-to-post-an-intercompany-order).

Po skonfigurowaniu tych parametrów należy najpierw międzyfirmowe zamówienie sprzedaży fakturę. Oryginalne zamówienia sprzedaży i zakupu zostaną zsynchronizowane.
