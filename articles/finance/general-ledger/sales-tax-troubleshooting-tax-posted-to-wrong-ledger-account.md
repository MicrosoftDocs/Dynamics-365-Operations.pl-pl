---
title: Podatek jest księgowany na niewłaściwym koncie księgowym w załączniku
description: Ten temat zawiera informacje na temat rozwiązywania problemów, które mogą pomóc przy księgowanie podatku na niewłaściwym koncie księgowym w załączniku.
author: qire
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 9c9f3fc63374b185a795977566cf73c8c29ee5d3
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686443"
---
# <a name="tax-is-posted-to-the-wrong-ledger-account-in-the-voucher"></a>Podatek jest księgowany na niewłaściwym koncie księgowym w załączniku

[!include [banner](../includes/banner.md)]

Podczas księgowania podatek może być księgowany na niewłaściwym koncie księgowym w załączniku. W razie potrzeby wykonaj kroki opisane w poniższych sekcjach, aby rozwiązać ten problem. W przykładach w tym temacie jako dokument biznesowy przyjmuje się zamówienie sprzedaży.

## <a name="find-the-tax-code-of-the-incorrectly-posted-tax-transaction"></a>Znajdowanie kodu podatku niepoprawnie zaksięgowanej transakcji podatkowej

1. Na stronie **Transakcje na załączniku** wybierz transakcję, którą chcesz się zajmować, a następnie wybierz pozycję **Zaksięgowany podatek**.

    [![Przycisk Zaksięgowany podatek na stronie Transakcje na załączniku.](./media/tax-posted-to-wrong-ledger-account-Picture1.png)](./media/tax-posted-to-wrong-ledger-account-Picture1.png)

2. Przejrzyj wartość w polu **Kod podatku**. W tym przykładzie jest to **VAT 19**.

    [![Pole kodu podatku na stronie Zaksięgowany podatek.](./media/tax-posted-to-wrong-ledger-account-Picture2.png)](./media/tax-posted-to-wrong-ledger-account-Picture2.png)

## <a name="check-the-ledger-posting-group-of-the-tax-code"></a>Weryfikacja grupy księgowania w księdze kodu podatku

1. Wybierz kolejno opcje **Podatek** \> **Podatki pośrednie** \> **Podatek** \> **Kody podatków**.
2. Znajdź i wybierz kod podatku, a następnie przejrzyj wartość w polu **Grupa księgowania w księdze**. W tym przykładzie jest to **VAT**.

    [![Pole Księgowanie podatku w księdze na stronie Kody podatku.](./media/tax-posted-to-wrong-ledger-account-Picture3.png)](./media/tax-posted-to-wrong-ledger-account-Picture3.png)

3. Wartość polu **Grupa księgowania w księdze** jest łączem. Aby wyświetlić szczegóły konfiguracji grupy, kliknij to łącze. Ewentualnie wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy) w polu, a następnie wybierz polecenie **Wyświetl szczegóły**.

    [![Polecenie Wyświetl szczegóły.](./media/tax-posted-to-wrong-ledger-account-Picture4.png)](./media/tax-posted-to-wrong-ledger-account-Picture4.png)

