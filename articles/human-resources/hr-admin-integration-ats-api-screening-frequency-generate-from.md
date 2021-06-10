---
title: Częstotliwość kontroli generowana na podstawie
description: W tym temacie opisano częstotliwość kontroli generowania na podstawie zestawu opcji dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: ae5ad3e556f40cedd385d8aadded9ef76447a98b
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054099"
---
# <a name="screening-frequency-generate-from"></a>Częstotliwość kontroli generowana na podstawie

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

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