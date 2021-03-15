---
title: Oblicz prognozę pozycji
description: W tym temacie wyjaśniono, jak obliczać prognozę pozycji w Zarządzaniu składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetItemForecast
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 155dc720804196ccc44fad5eaf71e3563a9c68cf
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5022565"
---
# <a name="calculate-item-forecast"></a>Oblicz prognozę pozycji

[!include [banner](../../includes/banner.md)]

 

Podobnie jak w przypadku obliczeń obciążenia zdolności produkcyjnych, które opisano w poprzedniej sekcji, można również ustawić obliczenia prognozy pozycji dla:

- wierszy harmonogramu konserwacji  
- zleceń pracy, które nie zostały jeszcze zaplanowane  
- zaplanowanych zleceń pracy

Jest to przydatne w przypadku, gdy użytkownik chce uzyskać przegląd oczekiwanego zużycia towarów (części zamiennych oraz innych towarów wymaganych do ukończenia zleceń pracy) w określonym okresie. Obliczanie prognozy pozycji można wykonać dla wszystkich składników majątku lub wybranych składników majątku. Można również dokonać obliczeń dotyczących działania dotyczącego przestojów związanych z konserwacją(**Wszystkie działania w ramach przerwy konserwacyjnej** lub **Aktywne działania w ramach przerwy konserwacyjnej**) lub pulą zleceń pracy (**Wszystkie pule zleceń pracy** lub **Aktywne pule zleceń pracy**).

1. Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Prognoza dla pozycji** lub **Zarządzanie składnikami majątku** > **Wspólne** > **Pule zleceń pracy** > **Wszystkie pule zleceń pracy** / **Aktywne pule zleceń pracy** > na liście wybierz pulę zleceń pracy > przycisk **Prognoza dla pozycji** lub **Zarządzanie składnikami majątku** > **Wspólne** > **Działania w ramach przerwy konserwacyjnej** > **Wszystkie działania w ramach przerwy konserwacyjnej** / **Aktywne działania w ramach przerwy konserwacyjnej** > wybierz czynność w ramach przerwy konserwacyjnej z listy > przycisk **Prognoza dla pozycji**.

2. W oknie dialogowym **Oblicz prognozę dla pozycji** wybierz okres, w którym zostaną wykonane obliczenia w polach **Data/godzina rozpoczęcia** i **Data/godzina zakończenia**.

3. Należy wybrać wartość „tak” na przełączniku **Uwzględnij harmonogram konserwacji**, jeśli wiersze obsługi harmonogramu konserwacji mają zostać uwzględnione w obliczeniach prognozy.

4. Należy wybrać wartość „tak” na przełączniku **Uwzględnij zlecenie pracy**, jeśli zadania zlecenia pracy mają zostać uwzględnione w obliczeniach prognozy.

5. Pola **Poziom** można użyć, aby wskazać, jak szczegółowe mają być wiersze prognozy dla pozycji dotyczące lokalizacji czynności konserwacyjnych. 

      Jeśli na przykład w polu wstawiono liczbę „1” i istnieje wielopoziomowa struktura lokalizacji czynności konserwacyjnych, wszystkie wiersze kontroli harmonogramu konserwacji i zlecenia pracy w lokalizacji czynności konserwacyjnych będą wyświetlane na najwyższym poziomie, dlatego godziny w wierszu mogą być dodawane z lokalizacji czynności konserwacyjnych znajdujących się na niższym poziomie. 
  
      W przypadku wstawienia liczby „0” w polu **Poziom** zostanie wyświetlony szczegółowy wynik zawierający wszystkie wiersze harmonogramu konserwacji i wszystkie zlecenia pracy na każdym poziomie lokalizacji czynności konserwacyjnych, z którymi są powiązane.

6. Kliknij przycisk **OK**, aby rozpocząć obliczanie.

7. W grupach **Grupuj wg...** kliknij odpowiednie przyciski, aby wyświetlić wymagany poziom szczegółowości obliczania. Na poniższym zrzucie ekranu wybrane przyciski **Grupuj wg** są wyróżniane kolorem niebieskim. Aby uaktywnić lub dezaktywować przycisk, należy go kliknąć.

8. Kliknij przycisk **Wyświetl wymiary**, jeśli chcesz wyświetlić wymiary produktu, magazynu lub śledzenia związane z towarami. Wybierz odpowiednie pola wyboru i kliknij **OK**.

![Rysunek 1](media/02-capacity-planning.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]