---
title: Nie można ustalić kodu podatku
description: Ten artykuł wyjaśnia, jak rozwiązać problem błędu Nie można ustalić kodu podatkowego w usłudze Obliczanie podatków.
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
ms.openlocfilehash: 6a74724de38cf362900277ab9addc8e6894f7689
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877867"
---
# <a name="tax-code-cannot-be-determined"></a>Nie można ustalić kodu podatku

[!include [banner](../includes/banner.md)]

Ten artykuł wyjaśnia, jakie kroki możesz podjąć, jeśli otrzymasz błąd Nie można ustalić kodu podatkowego w usłudze Obliczanie podatków.

## <a name="symptom"></a>Objaw

Otrzymujesz następujący komunikat o błędzie: Nagłówek/Wiersze - 1, nie można ustalić kodu podatkowego. Ewentualnie możesz znaleźć błąd w pliku rozwiązywania problemów, jak pokazano w poniższym przykładzie. Aby uzyskać więcej informacji, zobacz [Włącz tryb debugowania w celu rozwiązywania problemów](tcs-troubleshooting-enable-debug-mode.md).

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
                                "Code": "TaxSetup20001",
                                "Message": "Header/Lines - 1, tax code cannot be determined."
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

Problem pojawia się prawdopodobnie dlatego, że grupa podatkowa i grupa podatkowa elementu nie nachodzą na siebie.

## <a name="troubleshoot"></a>Rozwiąż problemy

Wykonaj poniższe kroki, aby rozwiązać ten problem.

1. W pliku rozwiązywania problemów sprawdź, czy została określona grupa podatkowa i grupa podatkowa artykułu. Jeśli wartości dla **Grupy podatkowej** i **Grupy podatkowej artykułu** są puste, grupa podatkowa i grupa podatkowa artykułu nie zostały jeszcze określone. Jeśli zostały one określone, wyniki mogą być nieprawidłowe.

    Oto przykład pliku do rozwiązywania problemów.

    ```json
    ======================Tax service calculation result JSON:===========================
    {
        "taxDocument": {
            "Header": [
                {
                    "Lines": [
                        {
                            "Tax Codes": {},
                            "Measures": {
                                "Tax Group": "Group A",
                                "Item Tax Group": "Group B"
                            },
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

2. Sprawdź, czy opcja **Obniżenie podatku od sprzedaży** w zakładce **Konfiguracja** w szczegółach linii zamówienia sprzedaży jest włączona.

    - Jeśli jest włączona, kody podatkowe są określane na podstawie wartości **Grupy podatkowej** i **Grupy podatkowej danej pozycji**, które wprowadzasz w wierszu transakcji. Sprawdź, czy te wartości zostały wprowadzone poprawnie.
    - Jeśli nie jest ona włączona, sprawdź, czy zostały ustawione prawidłowe wartości w polach **Zastosowanie grupy podatkowej** i **Zastosowanie grupy podatkowej dla danej pozycji**. Aby uzyskać więcej informacji, zobacz [Nie znaleziono pasującego wyniku](tcs-troubleshooting-no-matching-result.md).

3. Jeśli grupa podatkowa i grupa podatkowa elementu zostały określone poprawnie, sprawdź, czy istnieje dla nich nachodzenia na siebie.

    1. W RCS przejdź do **Funkcje podatkowe** \> **Kody i grupy podatkowe** \> **Grupa podatkowa**.

        | Grupa Line.Tax | Kody podatków |
        |----------------|-----------|
        | Grupa A        | A         |

    2. Przejdź do **Funkcje podatkowe** \> **Kody i grupy podatkowe** \> **Grupa podatków pozycji**.

        | Grupa podatkowa Line.Item | Kody podatków |
        |---------------------|-----------|
        | Grupa B             | mld         |

    Jeśli nie między grupą podatkową a grupą podatkową artykułu nie ma zbieżności, kod podatkowy nie zostanie ustalony.

## <a name="mitigation"></a>Sposób minimalizacji

1. Przejdź przez każdy krok w sekcji [Rozwiązywanie problemów](#troubleshoot) tego artykułu i popraw ustawienia, jeśli jest to konieczne. Jeśli grupa podatkowa i grupa podatkowa przedmiotu nie zostały poprawnie określone, zobacz [Nie znaleziono pasującego wyniku](tcs-troubleshooting-no-matching-result.md).
2. Jeśli nie ma przecięcia między grupą podatkową a grupą podatkową przedmiotów, stwórz nową wersję w RCS i popraw ustawienia.

    - Przejdź do **Funkcje podatkowe** \> **Kody i grupy podatkowe** > **Grupa podatków pozycji**.

        | Grupa podatkowa Line.Item | Kody podatków |
        |---------------------|-----------|
        | Grupa B             | A;B       |

    Kod podatkowy zostanie określony jako **A**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
