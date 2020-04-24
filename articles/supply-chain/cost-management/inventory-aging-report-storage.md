---
title: Raport wiekowania zapasów
description: W tym temacie opisano funkcje umożliwiające uruchamianie raportu wiekowania zapasów oraz udostępnianie danych wyjściowych w postaci formularza i wykresu.
author: AndersGirke
manager: tfehr
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2019-01-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 790c8fe3a52bce652227f1cef97eff6496476100
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201630"
---
# <a name="inventory-aging-report"></a>Raport wiekowania zapasów


[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

W rozwiązaniu Microsoft Dynamics 365 Supply Chain Management można uruchomić raport **wiekowania zapasów** i udostępnić dane wyjściowe jako formularz i wykres. W formularzu pola kolumny i salda zagregowane są dynamicznie dostosowywane w zależności od skonfigurowanego układu. Wykres zawiera przegląd wizualny obsługujący filtrowanie i umożliwiający drążenie do szczegółów. Ponadto jednostka danych o nazwie **Raport wiekowania zapasów** umożliwia eksportowanie wyników raportu **wiekowania zapasów** do formatu takiego jak plik Microsoft Excel lub plik PDF.

Ta metoda uruchamiania raportu **wiekowania zapasów** jest przydatna w przypadkach, gdy dane wyjściowe zawierają wiele wierszy. Na przykład produkcja będzie zawierała wiele wierszy, jeśli w systemie istnieje 50 000 sztuk i 300 sklepów utworzonych jako magazyny i żąda się przeliczeń zapasów według towarów, oddziału i magazynu.

## <a name="run-an-inventory-aging-report"></a>Przeprowadź raport wiekowania zapasów

1. Przejdź do **Zarządzanie kosztami \> Zapytania i raporty \> Przechowywanie raportu wiekowania zapasów**.
1. Wybierz pozycję **Nowy**.
1. W polu **Nazwa** wprowadź unikatową nazwę raportu.
1. Umożliwia wybór raportu **identyfikacja — ID** i przefiltrowanie go w miarę potrzeb

    Wykonywanie raportu jest zawsze wykonywane w ramach zadania wsadowego.

1. Po zakończeniu zadania wsadowego dane wyjściowe są wyświetlane na stronie **Magazyn raportu wiekowania zapasów**.
1. Aby wyświetlić dane wyjściowe jako formularz z tradycyjnym układem siatki, wybierz opcję **Pokaż szczegóły**. Aby wyświetlić dane wyjściowe jako zagregowany wykres, wybierz opcję **Wyświetl wykres**.

    > [!NOTE]
    > Formularz nie będzie zawierać sum częściowych, które są zdefiniowane w układzie raportu.

Jednostka danych **raportu wiekowania zapasów** umożliwia eksportowanie danych wyjściowych **raportu wiekowania zapasów** przez zastosowanie filtru dla pola **Identyfikator procesu — nazwa** w dowolnym formacie obsługiwanym przez funkcję zarządzania danymi.
