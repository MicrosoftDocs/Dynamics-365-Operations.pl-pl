---
title: Nie udało się znaleźć pasującego wyniku
description: Ten temat wyjaśnia, jak rozwiązać problem błędu Nie można znaleźć pasującego wyniku w usłudze Obliczanie podatków.
author: hangwan
ms.date: 03/25/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: hangwan
ms.search.validFrom: 03/23/2022
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: c1a343b0b74645d40b0a2582749968cc0a56afd7
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645411"
---
# <a name="no-matching-result-could-be-found"></a>Nie udało się znaleźć pasującego wyniku

[!include [banner](../includes/banner.md)]

Ten temat wyjaśnia, jakie kroki możesz podjąć, jeśli otrzymasz błąd Nie można znaleźć pasującego wyniku w usłudze Obliczanie podatków.

## <a name="symptom"></a>Objaw

Otrzymujesz następujący komunikat o błędzie: Nagłówek/Wiersze - 1, grupa podatkowa, nie można znaleźć pasującego wyniku.

```json
======================Tax service calculation result JSON:===========================
{
    "taxDocument": {
        "Header": [
            {
                "Lines": [
                    {
                        ...
                        "Errors": [
                            {
                                "Code": "TaxSetup20000",
                                "Message": "Header/Lines - 1, Tax group applicability, no matching result could be found."
                            }
                        ],
                        "Adjustment": null
                    }
                ],
                "Measures": {
                    ...
                },
                ...
            }
        ]
    },
    ...
}
```

## <a name="cause"></a>Powód

Problem pojawia się, gdy konfiguracja funkcji w Regulatory Configuration Service (RCS) jest nieprawidłowa.

## <a name="troubleshoot"></a>Rozwiąż problemy

1. Pobierz plik rozwiązywania problemów. Aby uzyskać więcej informacji, zobacz [Włącz tryb debugowania w celu rozwiązywania problemów](tcs-troubleshooting-enable-debug-mode.md).
2. Porównaj obliczenia usługi podatkowej z ustawieniami funkcji, aby naprawić problem z ustawieniami.

    Poniższy przykład przedstawia dane wejściowe do kalkulacji usługi podatkowej.

    ```json
    ===============================Tax service calculation input JSON:=====================================
    {
        "TaxableDocument": {
            "Header": [
                {
                    "Lines": [
                        {
                            ...
                        }
                    ],
                    "Business Process": "Sales",
                    "Ship From Zip Code": "30159",
                }
            ]
        },
        "Parameter": {
            ...
        },
        "Adjustment": {
            "Lines": {}
        }
    }
    ```

    Poniższa tabela zawiera listę grup podatkowych, które można zastosować w RCS.

    | Proces Header.Business | Jednostka Lines.Business | Kod pocztowy wysyłki z Header.Ship | Grupa podatku |
    |-------------------------|---------------------|---------------------------|-----------|
    | Arkusz                 |                     |                           | Grupa A   |
    | Sprzedaż                   |                     | 30160                     | Grupa B   |

    Zgodnie z danymi wejściowymi do kalkulacji usługi podatkowej wartość **Proces biznesowy** w nagłówku to **Sprzedaż**, a wartość **Kod pocztowy wysyłki** w nagłówku to **30159**. To wejście jest oparte na ustawieniu reguł stosowalności w RCS. Ponieważ nie ma pasującej linii, pojawia się błąd.

    > [!NOTE]
    > Jeśli wartość w regule stosowalności jest pusta, reguła ma zastosowanie do dowolnej wartości.

## <a name="mitigation"></a>Sposób minimalizacji

Wykonaj poniższe kroki, aby złagodzić ten błąd.

1. W RCS wybierz kolejno opcje **Funkcje globalizacji** \> **Obliczanie podatku**.
2. Utwórz nową wersję funkcji.
3. Dodaj wiersz dla odpowiedniej informacji.

    | Proces Header.Business | Jednostka Lines.Business | Kod pocztowy wysyłki z Header.Ship| Grupa podatku |
    |-------------------------|---------------------|--------------------------|-----------|
    | Arkusz                 |                     |                          | Grupa A   |
    | Sprzedaż                   |                     | 30160                    | Grupa B   |
    | Sprzedaż                   |                     | 30159                    | Grupa B   |

4. Opublikuj wersję konfiguracji funkcji.
5. W systemie Microsoft Dynamics 365 Finance przejdź do zakładki **Podatki** \> **Konfiguracja** \> **Konfiguracja podatkowa** \> **Parametry obliczeń podatkowych** i wybierz nową wersję.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
