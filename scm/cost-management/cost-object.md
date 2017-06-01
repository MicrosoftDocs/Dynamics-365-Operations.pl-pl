---
title: "Obiekty kosztów"
description: "Ten artykuł zawiera informacje o obiektach kosztów. Wyjaśniono w nim też sposób kumulowania kosztów i ilości. Obiekt kosztów to jednostka, dla której są kumulowane koszty i ilości. Jednostką obiektu kosztów może być produkt lub wariant produktu, takich jak wariant pod względem koloru i stylu."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19451
ms.assetid: ec776b98-813a-490d-848f-468452d98fac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: c818bfac6645b71bcc8b2249534aa80907786651
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="cost-objects"></a>Obiekty kosztów

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera informacje o obiektach kosztów. Wyjaśniono w nim też sposób kumulowania kosztów i ilości. Obiekt kosztów to jednostka, dla której są kumulowane koszty i ilości. Jednostką obiektu kosztów może być produkt lub wariant produktu, takich jak wariant pod względem koloru i stylu.  

<a name="cost-objects"></a>Obiekty kosztów
------------

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

<a name="see-also"></a>Informacje dodatkowe
--------

[Grupa wymiarów produktu](https://technet.microsoft.com/en-us/library/aa499382.aspx)

[Grupa wymiarów magazynowania](https://technet.microsoft.com/en-us/library/hh209317.aspx)

[Grupa wymiarów śledzenia](https://technet.microsoft.com/en-us/library/hh209465.aspx)

[Nowości i zmiany w systemie Microsoft Dynamics AX](/dynamics365/operations/dev-itpro/get-started/whats-new-changed)

[Wpisy kosztów](cost-entries.md)




