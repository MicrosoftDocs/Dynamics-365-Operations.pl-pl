---
title: Aby można było zaakceptować planowane zlecenie produkcyjne, należy je najpierw zaplanować
description: Przy próbie zatwierdzenia planowanego zamówienia pojawia się komunikat o błędzie z informacją, że zamówienie musi być zaplanowane, zanim będzie można je zatwierdzić.
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
ms.openlocfilehash: a360cb3cbd26e1bc1ebb1baf1a6a4d8282c28c5c
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294159"
---
# <a name="planned-production-order-must-be-scheduled-before-it-can-be-firmed"></a>Aby można było zaakceptować planowane zlecenie produkcyjne, należy je najpierw zaplanować

Kod błędu: SYS309802

## <a name="symptoms"></a>Objawy

Przy próbie potwierdzenia planowanego zlecenia pojawia się następujący komunikat o błędzie:

> Aby można było zaakceptować planowane zlecenie produkcyjne, należy je najpierw zaplanować.

## <a name="cause"></a>Powód

Planowane daty rozpoczęcia i zakończenia nie mogą być puste.

## <a name="resolution"></a>Rozwiązanie

Aby określić daty rozpoczęcia i zakończenia dla planowanego zlecenia, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Planowanie główne \> Planowanie główne \> Zamówienia planowane**.
1. Otwórz odnośne planowane zamówienie.
1. Na skróconej karcie **Ogólne**, w sekcji **Zaplanowane** określ daty w polach **Data rozpoczęcia** i **Data zakończenia**.
