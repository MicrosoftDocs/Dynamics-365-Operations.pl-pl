---
title: Niepoprawna wartość pola w rekordzie TaxTrans
description: Ten temat zawiera informacje dotyczące rozwiązywania problemów z niepoprawnymi wartościami pola w rekordzie TaxTrans.
author: EricWangChen
ms.date: 04/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 6d4e7fd1bae56c5a7cb9a1a558a5344b3e555e83
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8687596"
---
# <a name="incorrect-field-value-in-taxtrans"></a>Niepoprawna wartość pola w rekordzie TaxTrans

[!include [banner](../includes/banner.md)]

Jeśli wartość pola w rekordzie **TaxTrans** jest niepoprawna, użyj informacji z tego tematu, aby spróbować rozwiązać ten problem.

## <a name="overview-of-values"></a>Przegląd wartości
Na poniższej liście pokazano, że zestawy danych **TaxTrans**, **TaxUncommitted** i **TmpTaxWorkTrans** są do siebie podobne, ale różnią się sposobem działania.

  - **TaxTrans** jest wynikiem ostatniej zaksięgowanej transakcji podatkowej utrwalonym w bazie danych.
  - **TaxUncommitted** to pośredni obliczony wynik podatku utrwalony w bazie danych (jeśli ma zastosowanie), który będzie używany później podczas księgowania.
  - **TmpTaxWorkTrans** to tymczasowy obliczony wynik podatku w tabeli w pamięci (typ tabeli = InMemory).

Znalezienie przyczyny niepoprawnej kolumny **TaxTrans** oznacza także znalezienie głównej przyczyny niepoprawnej kolumny **TaxUncommitted** lub **TmpTaxWorkTrans**. Wynika to z tego, że te trzy kolumny są z siebie kopiowane.

Zwykle podczas obliczania podatku jest generowany rekord **TmpTaxWorkTrans**, a następnie ewentualnie rekord **TaxUncommitted**. Podczas księgowania podatku jest generowany rekord **TaxTrans**.


## <a name="add-breakpoints"></a>Dodawanie punktów przerwania
Aby dodać punkty przerwania, wykonaj następujące kroki: 

1. Dodaj rozszerzenia i punkty przerwania w *insert()* and *update()* w rozszerzeniach w sposób pokazany poniżej.

     - **TaxTrans**

        ```x++
        [ExtensionOf(tableStr(TaxTrans))]
        public final class TaxTrans_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - **TaxUncommitted**

        ```x++
        [ExtensionOf(tableStr(TaxUncommitted))]
        public final class TaxUncommitted_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - **TmpTaxWorkTrans**

        ```x++
        [ExtensionOf(tableStr(TmpTaxWorkTrans))]
        public final class TmpTaxWorkTrans_Extension
        {
            public void insert(boolean _ignoreCalculatedSalesTax)
            {
                next insert(_ignoreCalculatedSalesTax);
            }
        
            public void update(boolean _ignoreCalculatedSalesTax)
            {
                next update(_ignoreCalculatedSalesTax);
            }
        
        }
        
        ```

2. Możesz również dodać punkty przerwania bezpośrednio w przypadku braku rekordu **TaxUncommitted**.

     - *TaxTrans.insert()*, *TaxTrans.update()*
     - *TmpTaxWorkTrans.insert()*, *TmpTaxWorkTrans.update()*

## <a name="reproduce-and-debug"></a>Odtwarzanie i debugowanie

Po skonfigurowaniu punktów przerwania każda zmiana utrwalania danych jest widoczna podczas debugowania. Aby znaleźć główną przyczynę niepoprawnej kolumny **TaxTrans**, **TaxUncommitted** lub **TmpTaxWorkTrans**, zbadaj następujące warunki:

- Ostatni punkt przerwania, w którym kolumna jest poprawna.
- Pierwszy punkt przerwania, w którym kolumna jest niepoprawna.
- Co się dzieje między tymi dwoma punktami.

## <a name="determine-whether-customization-exists"></a>Określanie, czy dostosowanie istnieje
Jeśli zostały wykonane kroki w poprzednich sekcjach, ale nie rozwiązano problemu, określ, czy istnieje dostosowanie. Jeśli nie istnieją żadne dostosowania, skontaktuj się z pomocą techniczną firmy Microsoft, aby uzyskać pomoc.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

