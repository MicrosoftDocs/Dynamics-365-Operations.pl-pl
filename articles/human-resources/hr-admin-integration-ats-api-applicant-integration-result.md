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
ms.openlocfilehash: 3f173e15d5524dfd4d63113760760b2534cc8769456df621415a11e4053cc6fb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6725921"
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