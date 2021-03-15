---
title: Stan wniosku o rekrutację
description: W tym temacie opisano opcję stanu wniosku o rekrutację ustawioną dla Dynamics 365 Human Resources.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 55ed9c391a1b5f86c3c443b9fceeee5c2301444d
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125961"
---
# <a name="recruiting-request-status"></a>Stan wniosku o rekrutację

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