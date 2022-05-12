---
title: Włączenie trybu debugowania w usłudze Obliczanie podatków
description: Ten temat wyjaśnia, jak włączyć tryb debugowania w usłudze Obliczanie podatków, aby zbadać problemy.
author: hangwan
ms.date: 03/25/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: ''
ms.search.region: Global
ms.author: hangwan
ms.search.validFrom: 03/23/2022
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 2f526a2341c7ef682209ed979fe686e31ad62a37
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645427"
---
# <a name="enable-debug-mode-in-the-tax-calculation-service"></a>Włączenie trybu debugowania w usłudze Obliczanie podatków

[!include [banner](../includes/banner.md)]

Ten temat wyjaśnia, jak włączyć tryb debugowania w usłudze Obliczanie podatków, aby zbadać problemy.

1. Dodaj **&debug=vs%2CconfirmExit&** do adresu URL serwera obiektów aplikacji (AOS), a następnie odśwież stronę.
2. Gdy wybierzesz **Podatek od sprzedaży**, aby obliczyć podatek od sprzedaży, zostanie otwarty plik tekstowy o nazwie **TaxServiceTroubleshootingLog.txt**. Plik **TaxServiceTroubleshootingLog.txt** zawiera **TaxableDocument** oraz parametr obliczeniowy. Wyniki te są zwracane z serwisu podatkowego i zawierają informacje o wyjątkach, które służą do rozwiązywania problemów.

## <a name="sample"></a>Przykład

```json
===============================Tax service calculation input JSON:=====================================
{
    "TaxableDocument": {
    "Header": [
        {
        "Lines": [
            {
            "Transaction Line ID": "5816,68719677391",
            ...
            }
        ],
        "Transaction Header ID": "2022,68719506302",
        ...
        }
    ]
    },
    "Parameter": {
    "ContinueOnErrors": true,
    ...
    },
    "Adjustment": {
    "Lines": {}
    }
}
===========================Tax service calculation result JSON:=================================
{
    "taxDocument": {
    "Header": [
        {
        "Lines": [
            {
            "Tax Codes": {
                ...
            }
        ],
        "Measures": {
            "List Code": "EUTrade"
        },
        "Tax Registration ID": null,
        "Transaction Header ID": "2022,68719506302",
        "Errors": null
        }
    ]
    },
    "solutionId": "b51e0025-cbbe-4d37-bf0b-90d7be4f214d|1",
    "isPartialSuccess": false
}
=============================CorrelationId:==============================
"21f3a8a1-ee9a-477b-b44e-b8ec79e74d16"
```

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
