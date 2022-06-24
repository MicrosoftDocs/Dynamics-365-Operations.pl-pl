---
title: Stan stanowiska dla wniosku o rekrutację
description: W tym artykule opisano zestaw opcji stanu stanowiska dla wniosku o rekrutację dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: 736bdbfb8759ab61202d1f17e3cdc8294be0ba84
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846422"
---
# <a name="recruiting-request-position-status"></a>Stan stanowiska dla wniosku o rekrutację


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym artykule opisano zestaw opcji stanu stanowiska dla wniosku o rekrutację dla Dynamics 365 Human Resources.

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
