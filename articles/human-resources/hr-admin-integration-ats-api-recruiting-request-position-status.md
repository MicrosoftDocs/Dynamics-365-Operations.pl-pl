---
title: Stan stanowiska dla wniosku o rekrutację
description: W tym temacie opisano opcję stanu stanowiska dla wniosku o rekrutację ustawioną dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: 7e59e9381fb15b339095d6a71296813e0141e9ab
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5789739"
---
# <a name="recruiting-request-position-status"></a>Stan stanowiska dla wniosku o rekrutację

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano opcję stanu stanowiska dla wniosku o rekrutację ustawioną dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_hcmrecruitingrequestpositionstatus

W tym wyliczeniu jest ustawiana opcja wartości stanu poszczególnych stanowisk, do których jest zatrudniane w jednostce RecruitingRequestPosition.

| Wartość | Etykiety | opis |
| --- | --- | --- |
| 200000000 | Wolne | Stanowisko w wniosku o rekrutację jest otwarte do rekrutacji. Nie oznacza to, że obecnie nie ma aktywnego przypisania stanowiska do tego stanowiska. W czasie rekrutacji na to stanowisko może być zatrudniony pracownik. Wskazuje tylko, że stanowisko jest dostępne do rekrutacji w kontekście wniosku o rekrutację. |
| 200000001 | Obsadzone | Wybrano pracownika do przypisania do stanowiska. |
| 200000002 | Anulowana | Wniosek o rekrutację na to stanowisko został anulowany. |

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów](hr-admin-integration-ats-api-introduction.md)<br>
[Przykładowa kwerenda dla wniosku o rekrutację](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]