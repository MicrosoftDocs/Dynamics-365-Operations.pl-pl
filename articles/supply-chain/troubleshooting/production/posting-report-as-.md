---
title: Błąd podczas księgowania raportu jako gotowego arkusza
description: Podczas zaksięgowania arkusza Zgłoszenia gotowych wyświetlany jest komunikat o błędzie informujący, że zamówione ilości nie mogą zostać zmniejszone.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTableListPage, ProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 55db7d0033dd66c1b973abf96671a20ab05d61d8
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026802"
---
# <a name="error-when-the-report-as-finished-journal-is-posted"></a>Błąd podczas księgowania raportu jako gotowego arkusza

Numer artykułu z bazy wiedzy: 4612891

## <a name="symptoms"></a>Objawy

Podczas zaksięgowania arkusza **zgłoszenia gotowych** wystąpi błąd i zostanie wyświetlony następujący komunikat o błędzie:

> Ilość zamówiona nie może być zmniejszona. Niewystarczający poziom zapasów ze stanem Zamówione. Pozycje to Zakupione, Odebrane lub Zarejestrowane.

Ten błąd występuje tylko wtedy, gdy pole **Ilość towarów błędnych** jest ustawione w pierwszym wierszu arkusza **Zgłoszenie jako gotowe**, a pole **Ilość dobrych** jest ustawione w ostatnim wierszu. Jeśli pole **Ilość błędów** jest ustawione w ostatnim wierszu, nie występuje błąd.

## <a name="resolution"></a>Rozdzielczość

Aby uniknąć tego błędu, otwórz stronę **Parametry kontroli produkcji**, a następnie na karcie **Ogólne** dla opcji **Zwiększ ilość pozostała z błędami** ustaw wartość *Tak*.
