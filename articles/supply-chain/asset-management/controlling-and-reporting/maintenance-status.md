---
title: Stan konserwacji
description: W tym temacie wyjaśniono, jak obliczyć stan konserwacji w Zarządzaniu składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 516607c056125a16e075c33f3c2ad069efb396d9
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918356"
---
# <a name="maintenance-status"></a>Stan konserwacji

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

W module Zarządzanie składnikami majątku można wykonać obliczenia w celu przejrzenia informacji o nowych, aktywnych i zakończonych żądaniach obsługi, zleceniach i czynnościach związanych z konserwacją w określonym okresie. Można również wyświetlić liczbę zakończonych ocen stanu dla tego samego okresu. To obliczenie umożliwia uzyskanie przeglądu obciążenia pracą dotyczącą przychodzących i zakończonych żądań obsługi oraz zleceń produkcyjnych.

## <a name="make-a-maintenance-status-calculation"></a>Dokonaj obliczenia stan konserwacji

1. Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Stan konserwacji**.

2. W oknie dialogowym **Oblicz stan** wstaw okres, dla którego chcesz dokonać obliczeń w polach **Od dnia** i **Do dnia**.

3. Pola **Poziom** można użyć, aby wskazać, jak szczegółowe mają być wierszekonserwacji dotyczące lokalizacji czynności konserwacyjnych. Jeśli na przykład w polu wstawiono liczbę „1” i istnieje wielopoziomowa struktura lokalizacji czynności konserwacyjnych, wszystkie wiersze konserwacji dla lokalizacji czynności konserwacyjnych będą wyświetlane na najwyższym poziomie, dlatego godziny w wierszu mogą być dodawane z lokalizacji czynności konserwacyjnych znajdujących się na niższym poziomie. W przypadku wstawienia liczby „0” w polu **Poziom** zostanie wyświetlony szczegółowy wynik zawierający wszystkie wiersze konserwacji na każdym poziomie lokalizacji czynności konserwacyjnych, z którymi są powiązane.

4. Kliknij przycisk **OK**, aby rozpocząć obliczanie.

5. W **Grupuj wg...** grupach okienka akcji, kliknij odpowiednie przyciski, aby wyświetlić wymagany poziom szczegółowości obliczania. Wybrane przyciski okienka akcji są wyróżnione. Aby uaktywnić lub dezaktywować przycisk, należy go kliknąć.

6. Pamiętaj o kliknięciu przycisku **Aktualizuj**, aby zaktualizować obliczenia za każdym razem, gdy dokonywane są zmiany, aktywując lub dezaktywując przyciski **Grupuj wg...** lub przez obliczenie dla nowego okresu.

7. Kliknij przycisk **stan**, jeśli chcesz utworzyć nowe Obliczanie stanu eksploatacji.

>[!NOTE]
>Wyniki wyświetlane w **stanie konserwacji** obejmują tylko żądania obsługi i zlecenia, które mają rzeczywistą datę i godzinę rozpoczęcia. Data i godzina zakończenia mogą być puste

*Przykład 1:*

Na poniższym rysunku aktywowano przyciski **rok** i **miesiąc**. W tym miejscu można uzyskać ogólny przegląd informacji na temat miesięcznego obciążenia pracą i produktywności związanych z żądaniami obsługi i zleceniami produkcyjnymi. 

![Rysunek 1](media/13-controlling-and-reporting.png)

*Przykład 2:*

Na poniższym rysunku zostały dodane informacje o lokalizacjach czynności konserwacyjnych. Teraz możliwe jest porównanie obciążenia i przepływności między lokalizacjami czynności konserwacyjnych, które mogą reprezentować lokalizacje geograficzne, fabryki lub obszary robocze. 

![Rysunek 2](media/14-controlling-and-reporting.png)