4. W polu **Podatek należny** sprawdź, czy numer konta jest poprawny zgodnie z typem transakcji. Jeśli nie jest, wybierz poprawne konto, na którym transakcja ma być zaksięgowana. W tym przykładzie podatek z zamówienia sprzedaży powinien być księgowany na koncie podatku należnego 222200.

    [![Pole Podatek należny na stronie Grupy księgowania.](./media/tax-posted-to-wrong-ledger-account-Picture5.png)](./media/tax-posted-to-wrong-ledger-account-Picture5.png)

    W poniższej tabeli przedstawiono informacje o poszczególnych polach na stronie **Grupy księgowania w księdze**.

    | Pole                  | opis |
    |------------------------|-------------|
    | Podatek należny      | Konto główne wychodzących podatków, które są odprowadzane do urzędu skarbowego. |
    | Podatek naliczony   | Konto główne podatków przychodzących, które są otrzymywane od urzędu skarbowego. |
    | Wydatki podatku nienaliczonego        | Konto główne używane do księgowania ewentualnych podatków obrotowych podlegających odliczeniu, do których dostawcy nie zgłaszają roszczeń, lub raportowania ich do urzędu skarbowego w ramach mechanizmu odwrotnego obciążenia podatku od towarów i usług (GST) / ujednoliconego podatku (HST) Unii Europejskiej. Opcja **Ewentualny podatek obrotowy** musi zostać wybrana dla kodu podatku w grupie podatków, która jest używana w transakcji. To pole jest niedostępne, gdy na stronie **Parametry księgi głównej** zaznaczono opcję **Zastosuj zasady opodatkowania** dla podatku. |
    | Podatek nienaliczony należny        | Konto główne używane do księgowania przychodzących ewentualnych podatków obrotowych, które są odprowadzane do urzędów skarbowych. |
    | Konto rozliczeniowe     | Konto główne, które służy do księgowania salda netto kont księgowych określonych w polach **Należny ewentualny podatek obrotowy** i **Podatek naliczony**. |
    | Rabat gotówkowy dostawcy   | Konto główne, które służy do księgowania rabatów gotówkowych dla kodów podatku skojarzonych z tą grupą księgowania w księdze. |
    | Rabat gotówkowy odbiorcy | Konto główne, które służy do księgowania rabatów gotówkowych dla kodów podatku skojarzonych z tą grupą księgowania w księdze. |

    Aby uzyskać więcej informacji, zobacz [Konfigurowanie grup księgowania dla podatku](tasks/set-up-ledger-posting-groups-sales-tax.md)

## <a name="debug-in-code-to-check-ledger-dimensions"></a>Debugowanie w kodzie w celu sprawdzania wymiarów księgowych

W kodzie konto księgowania jest określone według wymiaru księgowego. Wymiar księgowy zapisuje identyfikator rekordu konta w bazie danych.

1. W przypadku zamówienia sprzedaży dodaj punkt przerwania w metodach **Tax::saveAndPost()** i **Tax::post()**. Należy zwrócić uwagę na wartość **\_ledgerDimension**.

    [![Przykładowy kod zamówienia sprzedaży z punktem przerwania.](./media/tax-posted-to-wrong-ledger-account-Picture6.png)](./media/tax-posted-to-wrong-ledger-account-Picture6.png)

    W przypadku zamówienia zakupu dodaj punkt przerwania w metodach **TaxPost::saveAndPost()** i **TaxPost::postToTaxTrans()**. Należy zwrócić uwagę na wartość **\_ledgerDimension**.

    [![Przykładowy kod zamówienia zakupu z punktem przerwania.](./media/tax-posted-to-wrong-ledger-account-Picture7.png)](./media/tax-posted-to-wrong-ledger-account-Picture7.png)

2. Uruchom następujące zapytanie SQL, aby znaleźć wartość wyświetlaną konta w bazie danych na podstawie identyfikatora rekordu zapisanego przez wymiar księgowy.

    ```sql
    select * from DIMENSIONATTRIBUTEVALUECOMBINATION where recid={the value of _ledgerDimension}
    ```

    [![Wartość wyświetlana identyfikatora rekordu.](./media/tax-posted-to-wrong-ledger-account-Picture8.png)](./media/tax-posted-to-wrong-ledger-account-Picture8.png)

3. Znajdź w stosie wywoła miejsce, w którym jest przypisywana wartość wymiaru **_ledgerDimension**. Zazwyczaj ta wartość pochodzi z **TmpTaxWorkTrans**. W takim przypadku należy dodać punkt przerwania w **TmpTaxWorkTrans::insert()** i **TmpTaxWorkTrans::update()**, aby znaleźć miejsce przypisania wartości.

## <a name="determine-whether-customization-exists"></a>Określanie, czy dostosowanie istnieje

Jeśli zostały wykonane kroki w poprzednich sekcjach, ale nie znaleziono problemu, określ, czy dostosowanie istnieje. Jeśli nie istnieją żadne dostosowania, utwórz żądanie obsługi do firmy Microsoft, aby uzyskać dalszą pomoc techniczną.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
