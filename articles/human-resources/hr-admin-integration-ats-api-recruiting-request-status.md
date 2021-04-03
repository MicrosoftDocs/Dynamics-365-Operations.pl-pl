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
ms.openlocfilehash: 0032e6bfdbfd2792dafda8bf24a1b0cbc551740d
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464653"
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