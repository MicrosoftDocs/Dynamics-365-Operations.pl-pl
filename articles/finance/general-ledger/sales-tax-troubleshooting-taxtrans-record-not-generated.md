---
title: Nie jest generowany rekord TaxTrans
description: Ten temat zawiera informacje na temat rozwiązywania problemów, które mogą pomóc w przypadku niewygenerowania rekordu TaxTrans.
author: qire
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 82b00387e39b88e1ab2bc27d9dbc4e36aac3a7a605c04669171997ba236ae39a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751309"
---
# <a name="taxtrans-record-isnt-generated"></a>Nie jest generowany rekord TaxTrans

[!include [banner](../includes/banner.md)]

Jeśli wybierzesz opcję **Zaksięgowany podatek** dla transakcji, ale na stronie **Zaksięgowany podatek** albo nie ma wierszy podatku albo brakuje wiersza podatku, być może rekord **TaxTrans** nie został wygenerowany.

[![Strona Zaksięgowany podatek, która nie zawiera pozycji w wierszach.](./media/taxtrans-is-not-generated-Picture1.png)](./media/taxtrans-is-not-generated-Picture1.png)

W razie potrzeby wykonaj kroki opisane w poniższych sekcjach, aby rozwiązać ten problem.

## <a name="check-the-sales-tax-before-you-post-the-transaction"></a>Sprawdzenie podatku przed zaksięgowaniem transakcji

1. Przed zaksięgowaniem transakcji, na stronie **Księgowanie faktury** wybierz opcję **Podatek**, aby sprawdzić obliczenie.

    [![Przycisk Podatek na stronie Księgowanie faktury.](./media/taxtrans-is-not-generated-Picture2.png)](./media/taxtrans-is-not-generated-Picture2.png)

2. Na stronie **Tymczasowe transakcje podatkowe** przejrzyj wyniki obliczenia. Jeśli podatek nie jest obliczany, zobacz temat [Podatek nie jest obliczany lub kwota podatku wynosi zero](sales-tax-troubleshooting-tax-not-calculated-amount-zero.md).

## <a name="find-the-taxtrans-record-in-all-posted-sales-tax"></a>Znajdowanie rekordu TaxTrans we wszystkich zaksięgowanych podatkach

1. Wybierz kolejno opcje **Podatek** \> **Zapytania i raporty** \> **Zapytania o podatki** > **Zaksięgowany podatek**.
2. W nagłówku kolumny **Załącznik** wybierz symbol filtru, aby znaleźć rekord **TaxTrans**.
3. Jeśli znajdziesz rekordy podatku, których szukasz, sprawdź datę. Jeśli ta data różni się od daty nagłówka arkusza, utwórz żądanie obsługi do firmy Microsoft dotyczące dodatkowej pomocy technicznej.

    [![Strona zaksięgowany podatek.](./media/taxtrans-is-not-generated-Picture4.png)](./media/taxtrans-is-not-generated-Picture4.png)

## <a name="debug-to-check-details"></a>Debugowanie w celu sprawdzenia szczegółów

1. Aby uzyskać informacje dotyczące sposobu debugowania i określania, czy wartości **TmpTaxWorkTrans** i **TaxUncommitted** zostały poprawnie wygenerowane, zobacz temat [Niepoprawne wartości pola w rekordzie TaxTrans](sales-tax-troubleshooting-field-value-taxtrans-incorrect.md).
2. Jeśli **TaxTmpWorkTrans** lub **TaxUncommitted** został poprawnie wygenerowany, dodaj punkt przerwania w **TaxPost::SaveAndPost()** i **Tax::SaveAndPost**, aby debugować przyczynę niewstawienia rekordu **TaxTrans**.

    [![Punkty przerwania dodane w kodzie.](./media/taxtrans-is-not-generated-Picture5.png)](./media/taxtrans-is-not-generated-Picture5.png)

    [![Wyniki dodanych punktów przerwania.](./media/taxtrans-is-not-generated-Picture6.png)](./media/taxtrans-is-not-generated-Picture6.png)

## <a name="determine-whether-customization-exists"></a>Określanie, czy dostosowanie istnieje

Jeśli zostały wykonane kroki w poprzednich sekcjach, ale nie znaleziono problemu, określ, czy dostosowanie istnieje. Jeśli nie istnieją żadne dostosowania, utwórz żądanie obsługi do firmy Microsoft, aby uzyskać dalszą pomoc techniczną.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
