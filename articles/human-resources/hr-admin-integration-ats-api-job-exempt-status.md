---
title: Status zwolnienia z pracy
description: W tym temacie opisano opcję Zwolnienie z pracy ustawioną dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: 8e91fbb420009d5131e2faa7dbea8a302a027e0a
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053858"
---
# <a name="job-exempt-status"></a>Status zwolnienia z pracy

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]