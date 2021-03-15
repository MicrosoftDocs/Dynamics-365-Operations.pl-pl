---
title: Częstotliwość kontroli generowana na podstawie
description: W tym temacie opisano częstotliwość kontroli generowania na podstawie zestawu opcji dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: f291e28584dadc465092d99a1354fda793ff7560
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2021
ms.locfileid: "5126153"
---
# <a name="screening-frequency-generate-from"></a>Częstotliwość kontroli generowana na podstawie

W tym temacie opisano częstotliwość kontroli generowania na podstawie zestawu opcji dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_hcmfrequencygeneratefrom

To wyliczenie zawiera zestaw opcji wartości określających datę rozpoczęcia obliczania następnej wymaganej kontroli.

| Wartość | Etykiety | opis |
| --- | --- | --- |
| 200000000 Niezaznaczone | Nie wybrano żadnej wartości. |
| 200000001 Data ukończenia | Obliczanie jest wykonywane od daty zakończenia ostatniej kontroli. |
| 200000002 Data wymagana | Obliczenie jest wykonywane od ostatniego wymaganego terminu przeglądu. |

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów](hr-admin-integration-ats-api-introduction.md)<br>
[Przykład kwerendy dotyczącej kandydata do zatrudnienia](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]