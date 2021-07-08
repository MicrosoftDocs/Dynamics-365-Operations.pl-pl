---
title: Numer wybranej formuły nie jest zatwierdzony dla zamówienia partii
description: Podczas próby utworzenia planowanego zamówienia pojawia się komunikat o błędzie z informacją, że wybrany numer formuły nie jest zatwierdzony dla zamówienia wsadowego.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4f993c92ca0a2f8f79e4b0e0eda43904529163f8
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294151"
---
# <a name="selected-formula-number-isnt-approved-for-a-batch-order"></a>Numer wybranej formuły nie jest zatwierdzony dla zamówienia partii

Kod błędu: PRO2614

## <a name="symptoms"></a>Objawy

Przy próbie potwierdzenia planowanego zlecenia pojawia się następujący komunikat o błędzie:

> Numer wybranej formuły nie jest zatwierdzony dla szarży produkcyjnej.

## <a name="cause"></a>Powód

System sprawdza poprawność operacji firmowania, aby upewnić się, że dla aktywnej pozycji dostępna jest zatwierdzona formuła. Prawdopodobnie należy zatwierdzić formułę.

## <a name="resolution"></a>Rozwiązanie

Aby zatwierdzić formułę, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie informacjami o produktach \> Listy składowe (BOM) i formuły \> Formuły**.
1. Wybierz odpowiednią formułę.
1. W okienku akcji na karcie **Formuła** w grupie **Obsługa** wybierz opcję **Zatwierdź formułę**.
1. W oknie dialogowym **Zatwierdzanie BOM lub formuły** wybierz osobę zatwierdzającą, a następnie wybierz przycisk **OK**.
