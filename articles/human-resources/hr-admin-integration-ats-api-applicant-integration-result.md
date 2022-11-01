---
title: Wynik integracji kandydata
description: W tym artykule opisano zestaw opcji wyników integracji kandydata dla Dynamics 365 Human Resources.
author: jaredha
ms.date: 09/12/2022
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
ms.openlocfilehash: 86f3f75e538268644cea4f927f04c07aae115f00
ms.sourcegitcommit: 27ce4fc706100b626b81c3a1023238acd872e76c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/20/2022
ms.locfileid: "9702236"
---
# <a name="applicant-integration-result"></a>Wynik integracji kandydata


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym artykule opisano zestaw opcji wyników integracji kandydata dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_hcmapplicantintegrationresult

To wyliczenie zapewnia stan rekordu kandydata.

| Wartość | Etykiety | opis |
| --- | --- | --- |
| 200000000 | Nieprzetworzone | Kandydat jest nadal uwzględniany. |
| 200000001 | Zatrudniono | Kandydat został zatrudniony. |
| 200000002 | Nie zatrudniono | Podjęto decyzję, aby nie zatrudniać kandydata. |
| 200000003 | Odrzucono | Kandydat już nie jest brany pod uwagę. |

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów](hr-admin-integration-ats-api-introduction.md)<br>
[Przykład kwerendy dotyczącej kandydata do zatrudnienia](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
