---
title: Koszt harmonogramu konserwacji
description: W tym temacie wyjaśniono harmonogram konserwacji w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 08/27/2019
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
ms.openlocfilehash: 405fd7fbbbb8862446d09b9ea33ef14348e691f9
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813780"
---
# <a name="maintenance-schedule-cost"></a>Koszt harmonogramu konserwacji

[!include [banner](../../includes/banner.md)]

 

W module Zarządzanie składnikami majątku można obliczać koszty budżetowe w wierszach harmonogramu konserwacji. Jest to przydatne w przypadku uzyskiwania przeglądu oczekiwanych kosztów, na przykład kosztów związanych z planowanymi zadaniami obsługi przeciwdziałania w przyszłym roku. Obliczenia są oparte na istniejących wierszach harmonogramu konserwacji typu „plany konserwacji” i „liczba serii” oraz „żądania konserwacji”.

1. Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Składniki majątku** > **Koszt harmonogramu konserwacji**.

2. W oknie **Koszt harmonogramu konserwacji** można wybrać **Zestaw wymiarów finansowych**, jeśli koszty mają być wyświetlane w wymiarach finansowych.

>[!NOTE]
>Zestawy wymiarów finansowych są konfigurowane w **Księga główna** > **Plan kont** > **Wymairy** > **Zestawy wymiarów finansowych**.

3. Pola **Poziom** można użyć, aby wskazać, jak szczegółowe mają być wiersze harmonogramu konserwacji dla pozycji dotyczące lokalizacji czynności konserwacyjnych. Jeśli na przykład w polu wstawiono liczbę „1” i istnieje wielopoziomowa struktura lokalizacji czynności konserwacyjnych, wszystkie wiersze kontroli harmonogramu konserwacji dla lokalizacji czynności konserwacyjnych będą wyświetlane na najwyższym poziomie, dlatego godziny w wierszu mogą być dodawane z lokalizacji czynności konserwacyjnych znajdujących się na niższym poziomie. W przypadku wstawienia liczby „0” w polu **Poziom** zostanie wyświetlony szczegółowy wynik zawierający wszystkie wiersze harmonogramu konserwacji na każdym poziomie lokalizacji czynności konserwacyjnych, z którymi są powiązane.

4. Jeśli chcesz przeprowadzić obliczenia dla konkretnych składników majątku, kliknij przycisk **Filtruj** na skróconej karcie **Rekordy do uwzględnienia** i wybierz odpowiednie składniki. W razie potrzeby można również określić **Oczekiwane rozpoczęcie** dla obliczenia kosztu lub wybrać inny **Stan** dla obliczenia kosztu.

5. Kliknij przycisk **OK**, aby rozpocząć obliczanie kosztu.

6. Na karcie **Koszt harmonogramu konserwacji** w grupach okienka akcji **Grupuj wg...** kliknij odpowiednie przyciski, aby wyświetlić wymagany poziom szczegółowości obliczania kosztu. Wybrane przyciski grupy okienka akcji są wyróżnione. Aby uaktywnić lub dezaktywować przycisk, należy go kliknąć.

7. Kliknij przycisk **Oblicz koszt**, jeśli chcesz dokonać nowego obliczenia kosztu.

Na poniższej ilustracji przedstawiono wyniki obliczenia kosztów harmonogramu konserwacji.

![Rysunek 1](media/17-preventive-maintenance.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]