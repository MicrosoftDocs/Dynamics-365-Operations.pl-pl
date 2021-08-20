---
title: Rozwiązywanie problemów z konfiguratorem produktów
description: W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z konfiguratorem produktów.
author: SmithaNataraj
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: f09ca4e69ca4bd3e87ee425c483b7a338045a0f28312a92b154fa07eb125927a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6772503"
---
# <a name="troubleshoot-the-product-configurator"></a>Rozwiązywanie problemów z konfiguratorem produktów

W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z konfiguratorem produktów.

## <a name="item-text-is-overwritten-when-i-configure-a-product-on-a-sales-order-line"></a>Podczas konfigurowania produktu w wierszu zamówienia sprzedaży tekst towaru jest zastępowany.

### <a name="issue-description"></a>Opis problemu

Ten problem występuje podczas tworzenia wiersza zamówienia sprzedaży dla towaru konfigurowalnego, a następnie modyfikowania tekstu towaru. Po skonfigurowaniu towaru i wybraniu opcji **OK** tekst jest zastępowany tekstem standardowym.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

To zachowanie jest oczekiwane. Pole tekstowe zawiera nazwę wariantu, która jest wypełniana tylko po skonfigurowaniu wiersza. Dlatego należy zmienić tekst po skonfigurowaniu wiersza, a nie przed.

## <a name="integer-attributes-are-incorrectly-rounded-when-product-configuration-models-are-calculated"></a>Atrybuty liczb całkowitych są niepoprawnie zaokrąglane w przypadku obliczania modeli konfiguracji produktu.

### <a name="issue-description"></a>Opis problemu

Ten problem może wystąpić w przypadku wykonywania następującej serii akcji:

1. Ustaw następujące atrybuty w modelu konfiguracji produkcji:

    - Dane wejściowe (liczba całkowita)
    - Procent (dziesiętny)
    - Wynik (liczba całkowita)

2. Utwórz obliczanie z następującymi wyrażeniami:

    *Wynik* = *Dane wejściowe* × *Procent* ÷ 100

W tym przypadku wynik liczby całkowitej nie zawsze jest poprawnie zaokrąglony. Na przykład wartość wejściowa to 1000, a wartością procentową jest 2,40. Dlatego oczekiwana liczba całkowita to 24, ponieważ 2,40 procent z 1000 wynosi 24 (lub 24,00 w postaci dziesiętnej). Zamiast tego wynik jest pokazywany jako 23. Jeśli jednak wartość procentowa wynosi 2,39, obliczenia są zaokrąglane do 24 zamiast 23. Gdy wartość procentowa wynosi 2,50, obliczenia są zaokrąglane do 25, zgodnie z oczekiwaniami.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Ten problem występuje ze względu na sposób, w jaki Microsoft Solver Foundation wewnętrznie reprezentuje liczby przy użyciu ułamków. W przypadku poprzedniego przykładu wynik obliczeń w przypadku, gdy procent wynosi 2,40, jest reprezentowany jako 27021597764222975 ÷ 1125899906842624 = 23,99999999999999911182158029987476766109466552734375. Gdy platforma .NET rzutuje tę wartość na liczbę całkowitą, zwróci wartość 23.

To zachowanie nie zostanie zmienione, ponieważ zależą od niego inne scenariusze. W powyższym przykładzie można rozwiązać ten problem, wprowadzając dodatkowy atrybut dziesiętny i obliczenie.

Na przykład można ustawić następujące atrybuty w modelu konfiguracji produkcji:

- Dane wejściowe (liczba całkowita)
- Procent (dziesiętny)
- ResultDecimal (liczba dziesiętna)
- ResultInteger (liczba całkowita)

Można dodać następujące obliczenia:

- *ResultDecimal* = *Dane wejściowe* × *Procent* ÷ 100
- *ResultInteger* = *ResultDecimal*


[!INCLUDE[footer-include](../../includes/footer-banner.md)]