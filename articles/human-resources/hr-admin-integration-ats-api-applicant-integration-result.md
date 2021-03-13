---
title: Wynik integracji kandydata
description: W tym temacie opisano zestaw opcji wyników integracji kandydata dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: 157864cd0eee879013724615ce31306c99c5aa68
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125816"
---
# <a name="applicant-integration-result"></a>Wynik integracji kandydata

W tym temacie opisano zestaw opcji wyników integracji kandydata dla Dynamics 365 Human Resources.

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
