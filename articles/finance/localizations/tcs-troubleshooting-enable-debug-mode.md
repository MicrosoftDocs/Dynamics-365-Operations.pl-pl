---
title: Włączanie trybu debugowania w usłudze obliczania podatku
description: Ten artykuł wyjaśnia, jak włączyć tryb debugowania w usłudze Obliczanie podatków, aby zbadać problemy.
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
ms.openlocfilehash: 2bb381939ebe32cb51caf730cdd441557d83a4c0
ms.sourcegitcommit: 088a7b5eb9a3b68710dfe012abf4c24776978750
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2022
ms.locfileid: "9620906"
---
# <a name="enable-debug-mode-in-the-tax-calculation-service"></a>Włączanie trybu debugowania w usłudze obliczania podatku

[!include [banner](../includes/banner.md)]

Ten artykuł wyjaśnia, jak włączyć tryb debugowania w usłudze Obliczanie podatków, aby zbadać problemy.

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
