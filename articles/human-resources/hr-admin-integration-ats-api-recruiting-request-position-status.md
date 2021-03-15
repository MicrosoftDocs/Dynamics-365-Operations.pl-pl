---
title: Stan stanowiska dla wniosku o rekrutację
description: W tym temacie opisano opcję stanu stanowiska dla wniosku o rekrutację ustawioną dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: 3f7bae64f58f0bdc1603b3c1b5493f1ebcfa8de9
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2021
ms.locfileid: "5126057"
---
# <a name="recruiting-request-position-status"></a>Stan stanowiska dla wniosku o rekrutację

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