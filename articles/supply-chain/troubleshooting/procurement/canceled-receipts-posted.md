---
title: Transakcje można księgować na zawieszonym koncie księgowym
description: W przypadku anulowania przyjęcia produktów system umożliwia księgowanie transakcji na zawieszonych kontach księgowych, nawet jeśli konta główne są zawieszone
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 20df0ee4107ad62bec0dd9a683660fe2375a3dd1
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477356"
---
# <a name="transactions-can-be-posted-to-a-suspended-ledger-account"></a>Transakcje można księgować na zawieszonym koncie księgowym

## <a name="symptoms"></a>Objawy

W przypadku anulowania przyjęcia produktów system umożliwia księgowanie transakcji na zawieszonych kontach księgowych, nawet jeśli konta główne są zawieszone.

## <a name="reproduce-the-issue"></a>Odtwórz ten błąd

Poniższa procedura przedstawia jeden ze sposobów odtworzenia błędu.

1. Na stronie **Parametry rozrachunków z dostawcami** na karcie **Ogólne** upewnij się, że opcja **Księguj dokument przyjęcia produktów w księdze** jest ustawiona na wartość *Tak*.
1. Utwórz zamówienie zakupu i dodaj wiersz zamówienia z ilością *1 000* dla produktu.
1. Potwierdź zamówienie zakupu.
1. Zaksięguj dokument przyjęcia produktów i sprawdź załączniki.
1. Zawiesić odpowiednie konta główne, *200140* i *140200*.
1. Anuluj zaksięgowane przyjęcia produktu.
1. Zwróć uwagę, że transakcje mogą być księgowane na zawieszonych kontach księgowych.

## <a name="resolution"></a>Rozwiązanie

Transakcje mogą być księgowane na zawieszonych kontach księgowych po anulowaniu przyjęcia produktów, ponieważ takie zachowanie umożliwia prawidłowe księgowanie.
