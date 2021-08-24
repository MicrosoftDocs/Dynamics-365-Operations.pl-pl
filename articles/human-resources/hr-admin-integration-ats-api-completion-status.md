---
title: Stan ukończenia
description: W tym temacie opisano opcję Stan ukończenia ustawioną dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: 67e464262897d89f80bd615156d56cc12a822dd4a0dfa6d5eb206c38ddd61ec5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732880"
---
# <a name="completion-status"></a>Stan ukończenia

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]