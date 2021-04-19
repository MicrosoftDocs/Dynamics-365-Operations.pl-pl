---
title: Oblicz obciążenie wydajności
description: W tym temacie wyjaśniono, jak tworzyć obliczać obciążanie wydajności w Zarządzaniu składnikami majątku.
author: johanhoffmann
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetCapacityLoad, EntAssetWorkOrderCapacityLoadCalculate, EntAssetWorkOrderCapacityLoad
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ba4b9ef43e27f689e1f10d2ee8f10f6ea4bf43ed
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821736"
---
# <a name="calculate-capacity-load"></a>Obliczanie obciążenia zdolności produkcyjnych

[!include [banner](../../includes/banner.md)]


W module Zarządzanie składnikami majątku można obliczać wydajności:

- wierszy harmonogramu konserwacji  
- zleceń pracy, które nie zostały jeszcze zaplanowane  
- zaplanowanych zleceń pracy

Jest to przydatne w przypadku, gdy użytkownik chce uzyskać przegląd spodziewanego obciążenia wydajności w danym okresie. Obliczanie obciążenia wydajności można wykonać dla wszystkich składników majątku lub wybranych składników majątku. Można również dokonać obliczeń dotyczących działań przestojów konserwacyjnych lub pul zleceń pracy.

1. Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Obciążenie wydajności** lub **Zarządzanie składnikami majątku** > **Wspólne** > **Pule zleceń pracy** > **Wszystkie pule zleceń pracy** / **Aktywne pule zleceń pracy** > na liście wybierz pulę zleceń pracy > przycisk **Obciążenie wydajności** lub **Zarządzanie składnikami majątku** > **Wspólne** > **Działania w ramach przerwy konserwacyjnej** > **Wszystkie działania w ramach przerwy konserwacyjnej** / **Aktywne działania w ramach przerwy konserwacyjnej** > wybierz czynność konserwacyjną z listy > przycisk **Obciążenie wydajności**.

2. W oknie dialogowym **Oblicz obciążenie wydajności** wybierz okres, w którym zostaną wykonane obliczenia w polach **Data/godzina rozpoczęcia** i **Data/godzina zakończenia**.

3. Należy wybrać wartość „tak” na przełączniku **Uwzględnij harmonogram konserwacji**, jeśli wiersze obsługi harmonogramu konserwacji mają zostać uwzględnione w obliczeniach.

4. Należy wybrać wartość „tak” na przełączniku **Uwzględnij zlecenie pracy**, jeśli zadania zlecenia pracy mają zostać uwzględnione w obliczeniach.

5. Pola **Poziom** można użyć, aby wskazać, jak szczegółowe mają być wiersze obciążenia wydajności dotyczące lokalizacji czynności konserwacyjnych. 

    Jeśli na przykład w polu wstawiono liczbę „1” i istnieje wielopoziomowa struktura lokalizacji czynności konserwacyjnych, wszystkie wiersze kontroli harmonogramu konserwacji i zlecenia pracy w lokalizacji czynności konserwacyjnych będą wyświetlane na najwyższym poziomie, dlatego godziny w wierszu mogą być dodawane z lokalizacji czynności konserwacyjnych znajdujących się na niższym poziomie. 
    
    W przypadku wstawienia liczby „0” w polu **Poziom** zostanie wyświetlony szczegółowy wynik zawierający wszystkie wiersze harmonogramu konserwacji i wszystkie zlecenia pracy na każdym poziomie lokalizacji czynności konserwacyjnych, z którymi są powiązane.

6. Kliknij przycisk **OK**, aby rozpocząć obliczanie.

7. W grupach **Grupuj wg...** kliknij odpowiednie przyciski, aby wyświetlić wymagany poziom szczegółowości obliczania. Na poniższym zrzucie ekranu wybrane przyciski **Grupuj wg** są wyróżniane kolorem niebieskim. Aby uaktywnić lub dezaktywować przycisk, należy go kliknąć.

    ![Rysunek 1](media/01-capacity-planning.png)

>[!NOTE]
>Aby skoncentrować się tylko na planowaniu zdolności produkcyjnych w odniesieniu do zaplanowanych zleceń pracy, zobacz [Obliczanie obciążenia zdolności produkcyjnych na zaplanowanych zleceniach pracy](../work-order-scheduling/calculate-capacity-load-on-scheduled-work-orders.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]