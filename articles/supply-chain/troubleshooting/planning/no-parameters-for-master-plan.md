---
title: Parametry dla planu głównego nie istnieją
description: Podczas próby zatwierdzenia planowanego zlecenia pojawia się komunikat o błędzie, który mówi, że nie istnieją żadne parametry dla planu głównego.
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
ms.openlocfilehash: d4b64af2e30109b8560d40c4c532504611528bbe
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294157"
---
# <a name="parameters-for-the-master-plan-dont-exist"></a>Parametry dla planu głównego nie istnieją

Kod błędu: SYS25368

## <a name="symptoms"></a>Objawy

Przy próbie potwierdzenia planowanego zlecenia pojawia się następujący komunikat o błędzie:

> Parametry dla planu głównego %1 nie istnieją.

## <a name="cause"></a>Powód

Z powodu problemów z konfiguracją system nie może znaleźć ustawień dla określonego planu.

## <a name="resolution"></a>Rozwiązanie

- Przejdź do **Planowania głównego \> Konfiguracja \> Plany \> Plany główne** i upewnij się, że istnieje plan o określonej nazwie.
