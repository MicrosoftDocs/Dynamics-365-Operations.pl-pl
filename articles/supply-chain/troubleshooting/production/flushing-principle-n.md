---
title: Ustawienia reguły opróżniania w wierszach BOM nie są zachowane
description: Ustawienia reguły opróżniania w wierszach listy składników BOM nie są zachowane.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PurchTable,ProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 84a84728016119a2a02f59f6903171afbceb48e7
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026815"
---
# <a name="flushing-principle-settings-on-bom-lines-arent-respected"></a>Ustawienia reguły opróżniania w wierszach BOM nie są zachowane

Numer artykułu z bazy wiedzy: 4612725

## <a name="symptoms"></a>Objawy

Ten problem występuje, gdy w polu **Automatyczne zużycie BOM** na karcie **Aktualizacja automatyczna** na stronie **Parametry kontroli produkcji** jest ustawiona wartość *Zasada opróżniania*. To ustawienie wskazuje, że wszystkie wiersze BOM powinny być zużywane automatycznie po otrzymaniu zamówienia zakupu. Jeśli pole **Zasada opróżniania** w wierszach BOM zostanie jawnie ustawione na wartość *Ręcznie*, można oczekiwać, że wiersze BOM nie będą zużywane automatycznie. Jednak w przypadku tego problemu wiersze BOM, w których w polu **Reguły opróżniania** jest ustawiona wartość *Ręcznie*, są mimo to zużywane automatycznie.

## <a name="resolution"></a>Rozdzielczość

Jeśli występuje ten problem, parametry kontroli produkcji mogą być tak ustawione, aby zastąpić ustawienie **Reguły opróżniania** w wierszach BOM. Na stronie **Parametry kontroli produkcji**, na karcie **Aktualizacja automatyczna** sprawdź wartość pola **Automatyczne zużycie BOM**. Jeśli jest ustawiona wartość *Zawsze*, system zignoruje ustawienie **Reguły opróżniania** we wszystkich wierszach BOM i zawsze opróżnia wiersze. Aby system był przestrzegany ustawienia **reguły opróżniania** w wierszach BOM, zmień wartość pola **Automatyczne zużycie BOM** na *Zasadę opróżniania*.
