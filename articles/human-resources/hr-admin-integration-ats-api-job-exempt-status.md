---
title: Status zwolnienia z pracy
description: W tym temacie opisano opcję Zwolnienie z pracy ustawioną dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: 0cd6ffc01793c8ff12e36175c7c9feaf8a4b3cdf
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125576"
---
# <a name="job-exempt-status"></a>Status zwolnienia z pracy

W tym temacie opisano opcję Zwolnienie z pracy ustawioną dla Dynamics 365 Human Resources.

Nazwa fizyczna: cdm_jobexemptstatus

To wyliczenie określa zestaw opcji dla wartości statusu zwolnienia z zadań FLSA. Te informacje są dostępne w istniejącym zestawie opcji cdm_jobexemptstatus.

| Wartość | Etykiety | opis |
| --- | --- | --- |
| 200000000 | Zwolnienie | Stanowisko ma status zwolnienia na podstawie wytycznych FLSA. |
| 200000001 | NonExempt | Stanowisko nie ma statusu zwolnienia na podstawie wytycznych FLSA. |
| 200000002 | Nie ma zastosowania | Wytyczne dotyczące stanu FLSA nie mają zastosowania do tego stanowiska. |

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów](hr-admin-integration-ats-api-introduction.md)<br>
[Przykładowa kwerenda dla wniosku o rekrutację](hr-admin-integration-ats-api-recruiting-request-example-query.md)
