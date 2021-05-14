---
title: Wydajność obliczania podatku wpływa na transakcje
description: Ten temat zawiera informacje dotyczące rozwiązywania problemów związanych z wydajnością obliczeń podatku i ich wpływem na transakcje.
author: shtao
manager: beya
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 7ff9d9b80172c3b337737b1cd53b4c56d1befe57
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947695"
---
# <a name="tax-calculation-performance-affects-transactions"></a>Wydajność obliczania podatku wpływa na transakcje

[!include [banner](../includes/banner.md)]

Czasami na transakcję wpływają problemy z wydajnością dotyczące obliczania podatku. W razie potrzeby wykonaj kroki opisane w poniższych sekcjach, aby rozwiązać ten problem.

## <a name="review-the-transaction-line-count"></a>Weryfikacja liczby wierszy transakcji

Określ, czy transakcja ma dużą liczbę wierszy (na przykład więcej niż kilkaset). Jeśli nie, przejdź do następnej sekcji. Jeśli transakcja ma kilkaset wierszy, opóźnij obliczanie podatku. Aby uzyskać więcej informacji, zobacz temat [Włączanie opóźnionego obliczania podatku w arkuszach](enable-delayed-tax-calculation.md). 

Następnie można określić, czy któryś z poniższych warunków jest spełniony:

- Istnieją transakcje importu z dużych plików.
- W wielu sesjach jest jednocześnie przetwarzany ten sam podatek dla transakcji.
- Transakcja ma wiele wierszy, a widoki są aktualizowane w czasie rzeczywistym. Na przykład pole **Obliczona kwota podatku** na stronie **Arkusz ogólny** jest aktualizowane w czasie rzeczywistym, gdy pola wiersza uległy zmianie.

   [![Pole obliczonej kwoty podatku na stronie załącznika arkusza](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)

Jeśli którykolwiek z tych warunków jest spełniony, opóźnij obliczanie podatku.

## <a name="review-the-call-stack"></a>Przeglądanie stosu wywołań

Przejrzyj stos wywołań, aby określić, czy obliczanie podatku jest wywoływane wielokrotnie. Jeśli nie jest, przejdź do następnej sekcji. Jeśli stos wywołań jest wywoływany wielokrotnie, należy wykonać następujące kroki, aby skrócić czas obliczania podatku.

1. Jeśli arkusz uwzględnia transakcję, opóźnij obliczanie podatku. Aby uzyskać więcej informacji, zobacz temat [Włączanie opóźnionego obliczania podatku w arkuszach](enable-delayed-tax-calculation.md).
2. Jeśli transakcja jest zamówieniem zakupu, a wersja aplikacji jest nowsza niż 10.0.15, można opóźnić obliczanie podatku do czasu ostatecznego obliczenia, włączając flighting **PurchTableChangeMgmtDistributionUpdateOnToggle_KillSwitch**.

## <a name="review-the-call-stack-timeline"></a>Przeglądanie osi czasu stosu wywołań

Przejrzyj oś czasu stosu wywołań, aby określić, czy istnieją następujące problemy. Jeśli tak, włącz flighting **TaxUncommittedDoIsolateScopeFlighting**, aby rozwiązać ten problem.

- Transakcja powoduje, że system zawiesza się do końca sesji. W związku z tym transakcja nie może obliczyć wyniku podatku. Na poniższej ilustracji przedstawiono odbierane okno komunikatu „Sesja zakończona”.

    [![Komunikat o zakończeniu sesji](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)

- Metody **TaxUncommitted** zabierają więcej czasu niż inne metody. Na przykład na poniższej ilustracji metoda **TaxUncommitted::updateTaxUncommitted()** zabiera 43 347,42 sekundy, a inne metody tylko 0,09 sekundy.

    [![Czasy trwania metod](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)

## <a name="customizing-and-calling-tax-calculation"></a>Dostosowywanie i wywoływanie obliczeń podatku

Podczas dostosowywania nie należy wywołać obliczania przy metodzie **insert()** lub **update()** w każdym wierszu. Obliczanie podatku powinno być wywoływane na poziomie transakcji.

## <a name="determine-whether-customization-exists"></a>Określanie, czy dostosowanie istnieje

Jeśli zostały wykonane kroki w poprzednich sekcjach, ale nie znaleziono problemu, określ, czy dostosowanie istnieje. Jeśli nie istnieją żadne dostosowania, utwórz żądanie obsługi do firmy Microsoft, aby uzyskać dalszą pomoc techniczną.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
