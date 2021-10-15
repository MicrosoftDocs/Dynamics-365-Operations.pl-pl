---
title: Obiekty kosztów
description: Ten artykuł zawiera informacje o obiektach kosztów. Wyjaśniono w nim też sposób kumulowania kosztów i ilości. Obiekt kosztów to jednostka, dla której są kumulowane koszty i ilości. Jednostką obiektu kosztów może być produkt lub wariant produktu, takich jak wariant pod względem koloru i stylu.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19451
ms.assetid: ec776b98-813a-490d-848f-468452d98fac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d27e2dcfd8f70c8d4b0f2ae1254f3c4fce63bb4d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572176"
---
# <a name="cost-objects"></a>Obiekty kosztów

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje o obiektach kosztów. Wyjaśniono w nim też sposób kumulowania kosztów i ilości. Obiekt kosztów to jednostka, dla której są kumulowane koszty i ilości. Jednostką obiektu kosztów może być produkt lub wariant produktu, takich jak wariant pod względem koloru i stylu.  

## <a name="cost-objects"></a>Obiekty kosztów

Na stronie **Obiekty kosztów** znajduje się lista wszystkich obiektów kosztów, które są zarejestrowane dla produktu. Obiekty kosztów są definiowane na podstawie danych z następujących źródeł:

-   Produkt
-   Grupa wymiarów produktu
-   Grupa wymiarów magazynowania
-   Grupa wymiarów śledzenia

**Uwaga:** obiekt kosztu reprezentuje tylko element kosztów typu **Materiały bezpośrednie**. Obiekt kosztów i obiekt magazynu różnią się od siebie tym, że obiekt kosztów jest definiowany przez wymiary magazynowe, które są wybrane dla magazynu finansowego. Towar może na przykład mieć następującą konfigurację:

-   **Witryna:** Magazyn fizyczny = Tak, Magazyn finansowy = Tak
-   **Magazyn:** Magazyn fizyczny = Tak, Magazyn finansowy = Nie
-   **Nr partii:** Magazyn fizyczny = Tak, Magazyn finansowy = Nie

W poniższej tabeli przedstawiono, co jest przedmiotem kosztu i co jest obiektem magazynu.

| Typ obiektu      | Numer pozycji | Oddział | Magazyn | Numer partii |
|------------------|-------------|------|-----------|-----------|
| Obiekt kosztów      | x           | x    |           |           |
| Obiekt magazynu | x           | x    |  x        | x         |

## <a name="accumulation-of-costs-and-quantities"></a>Akumulacja kosztów i ilości
-   Pole **Wartość** zawiera sumę z następujących wartości:
    -   Fizyczna wartość kosztu
    -   Wartość finansowa
    -   Korekty
-   Pole **Ilość** zawiera sumę z następujących wartości:
    -   Odebrano
    -   Wydane
    -   Zaksięgowana ilość
-   Pole **Średni koszt jednostkowy** jest polem obliczanym. Wartość jest obliczana przez podzielenie wartości **Wartość** przez wartość **Ilość**.

**Uwaga:** Parametr **Włącz wartość fizyczną** nie ma wpływu na wcześniejsze obliczenia.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Grupa wymiarów produktu](/dynamicsax-2012/appuser-itpro/about-product-dimensions)

[Grupa wymiarów magazynowania](/dynamicsax-2012//storage-dimension-groups-form)

[Grupa wymiarów śledzenia](/dynamicsax-2012//tracking-dimension-groups-form)

[Nowości i zmiany](../../fin-ops-core/fin-ops/get-started/whats-new-changed.md)

[Wpisy kosztów](cost-entries.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]