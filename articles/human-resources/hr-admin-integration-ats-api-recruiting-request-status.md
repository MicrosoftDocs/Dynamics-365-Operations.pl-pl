---
title: Stan wniosku o rekrutację
description: W tym temacie opisano opcję stanu wniosku o rekrutację ustawioną dla Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3b05cc531a84144708ff52913927bbd04574a3b2
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059191"
---
# <a name="recruiting-request-status"></a>Stan wniosku o rekrutację

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano opcję stanu wniosku o rekrutację ustawioną dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_hcmrecruitingrequeststatus

To wyliczenie zapewnia zestaw opcji dla wartości statusu RecruitingRequest.

| Wartość | Etykiety | opis |
| --- | --- | --- |
| 200000000 | Robocza | Wniosek jest w wersji roboczej i nie jest gotowy do aktywnej rekrutacji. |
| 200000001 | W trakcie przeglądu | Żądanie zostało przesłane i jest kierowane do zatwierdzenia przez przepływ pracy. Dostępne tylko po włączeniu przepływu pracy. |
| 200000002 | Oczekująca | Żądanie oczekuje na akcję przepływu pracy. Dostępne tylko po włączeniu przepływu pracy. |
| 200000003 | Anulowana | Żądanie zostało anulowane. Dostępne tylko po włączeniu przepływu pracy. |
| 200000004 | Odrzucone | Żądanie zostało odrzucone. Dostępne tylko po włączeniu przepływu pracy. |
| 200000005 | Aktywni | Każdy przepływ pracy jest ukończony i zatwierdzony, a żądanie jest gotowe do aktywnej rekrutacji. |
| 200000006 | Zamknięte | Wniosek o rekrutację jest zakończony. |

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów](hr-admin-integration-ats-api-introduction.md)<br>
[Przykładowa kwerenda dla wniosku o rekrutację](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]