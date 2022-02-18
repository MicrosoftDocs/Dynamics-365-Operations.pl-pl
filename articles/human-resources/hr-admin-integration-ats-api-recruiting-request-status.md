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
ms.openlocfilehash: d845179077fc2e04dfb3bd05eaa70b0a2a016121
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067108"
---
# <a name="recruiting-request-status"></a>Stan wniosku o rekrutację


[!INCLUDE [PEAP](../includes/peap-1.md)]

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
