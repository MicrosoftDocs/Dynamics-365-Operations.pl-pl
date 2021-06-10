---
title: Wynik integracji kandydata
description: W tym temacie opisano zestaw opcji wyników integracji kandydata dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: 8bef974abff18d7c07ecd679b7e01b31ea1459c4
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053906"
---
# <a name="applicant-integration-result"></a>Wynik integracji kandydata

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]