---
title: Stan ukończenia
description: W tym temacie opisano opcję Stan ukończenia ustawioną dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: e9024e00b5d25117fd255084609c4f8db9284f32
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125696"
---
# <a name="completion-status"></a>Stan ukończenia

W tym temacie opisano opcję Stan ukończenia ustawioną dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_hcmcompletionstatus

To wyliczenie zawiera zestaw opcji wartości stanu dla kontroli kandydatów. 

| Wartość | Etykiety | opis |
| --- | --- | --- |
| 200000000 | Nieukończone | Kandydat nie zakończył jeszcze kontroli. |
| 200000001 | Sukces | Kandydat przeszedł kontrolę. |
| 200000002 | Niepowodzenie | Kandydat nie przeszedł kontroli. |

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów](hr-admin-integration-ats-api-introduction.md)<br>
[Przykład kwerendy dotyczącej kandydata do zatrudnienia](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)
