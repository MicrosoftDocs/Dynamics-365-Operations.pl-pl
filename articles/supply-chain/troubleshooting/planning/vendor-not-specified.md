---
title: Sprzedawca nie jest określony, kiedy planowane zamówienia są potwierdzane
description: Przy próbie potwierdzenia planowanych zamówień pojawia się komunikat o błędzie z informacją, że nie określono sprzedawcy.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4d523d57a862f67fcd40edd60a0fabf40ea7dabcf058f2d11af1fe003c9e304b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741987"
---
# <a name="vendor-isnt-specified-when-planned-orders-are-firmed"></a>Sprzedawca nie jest określony, kiedy planowane zamówienia są potwierdzane

Kod błędu: SYS23532

## <a name="symptoms"></a>Objawy

Przy próbie potwierdzenia zaplanowanych zleceń pojawia się następujący komunikat o błędzie:

> Nie określono dostawcy

## <a name="resolution"></a>Rozwiązanie

Aby określić dostawcę, wykonaj następujące czynności.

1. Otwórz planowane zlecenie, w którym brakuje sprzedawcy.
1. Na skróconej karcie **Planowana podaż** wybierz dostawcę w polu **Dostawca**.
