---
title: Obliczanie obciążenia zdolności produkcyjnych na zaplanowanych zleceniach pracy
description: W tym temacie opisano sposób obliczania obciążenia zdolności produkcyjnych w zaplanowanych zleceniach pracy w module Zarządzanie składnikami majątku
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 09e0fc17a288a278b7b1feaba8c7b73425aa2d52
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808167"
---
# <a name="calculate-capacity-load-on-scheduled-work-orders"></a>Obliczanie obciążenia zdolności produkcyjnych na zaplanowanych zleceniach pracy

[!include [banner](../../includes/banner.md)]

 

Można obliczyć obciążenie zdolności produkcyjnych w zaplanowanych zleceniach pracy, aby uzyskać przegląd obciążenia pracą dla zasobów w danym okresie. Można wykonywać obliczenia dla następujących zasobów: konserwatorzy, grupy pracowników, narzędzia i składniki majątku.

1. Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Harmonogram** > **Obciążenie wydajności**.

2. W oknie dialogowym **Obliczanie obciążenia zdolności produkcyjnych** > pole **Pokaż** wybierz typ obciążenia pracą do obliczenia: **Zdolności produkcyjne**, **Zarezerwowane**” lub **Pozostałe**.

3. Wybierz wartość **Tak**” w przełączniku **Pomiń zero**, jeśli nie chcesz wyświetlać wyników z kosztem zerowym.

4. Wybierz typy zasobów, dla których chcesz obliczyć obciążenie zdolności produkcyjnych, wybierając wartość **Tak** w odpowiednich przełącznikach **Pracownik**, **Grupa konserwatorów**, **Narzędzie** i **Składnik majątku**.

5. Wybierz datę początkową obliczeń w polu **Od dnia**.

6. W polu **Typ zakresu** wybierz zakres dla obliczania: **Dzień**, **Tydzień**, **Miesiąc** lub **Kwartał**.

7. W polu **Częstotliwość okresu** wstaw liczbę zakresów, które mają zostać obliczone. Jeśli na przykład jako typ zakresu wybrano **Dzień**, a w tym polu zostanie wprowadzona liczba „5”, zostanie wykonane obliczenie okresu pięciu dni od daty rozpoczęcia.

8. Kliknij przycisk **OK**, aby rozpocząć obliczanie.

Na poniższym rysunku przedstawiono wynik obliczeń obejmujących trzy tygodnie dla typu ładunku **Zarezerwowane**.

![Rysunek 1](media/08-work-order-scheduling.png)

[!NOTE]
Jeśli w obliczeniach zostanie wybrana opcja **Zdolności produkcyjne** lub **Pozostałe**, zostanie wyświetlony ten sam wynik, jeśli nie wykonano rezerwacji dla zasobów w wybranym okresie.

Aby dowiedzieć się, jak obliczać obciążenia zdolności produkcyjnych w wierszach harmonogramu konserwacji i nieplanowanych zleceniach pracy, zapoznaj się z informacjami w temacie [Obliczanie obciążenia zdolności produkcyjnych](../capacity-planning/calculate-capacity-load.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]