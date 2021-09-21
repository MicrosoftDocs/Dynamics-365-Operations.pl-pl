---
title: Maksymalna liczba miejsc dziesiętnych dla jednostki magazynowej wynosi 0
description: 'Podczas próby zaksięgowania transakcji magazynowej lub rezerwacji zapasów zostanie wyświetlony komunikat o błędzie: „Maksymalna liczba miejsc dziesiętnych dla jednostki magazynowej wynosi 0”.'
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 9dec198e2d77efd2253c80e14d15791cc37f88e1
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477347"
---
# <a name="maximum-number-of-decimals-for-the-stock-keeping-unit-is-0"></a>Maksymalna liczba miejsc dziesiętnych dla jednostki magazynowej wynosi 0


## <a name="symptoms"></a>Objawy

Podczas próby zaksięgowania transakcji magazynowej lub rezerwacji zapasów zostanie wyświetlony następujący komunikat o błędzie:

> Maksymalna liczba miejsc dziesiętnych dla jednostki magazynowej wynosi 0.

Ten problem występuje, gdy ilość transakcji magazynowej jest określona jako wartość dziesiętna poniżej poziomu dokładności, który obsługuje to pole. Na przykład dla transakcji magazynowej określono ilość *0,5*, ale są obsługiwane tylko liczby całkowite. Dlatego powinna to być wartość *1*, a nie *0,5*.

## <a name="resolution"></a>Rozwiązanie

1. Uruchom następujący skrypt w wystąpieniu programu SQL Server, aby zaokrąglić ilości w transakcjach magazynowych. Ten skrypt spowoduje poprawienie wartości w tabeli **inventTrans**.

    ```sql
    update it set it.QTY = round(it.qty, decimalPrecisionValue) from inventtrans it where it.DATAAREAID='XXXX' and it.PARTITION=XXXXXX and it.qty <> round(it.qty, decimalPrecisionValue) and exists (select 'x' from INVENTTABLEMODULE a, unitofmeasure b where  a.unitid =b.SYMBOL and a.partition=it.partition and a.PARTITION=b.PARTITION and  MODULETYPE =0 and  b.DECIMALPRECISION=decimalPrecisionValue and a.DATAAREAID='XXXX' and a.ITEMID =it.ITEMID and it.DATAAREAID=a.DATAAREAID)
    ```

1. Uruchom sprawdzanie spójności dostępnych zapasów, dla których włączono opcję **poprawiania błędu**. Ten test spowoduje poprawienie wartości w tabeli **inventSum**.

> [!IMPORTANT]
> Zdecydowanie zalecamy uważne edytowanie skryptu zgodnie z wymaganiami środowiska, testowanie go w środowisku testowym, a następnie sprawdzanie wynikowych danych przed uruchomieniem skryptu w środowisku produkcyjnym.
