---
title: Stan konserwacji
description: W tym temacie wyjaśniono, jak obliczyć stan konserwacji w Zarządzaniu składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fbe2b3fd9ce63c34aedb790583dea572d3d9b079
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205485"
---
# <a name="maintenance-status"></a>Stan konserwacji

[!include [banner](../../includes/banner.md)]

 

W module Zarządzanie składnikami majątku można wykonać obliczenia dla określonego okresu w celu przejrzenia informacji o nowych, aktywnych i zakończonych żądaniach obsługi, zleceniach i czynnościach związanych z konserwacją. Można również wyświetlić liczbę zakończonych ocen stanu dla tego samego okresu. To obliczenie umożliwia uzyskanie przeglądu obciążenia pracą dla przychodzących i zakończonych żądań obsługi oraz zleceń produkcyjnych.

## <a name="make-a-maintenance-status-calculation"></a>Dokonaj obliczenia stan konserwacji

1. Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Stan konserwacji**.

2. W oknie dialogowym **Oblicz stan** wybierz zakres czasu, dla którego chcesz dokonać obliczeń w polach **Od dnia** i **Do dnia**.

3. Pola **Poziom** można użyć, aby wskazać, jak szczegółowe mają być wierszekonserwacji dotyczące lokalizacji czynności konserwacyjnych. 

  Jeśli na przykład w polu wstawiono liczbę „1” i istnieje wielopoziomowa struktura lokalizacji czynności konserwacyjnych, wszystkie wiersze konserwacji dla lokalizacji czynności konserwacyjnych będą wyświetlane na najwyższym poziomie, dlatego godziny w wierszu mogą być dodawane z lokalizacji czynności konserwacyjnych znajdujących się na niższym poziomie. 
  
  W przypadku wstawienia liczby „0” w polu **Poziom** zostanie wyświetlony szczegółowy wynik zawierający wszystkie wiersze konserwacji na każdym poziomie lokalizacji czynności konserwacyjnych, z którymi są powiązane.

4. Kliknij przycisk **OK**, aby rozpocząć obliczanie.

5. Kliknij przyciski **Grupuj wg...**, aby wyświetlić wymagany poziom szczegółowości obliczania. Wybrane przyciski grupy **Grupuj wg...** są wyróżnione. Aby uaktywnić lub dezaktywować przycisk, należy go kliknąć.

6. Pamiętaj o kliknięciu przycisku **Aktualizuj**, aby zaktualizować obliczenia za każdym razem, gdy dokonywane są zmiany, aktywując lub dezaktywując przyciski **Grupuj wg...** lub przez wykonianie obliczenia dla nowego okresu.

7. Kliknij przycisk **stan**, jeśli chcesz utworzyć nowe Obliczanie stanu eksploatacji.

>[!NOTE]
>Wyniki wyświetlane w **stanie konserwacji** obejmują tylko żądania obsługi i zlecenia, które mają rzeczywistą datę i godzinę rozpoczęcia. Data i godzina zakończenia mogą być puste

## <a name="example-1"></a>Przykład 1

Na poniższym zrzucie ekranu aktywowano przyciski **rok** i **miesiąc**. Po wybraniu opcji **Grupuj wg...** można uzyskać ogólny przegląd informacji na temat miesięcznego obciążenia pracą i produktywności związanych z żądaniami obsługi i zleceniami produkcyjnymi. 

![Przykład miesięcznego obciążenia pracą](media/13-controlling-and-reporting.png)

## <a name="example-2"></a>Przykład 2

Na poniższym zrzucie ekranu zostały dodane informacje o lokalizacjach czynności konserwacyjnych. Teraz możliwe jest porównanie obciążenia i przepływności między lokalizacjami czynności konserwacyjnych, które mogą reprezentować lokalizacje geograficzne, fabryki lub obszary robocze. 

![Przykład miesięcznego obciążenia pracą z lokalizacjami czynności konserwacyjnych](media/14-controlling-and-reporting.png)

