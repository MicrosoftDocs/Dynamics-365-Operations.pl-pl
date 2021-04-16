---
title: Stan ukończenia
description: W tym temacie opisano opcję Stan ukończenia ustawioną dla Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f1b0c61ac9d9dc611d2a4700a1a004e3d15b4445
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798376"
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