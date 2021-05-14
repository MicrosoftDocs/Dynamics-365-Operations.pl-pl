---
title: Praca nie jest zablokowana
description: Praca nie jest zablokowana
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d64ab282972e46e8857581b59e5705dd15667328
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924211"
---
# <a name="work-isnt-blocked"></a>Praca nie jest zablokowana

Kod błędu: WHSUnblockNotBlockedWorkErrorMessage

## <a name="symptoms"></a>Objawy

W systemie wyświetlany jest następujący komunikat o błędzie:

> Praca o identyfikatorze %1 nie jest zablokowana.

## <a name="cause"></a>Powód

Opcja **Zablokowana grupy czynności** dla grupy czynności ma wartość *Nie*. Nie można odblokować pracy, ponieważ nie jest ona obecnie zablokowana.

## <a name="resolution"></a>Rozdzielczość

 Odblokować można tylko wtedy, gdy dla opcji **Zablokowana grupy czynności** jest ustawiona wartość *Tak*.
