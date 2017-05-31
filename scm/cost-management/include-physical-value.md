---
title: "Włącz wartość fizyczną"
description: "Pole wyboru Włącz wartość fizyczną na skróconej karcie Model magazynu na stronie Grupy modeli pozycji służy do określania, czy przy obliczaniu średniej kroczącej kosztu własnego towaru są uwzględniane fizycznie zaktualizowane transakcje."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventModelGroup
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 79033
ms.assetid: 1928c145-bf82-436d-87ca-e7a173e31923
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 2d45e7a56851f3f4ac7a7d2d8c4ca9f23b6535fc
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="include-physical-value"></a>Włącz wartość fizyczną

[!include[banner](../includes/banner.md)]


Pole wyboru Włącz wartość fizyczną na skróconej karcie Model magazynu na stronie Grupy modeli pozycji służy do określania, czy przy obliczaniu średniej kroczącej kosztu własnego towaru są uwzględniane fizycznie zaktualizowane transakcje.

Pole wyboru **Włącz wartość fizyczną** ma następujące wartości.

| Wartość    | Wynik                                                                                                                          |
|----------|---------------------------------------------------------------------------------------------------------------------------------|
| Wybrano | Do obliczania średniej kroczącej kosztu własnego są używane transakcje zaktualizowane fizycznie i finansowo. |
| Zaakceptowane  | Do obliczania średniej kroczącej kosztu własnego są używane tylko transakcje zaktualizowane finansowo.                                     |

To pole wyboru działa nieco inaczej zależnie od wybranego modelu zapasów.

-   Zaznaczenie pola wyboru **Włącz wartość fizyczną** w przypadku używania modelu zapasów FIFO (pierwszy na wejściu, pierwszy na wyjściu), LIFO (ostatni na wejściu, pierwszy na wyjściu) lub LIFO wg daty, zamknięcie zapasów powoduje korekty również transakcji zaktualizowanych fizycznie.
-   Jeśli przy używaniu tych modeli zapasów nie zaznaczysz pola wyboru **Włącz wartość fizyczną**, zamknięcie zapasów spowoduje rozliczenie tylko z transakcjami zaktualizowanymi finansowo.
-   W przypadku używania modelu zapasów Średnia ważona lub Średnia ważona z datą zamknięcie zapasów spowoduje rozliczenie tylko transakcji zaktualizowanych finansowo, niezależnie od tego, czy zaznaczono pole wyboru **Włącz wartość fizyczną**.

**Przykład 1** Zaznaczono pole wyboru **Włącz wartość fizyczną** i przyjęto następujące zamówienia zakupu:

-   Zamówienie zakupu na ilość 2 z kosztem własnym 10,00 zł, które zostało zaktualizowane przez dokument dostawy
-   Zamówienie zakupu na ilość 3 z kosztem własnym 12,00 zł, które zostało zaktualizowane przez fakturę

W tym przypadku średnia krocząca kosztu własnego wyniesie 11,20 zł, ponieważ do jego obliczenia są używane transakcje zaktualizowane fizycznie i finansowo. **Przykład 2** Nie zaznaczono pola wyboru **Włącz wartość fizyczną**, a koszt własny w konfiguracji towaru wynosi 10,00 zł. Przyjęto zamówienie zakupu na ilość 20 z kosztem własnym 12,00 zł, które zostało zaktualizowane przez dokument dostawy. Podczas księgowania zamówienia sprzedaży zaksięgowana kwota kosztu wyniesie 10,00 zł, ponieważ średnia krocząca kosztu własnego nie będzie uwzględniała transakcji zaktualizowanych fizycznie. **Uwaga:** Jeśli dla tego towaru zostałoby zaznaczone pole wyboru **Włącz wartość fizyczną**, podczas księgowania zamówienia sprzedaży zaksięgowana kwota kosztu wynosiłaby 12,00 zł.




