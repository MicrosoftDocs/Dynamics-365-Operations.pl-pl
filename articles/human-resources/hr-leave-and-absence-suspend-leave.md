---
title: Zawieszenie urlopu
description: Istnieje możliwość zawieszenia urlopu dla pracownika w Dynamics 365 Human Resources.
author: twheeloc
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SuspendLeave, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9c8262fb34175f6f9326d6be82c922b2170fc5a7
ms.sourcegitcommit: e88ecaccd82afa3a915e41df1d4287d99da6a48a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/29/2022
ms.locfileid: "9805268"
---
# <a name="suspend-leave"></a>Wstrzymaj urlop

>[!Important]
>Funkcjonalność opisana w tym artykule jest obecnie dostępna dla klientów samodzielnej wersji Dynamics 365 Human Resources. Część lub całość tej funkcjonalności będzie dostępna w ramach przyszłego wydania infrastruktury Finance po wydaniu wersji Finance 10.0.26.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Możesz zawiesić urlop dla pracownika, aby zatrzymać naliczanie urlopu od przetwarzania wybranych typów urlopów.

## <a name="suspend-leave-and-absence-for-an-employee"></a>Zawieszanie urlopów i nieobecności dla pracownika etatowego

1. W rekordzie pracownika wybierz pozycję **Urlop**.

2. Wybierz **Wstrzymaj urlop**.

3. Wybierz pozycję **Nowy**.

4. W oknie dialogowym **Wstrzymaj naliczanie urlopu** wybierz **Typ urlopu** wraz z **Datą rozpoczęcia** i **Datą zakończenia** zawieszenia.

5. Opcjonalnie możesz dodać **Komentarz** dotyczący zawieszenia. 

Jeśli naliczenia są przetwarzane podczas zawieszenia urlopu pracownika, nie zostaną nałożone żadne naliczenie dla typów wstrzymania urlopów.

> [!NOTE]
> Wnioski o udzielenie urlopu zawieszają wnioski o udzielenie czasu wolnego, ale wnioski o udzielenie czasu wolnego nie zawieszają wniosków o udzielenie urlopu.

## <a name="see-also"></a>Informacje dodatkowe

- [Omówienie urlopów i nieobecności](hr-leave-and-absence-overview.md)
- [Konfigurowanie typów urlopów i nieobecności](hr-leave-and-absence-types.md)
- [Naliczanie do planów urlopów i nieobecności](hr-leave-and-absence-accrue.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
