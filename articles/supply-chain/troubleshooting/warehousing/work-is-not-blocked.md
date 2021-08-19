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
ms.openlocfilehash: 6b4361682246397732e8326b98b1b86ff878664e54c8c352296b0d7eaff6bbbd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6719558"
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
