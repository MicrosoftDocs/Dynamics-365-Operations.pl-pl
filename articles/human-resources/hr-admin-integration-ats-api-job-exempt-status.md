---
title: Status zwolnienia z pracy
description: W tym artykule opisano opcję Stan zwolnienia z pracy ustawioną dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: e59a71264d50cecce4d31dfa26ad7f05ef3f34e4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894680"
---
# <a name="job-exempt-status"></a>Status zwolnienia z pracy


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym artykule opisano opcję Stan zwolnienia z pracy ustawioną dla Dynamics 365 Human Resources.

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
