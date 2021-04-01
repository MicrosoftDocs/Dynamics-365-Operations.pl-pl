---
title: Konfigurowanie typów wydatków
description: W tym temacie wyjaśniono, jak konfigurować typy wydatków w module Wynajem składnika majątku.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2019-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 1538826f140393eec59be9ff4df5242d5ced9d8f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249756"
---
# <a name="set-up-expense-types"></a>Konfigurowanie typów wydatków

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak konfigurować typy wydatków w module Wynajem składnika majątku. Koszty, które nie są reprezentowane w harmonogramie płatności, są nazywane *kosztami wydatków*. Przykładami tych kosztów są podatki od nieruchomości, wspólne koszty utrzymania obszaru oraz koszty ubezpieczenia.

## <a name="add-an-administrative-expense-type"></a>Dodawanie typu wydatku administracyjnego

1. Przejdź do **Wynajem składnika majątku \> Ustawienia \> Typy wydatków**.
2. Wybierz pozycję **Nowy**.
3. W odpowiednich polach wprowadź nowy typ wydatku oraz jego opis.

## <a name="assign-accounts-to-administrative-costs"></a>Przypisywanie kont do kosztów administracyjnych

Następnie należy skojarzyć konta z typami wydatków. Te konta będą obciążane podczas księgowania wpisów harmonogramu wydatków. Konto przeciwstawne jest określane w wierszach sekcji **Harmonogram płatności kosztów wykonawczych** dla każdej umowy wynajmu.

1. Przejdź do **Wynajem składnika majątku \> Ustawienia \> Parametry wynajmu składników majątku**.
2. Na karcie **Konta** na skróconej karcie **Koszty wykonawcze** w polu **Typ wydatku** zaznacz typ wydatku.
3. Wybierz opcję **Dodaj**.
4. W polu **Typ księgi** wybierz typ księgi, który ma zostać połączony z kosztami administracyjnymi.

    > [!NOTE]
    > Z tym samym kontem wydatków można łączyć wiele typów ksiąg.

5. W polu **Kod konta** określ, do których umów wynajmu ma być stosowana księga:

    - **Wszystkie** – księga ma zastosowanie do wszystkich umów wynajmu.
    - **Grupa** — zastosowanie księgi do wybranej grupy umów wynajmu.
    - **tabela** – księga ma zastosowanie do wybranych umów wynajmu.

6. Jeśli w polu **Kod konta** wybrano opcję **Grupa** lub **Tabela**, wybierz numer konta lub numer grupy w polu **Numer konta/grupy**.
7. W odpowiednich polach wybierz konto główne leasingu finansowego i konto główne leasingu operacyjnego.

Po wykonaniu tych kroków można dodawać wydatki za pomocą wierszy w sekcji **Harmonogram płatności kosztów wykonawczych** na stronie **Szczegóły wynajmu** dla wybranej umowy wynajmu. Wydatki można dodawać również podczas tworzenia nowej umowy wynajmu.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]