---
title: Amortyzacja według zużycia
description: Ten artykuł zawiera omówienie metody amortyzacji Amortyzacja według zużycia.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: kfend
ms.custom: 13751
ms.assetid: d25a681f-49a5-4bfc-aa76-1c6373e35dd8
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e5597e2d960f5d6393515370d3495b77569191b5
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/05/2022
ms.locfileid: "8712405"
---
# <a name="consumption-depreciation"></a>Amortyzacja według zużycia

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera omówienie metody amortyzacji Amortyzacja według zużycia.

Jeśli podczas ustawiania profilu amortyzacji środków trwałych zaznaczono opcję **Zużycie** w polu **Metoda** na stronie **Profile amortyzacji**, środki trwałe będą przypisane do profilu amortyzacji na podstawie ich zużycia. Nie trzeba ustawiać wartość procentowych i interwałów na stronie **Profile amortyzacji**. Po utworzeniu profilu amortyzacji używającego metody Zużycie można ustawić metodę na różne sposoby.

## <a name="set-up-and-use-consumption-depreciation"></a>Konfigurowanie i używanie amortyzacji według zużycia
1.  Utwórz profil amortyzacji na stronie **Profile amortyzacji**. Do obliczeń zużycia profil amortyzacji musi zawierać identyfikator i nazwę, a w polu **Metoda** trzeba zaznaczyć **Zużycie**.
2.  Na stronie **Współczynniki zużycia** ustaw współczynniki zużycia. Każdy współczynnik zużycia musi mieć identyfikator i nazwę, i musi być wyrażony jako ilość lub wartość procentowa.
3.  Na stronie **Jednostki zużycia** ustaw jednostki zużycia. Każda jednostka zużycia musi mieć identyfikator i nazwę. Jednostki amortyzacji są używane do obliczania amortyzacji wg zużycia na stronie **amortyzacji według zużycia**. Przykładowymi jednostkami są km, kg i godzina.
4.  Na stronie **środki trwałe** ustaw poszczególne środki trwałe. Dla każdego środka trwałego wybierz modele ewidencji i księgi amortyzacji z profilami amortyzacji. Należy ustawić modele ewidencji lub księgi amortyzacji dla amortyzacji według zużycia, jeśli jakikolwiek ze środków trwałych używa profili amortyzacji opartych na metodzie Zużycia. Ta konfiguracja jest przeprowadzana albo na karcie **amortyzacji** na stronie **Modele ewidencji**, albo na skróconej karcie **Ogólne** na stronie **profilu amortyzacji**. Jeden model ewidencji można stosować dla wielu środków trwałych. Profile amortyzacji są częścią modelu ewidencji lub księgi amortyzacji wybranych dla każdego środka trwałego. Nie można dodawać lub modyfikować profili amortyzacji bezpośrednio na stronie **Środki trwałe**. Profile amortyzacji można zmodyfikować tylko na stronie **ksiąg amortyzacji**.
5.  Na stronie **Modele ewidencji** lub **Księgi amortyzacji** w grupie pól **amortyzacji według zużycia** wprowadź informacje w następujących polach:
    -   Współczynnik zużycia
    -   Jednostka
    -   Jednostka amortyzacji
    -   Szacunkowe zużycie

    W polu **Zaksięgowane zużycie** jest wyświetlona wartość amortyzacji według zużycia (w jednostkach), która została już zaksięgowana w modelu ewidencji środków trwałych lub w księdze amortyzacji. Wartość w tym polu nie można ręcznie zmienić wartości.

## <a name="examples"></a>Przykłady
### <a name="example-1"></a>Przykład 1

31 stycznia ustawiono następujący współczynnik zużycia:

-   Ilość wynosi 1000.
-   Jednostka amortyzacji, która jest określona dla środka trwałego, wynosi 1,5.

Propozycja amortyzacji na 31 stycznia jest następująca: ilość x jednostka amortyzacji 1000 x 1,5 = 1500, jeśli współczynnik określony dla środka trwałego ustawiono jako procentowy, ilość, którą oblicza się w polu **szacowane zużycie** dla modelu ewidencji środka trwałego jest mnożona przez wartość procentową ustawioną dla wybranej daty końcowej. Tak obliczona ilość jest sugerowana jako wielkość amortyzacji dla okresu.

### <a name="example-2"></a>Przykład 2

Dla 31 stycznia ustawiono następujący współczynnik amortyzacji według zużycia:

-   Wartość procentowa wynosi 10 procent.
-   Jednostka amortyzacji, która jest określona dla środka trwałego, wynosi 1,5.
-   Szacowana ilość środka trwałego wynosi 2000.

Propozycja amortyzacji na 31 stycznia jest w następująca: szacowana ilość x procent x Jednostka amortyzacji 2000 x 0,10 x 1,5 = 300





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
