---
title: Konfigurowanie ksiąg wynajmu
description: W tym temacie opisano informacje przechowywane w księgach wynajmu. Księgi wynajmu zawierają zasady rachunkowości, które decydują o sposobie księgowania wynajmu w systemie.
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
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 28518341544327f1983e563b719b0f455b6e1c43
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "4446997"
---
# <a name="set-up-lease-books"></a>Konfigurowanie ksiąg wynajmu

[!include [banner](../includes/banner.md)]

Księgi wynajmu zawierają zasady rachunkowości, które decydują o sposobie księgowania wynajmu w systemie. Moduł Wynajem składnika majątku obsługuje nie tylko księgowanie na podstawie gotówki, ale również następujące standardy:

- Ogólnie przyjęte zasady rachunkowości w Stanach Zjednoczonych (US GAAP)
- Accounting Standards Codification Topic 842 (ASC 842)
- ASC 840
- Międzynarodowy Standard Sprawozdawczości Finansowej nr 16 (MSSF 16)
- Międzynarodowy Standard Rachunkowości nr 17 (MSR 17)

Aby utworzyć księgę wynajmu, wykonaj następujące czynności.

1. Przejdź do **Wynajem składnika majątku \> Ustawienia \> Księgi wynajmu**.
2. Wybierz opcję **Nowy**, aby dodać księgę.
3. Ustaw wartości w następujących polach.

    | Imię i nazwisko                                     | opis |
    |------------------------------------------|-------------|
    | Warstwa księgowania                            | Wybierz warstwę księgowania, która ma być używana. Każda księga dołączona do umowy wynajmu jest skonfigurowana dla określonej warstwy księgowania. Każda warstwa księgowania ma inne cele księgowania. |
    | Typ wynajmu                               | Określ, czy wynajem ma być klasyfikowany automatycznie, czy też powinien być wstępnie definiowany jako leasing finansowy lub operacyjny. |
    | Struktura księgowania                     | Wybierz strukturę skojarzoną z księgą. |
    | Konfiguracja okresu wynajmu/okresu użyteczności          | System klasyfikuje wynajem jako leasing finansowy, jeśli typ wynajmu jest ustawiony na **Automatycznie** i jeśli wartość okresu wynajmu w okresie użyteczności składnika majątku jest większa lub równa wartości procentowej wprowadzonej w tym polu.  |
    | Konfiguracja wartości bieżącej / wartości godziwej składnika majątku   | Wprowadź liczbę całkowitą określającą próg decydujący o typie wynajmu. Jeśli wartość bieżąca przyszłych opłat z tytułu wynajmu jest większa od wartości zdefiniowanej przez użytkownika w konfiguracji księgi oraz ustawiono automatyczne klasyfikowanie wynajmu w danej księdze, system zaklasyfikuje wynajem jako leasing finansowy. |
    | Próg krótkiego terminu                     | Wprowadź liczbę miesięcy, która ma być używana jako próg wynajmu krótkoterminowego. Jeśli wartość okresu wynajmu jest mniejsza lub równa liczbie miesięcy wprowadzonej w tym polu, system zaklasyfikuje wynajem jako krótkoterminowy i zastosuje metodę odroczonego czynszu. |
    | Próg niskiej wartości                      | Wprowadź kwotę, która ma być używana jako próg wynajmu o niskiej wartości. Jeśli wartość godziwa składnika majątku jest mniejsza lub równa wartości wprowadzonej w tym polu, system zaklasyfikuje wynajem jako mający niską wartość i zastosuje metodę odroczonego czynszu. |
    | Płatność dla dostawcy                            | Ustaw w tej opcji wartość **Tak**, aby zezwolić na księgowanie opłat z tytułu wynajmu jako faktury na koncie dostawcy określonym dla każdej umowy wynajmu. Po zaksięgowaniu opłaty z tytułu wynajmu konto dostawcy zostanie uznane. Jeśli ta opcja ma wartość **Nie**, będzie uznawane konto ustawione dla typu księgowania **Opłata z tytułu wynajmu** na stronie **Parametry księgowania wynajmu**. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]