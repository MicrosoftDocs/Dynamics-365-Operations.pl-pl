---
# required metadata
title: Dodaj typy kwot płatności
description: 'W tym temacie wyjaśniono, jak skonfigurować rodzaje kwot płatności w leasingu aktywów.'
author: moaamer
ms.date: 01/11/2022
ms.topic: article
ms.prod: null
ms.technology: null
ms.search.form: AssetLeaseIndexRevaluation
audience: Application User
ms.reviewer: twheeloc
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: '2020-10-28'
ms.dyn365.ops.version: 10.0.14
---

# <a name="add-payment-amount-types"></a>Dodaj typy kwot płatności

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak skonfigurować rodzaje kwot płatności w leasingu aktywów. W ten sposób można popisać kwotę płatności dzierżawy zamiast dodawać kwotę ryczałtu do wierszy harmonogramu płatności.

Aby dodać typy kwot płatności, wykonaj następujące czynności.

1. Przejdź do **Wynajem składnika majątku \> Ustawienia \> Rodzaje kwoty płatności**.
2. Wybierz pozycję **Nowy**.
3. Wprowadź nowy typ płatności i opis.

> [!NOTE]
> W przypadku przesądu indeksu IFRS 16 należy utworzyć jeden typ kwoty płatności i oznaczyć go jako **Używany w przesyłce indeksu IRFS 16**. Ten typ kwoty płatności będzie używany, gdy proces przesyłania indeksu jest uruchamiany względem księgi IFRS 16 i będzie uwzględniał zmiany, które wystąpiły w procesie przesądu indeksu.
>
> Jeśli dla opcji **podziału płatności** w dzierżawie jest ustawiona wartość **Tak**, to jeśli zostanie uruchomione przesunienie indeksu dla IFRS 16, ale dla usługi IFRS 16 nie ma typu płatności, proces nie zostanie ukończony.

Rekord zostanie oznaczony jako **Używany dla przesądu indeksu IFRS 16**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
