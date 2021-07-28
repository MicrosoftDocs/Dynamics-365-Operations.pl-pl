---
title: Podatek nie został obliczony lub kwota podatku wynosi zero
description: Ten temat zawiera informacje na temat rozwiązywania problemów, które mogą pomóc w sytuacji, gdy kwota podatku wynosi 0 (zero) lub podatek nie został obliczony.
author: shtao
ms.date: 04/01/2021
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
ms.openlocfilehash: c731e0284b720394059384e21deea1ea4407718c
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6352817"
---
# <a name="tax-isnt-calculated-or-the-tax-amount-is-zero"></a>Podatek nie został obliczony lub kwota podatku wynosi zero

[!include [banner](../includes/banner.md)]

Transakcja może zawierać kwotę wiersza różną od 0 (zero), ale nie obliczono podatku albo obliczona kwota podatku wynosi 0. W razie potrzeby wykonaj kroki opisane w poniższych sekcjach, aby rozwiązać ten problem.

## <a name="verify-that-tax-codes-are-correctly-selected-by-the-transaction"></a>Sprawdzanie, czy kody podatku są poprawnie wybrane przez transakcję

Jeśli transakcja nie wybierze poprawnych kodów podatków lub nie wybierze żadnych kodów podatków, podatki od niej nie będą obliczane. Wykonaj następujące kroki, aby sprawdzić, czy kody podatku są poprawnie wybrane przez transakcję. 

1. W wierszu transakcji, na skróconej karcie **Szczegóły wiersza**, na karcie **Ustawienia**, w sekcji **Podatek** sprawdź, czy w polach **Grupa podatków dla towaru** i **Grupa podatków** zostały wybrane poprawne grupy podatków. Jeśli nie wybrano prawidłowych grup podatków, należy je wybrać.

    [![Pola Grupa podatków dla towaru i Grupa podatków.](./media/tax-not-calculated-tax-amount-zero-Picture1.png)](./media/tax-not-calculated-tax-amount-zero-Picture1.png)

2. Wybierz kolejno opcje **Podatek** \> **Podatki pośrednie** \> **Podatek** \> **Grupy podatków**.
3. Wybierz odpowiednią grupę podatków, a następnie na skróconej karcie **Ustawienia** zanotuj kod podatku w polu **Kod podatku**.

    [![Strona Grupy podatków.](./media/tax-not-calculated-tax-amount-zero-Picture2.png)](./media/tax-not-calculated-tax-amount-zero-Picture2.png)

4. Wybierz kolejno opcje **Podatek** \> **Podatki pośrednie** \> **Podatek** \> **Grupy podatków dla towaru**.
5. Wybierz odpowiednią grupę podatków dla towaru, a następnie na skróconej karcie **Ustawienia** sprawdź, czy kod podatku w polu **Kod podatku** odpowiada kodowi podatku grupy podatków.

    [![Strona Grupy podatków dla towaru.](./media/tax-not-calculated-tax-amount-zero-Picture3.png)](./media/tax-not-calculated-tax-amount-zero-Picture3.png)

6. Jeśli kody podatków są różne, zaktualizuj kod podatku jednej z grup.

## <a name="verify-that-the-selected-tax-codes-arent-exempt-and-that-they-have-the-correct-tax-rate-value"></a>Sprawdź, czy wybrane kody podatków nie podlegają zwolnieniu z podatku i mają prawidłową wartość stawki podatku

Jeśli kody podatków są zwolnione lub stawka podatku wynosi 0 (zero), wynikiem obliczenia podatku będzie 0. Aby sprawdzić, czy wybrane kody podatków są zwolnione z podatku i czy jest do nich stosowana właściwa stawka podatku, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Podatek** \> **Podatki pośrednie** \> **Podatek** \> **Grupy podatków**.
2. Wybierz odpowiednią grupę podatków, a następnie na skróconej karcie **Ustawienia** sprawdź, czy pole wyboru **Zwolnienie** nie jest zaznaczone. Jeśli jest zaznaczone, usuń jego zaznaczenie.

    [![Pole wyboru Zwolnienie na stronie Grupy podatków.](./media/tax-not-calculated-tax-amount-zero-Picture4.png)](./media/tax-not-calculated-tax-amount-zero-Picture4.png)

3. Wybierz kolejno opcje **Podatek** \> **Podatki pośrednie** \> **Podatek** \> **Kody podatków**.
4. Wybierz odpowiedni kod podatku, a następnie sprawdź, czy wartość stawki podatku w polu **Wartość** nie jest równa 0 (zero). Jeśli wynosi 0, należy zaktualizować to pole, tak aby było ustawione na poprawną stawkę podatku.

    [![Pole Wartość na stronie Wartości kodu podatku.](./media/tax-not-calculated-tax-amount-zero-Picture5.png)](./media/tax-not-calculated-tax-amount-zero-Picture5.png)

## <a name="determine-whether-zero-is-the-correct-tax-amount"></a>Określanie, czy zero jest poprawną kwotą podatku

W niektórych scenariuszach kwota podatku 0 (zero) jest poprawna. Aby określić, czy wartość 0 jest właściwą kwotą podatku dla transakcji, należy wykonać następujące kroki.

1. Przejdź do pozycji **Księga główna** \> **Ustawienia księgi** \> **Parametry księgi głównej**.
2. Sprawdź, czy wybrano wartość **Suma** na karcie **Podatek** w polu **Metoda obliczania**.

    [![Pole Metoda obliczania na stronie Parametry księgi głównej.](./media/tax-not-calculated-tax-amount-zero-Picture6.png)](./media/tax-not-calculated-tax-amount-zero-Picture6.png)

3. Wybierz kolejno opcje **Podatek** \> **Podatki pośrednie** \> **Podatek** \> **Kody podatków**.
4. Wybierz odpowiedni kod podatku, wybierz opcje **Obliczanie** \> **Podstawa limitu** i sprawdź, czy podstawa limitu jest ustawiona na wartość **Kwota netto faktury** lub **Kwota faktury z innymi podatkami**. Aby uzyskać więcej informacji, zobacz temat [Suma faktury z innymi podatkami](marginal-base-field.md#invoice-total-incl-other-sales-tax-amounts).
5. Jeśli w krokach 2 i 4 określone są poprawne wartości, należy określić, czy łączna kwota transakcji wynosi 0 (zero). Jeśli łączna kwota wynosi 0, należy oczekiwać kwoty podatku w wysokości 0. Ponieważ obliczenie podatku jest oparte na łącznej kwocie salda faktury i ta kwota nie jest wiersz po wierszu, kwota podatku w wysokości 0 zostanie przydzielona do każdego wiersza po obliczeniu podatku.

## <a name="determine-whether-customization-exists"></a>Określanie, czy dostosowanie istnieje

Jeśli zostały wykonane kroki w poprzednich sekcjach, ale nie znaleziono problemu, określ, czy dostosowanie istnieje. Jeśli nie istnieją żadne dostosowania, utwórz żądanie obsługi do firmy Microsoft, aby uzyskać dalszą pomoc techniczną.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
