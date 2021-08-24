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
ms.openlocfilehash: 7b87bff6925721a20ad9d8bf92e64113d30333defd2d6708b445bcd2126e485a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6766249"
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