---
title: Liczby całkowite niepoprawnie zaokrąglone w obliczeniach modeli konfiguracji produktu
description: Wyniki w liczbach całkowitych nie są zawsze poprawnie zaokrąglone podczas obliczania modeli konfiguracji produktu. Rozwiąż problem z dodanym atrybutem dziesiętnym i obliczeniem.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: b17145d7d17cb784fe11b3fbf65ddf5aa5530f27
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477327"
---
# <a name="integers-incorrectly-rounded-when-product-configuration-models-are-calculated"></a>Liczby całkowite niepoprawnie zaokrąglone podczas obliczania modeli konfiguracji produktu

## <a name="symptoms"></a>Objawy

Ten problem może wystąpić w przypadku wykonywania następującej serii akcji:

1. Ustaw te atrybuty w modelu konfiguracji produkcji:

    - Dane wejściowe (liczba całkowita)
    - Procent (dziesiętny)
    - Wynik (liczba całkowita)

2. Utwórz obliczanie z następującymi wyrażeniami:

    *Wynik* = *Dane wejściowe* × *Procent* ÷ 100

W tym przypadku wynik liczby całkowitej nie zawsze jest poprawnie zaokrąglony. Jeśli na przykład wartość wejściowa wynosi 1000, a wartość procentowa wynosi 2,40, wynik całkowity wynosi 24, ponieważ 2,40 procent z 1000 to 24 (czyli 24,00 w postaci dziesiętnej). Zamiast tego wynik jest pokazywany jako 23. Jeśli jednak wartość procentowa wynosi 2,39, obliczenia są zaokrąglane do 24 zamiast 23. Gdy wartość procentowa wynosi 2,50, obliczenia są zaokrąglane do 25, zgodnie z oczekiwaniami.

## <a name="cause"></a>Powód

Ten problem występuje ze względu na sposób, w jaki Microsoft Solver Foundation wewnętrznie reprezentuje liczby przy użyciu ułamków. W przypadku poprzedniego przykładu wynik obliczeń w przypadku, gdy procent wynosi 2,40, jest reprezentowany jako 27021597764222975 ÷ 1125899906842624 = 23,99999999999999911182158029987476766109466552734375. Gdy platforma .NET rzutuje tę wartość na liczbę całkowitą, zwróci wartość 23.

## <a name="resolution"></a>Rozwiązanie

To zachowanie nie zostanie zmienione, ponieważ zależą od niego inne scenariusze. W powyższym przykładzie można rozwiązać ten problem, wprowadzając dodatkowy atrybut dziesiętny i obliczenia.

Na przykład ustaw następujące atrybuty w modelu konfiguracji produkcji:

- Dane wejściowe (liczba całkowita)
- Procent (dziesiętny)
- ResultDecimal (liczba dziesiętna)
- ResultInteger (liczba całkowita)

Można dodać następujące obliczenia:

- *ResultDecimal* = *Dane wejściowe* × *Procent* ÷ 100
- *ResultInteger* = *ResultDecimal*
