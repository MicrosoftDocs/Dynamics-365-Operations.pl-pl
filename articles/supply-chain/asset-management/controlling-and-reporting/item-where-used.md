---
title: Używająca pozycja
description: W tym temacie opisano sposób uzyskiwania przeglądu miejsca użycia towaru w Zarządzaniu składnikami majątku.
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetItemWhereUsed, EntAssetItemWhereUsedCalculate
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 262a5a9d83767599f6e15183d6afcacf4b5901fe
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808647"
---
# <a name="item-where-used"></a>Używająca pozycja

[!include [banner](../../includes/banner.md)]

 

Można dokonać obliczeń dla konkretnego towaru, aby uzyskać przegląd informacji o miejscu użycia towaru w module Zarządzanie składnikami majątku. Wyniki zawierają kontekst, w którym towar został użyty w czasie jego istnienia. Stronę **Używająca pozycja** można otworzyć z głównego menu modułu Zarządzanie składnikami majątku, a także uzyskać do niej dostęp z następujących stron:

- [Obiekty BOM składnika majątku](../objects/object-BOM.md)

- [Części zamienne w domyślnym typie składnika majątku](../setup-for-objects/object-types.md#spare-parts-on-the-asset-type-setup)

- [Kategorie typów zadań obsługi i typy zadań serwisowych, warianty typu zadań obsługi, handel zadaniami konserwacyjnymi oraz listy kontrolne konserwacji](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md)

- [Prognoza konserwacji](../work-orders/maintenance-forecasts.md)

- [Zaopatrzenie](../work-orders/procurement.md)

- [Zakup zlecenia pracy](../work-orders/procurement.md)

## <a name="make-an-item-where-used-calculation"></a>Umożliwia obliczanie użycia pozycji w miejscu

1. Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Używająca pozycja** lub wybierz **Używająca pozycja** na jednej ze stron wymienionych powyżej.

2. W oknie **Używająca pozycja** wybierz towar, dla którego chcesz dokonać obliczeń w polu **Kod towaru** .

3. Pola **Poziom** można użyć, aby wskazać, jak szczegółowe mają być wiersze dla pozycji dotyczące lokalizacji czynności konserwacyjnych. 

    Jeśli na przykład w polu zostanie wstawiony numer „1”, a istnieje struktura lokalizacji funkcjonalnej z wieloma poziomami, wszystkie wiersze pozycji dla lokalizacji funkcjonalnej będą wyświetlane na najwyższym poziomie. Relacja/ilość w wierszu można więc dodać z lokalizacji funkcjonalnych znajdujących się na niższym poziomie. 
    
    W przypadku wstawienia liczby „0” w polu **Poziom** zostanie wyświetlony szczegółowy wynik zawierający wszystkie wiersze pozycji na każdym poziomie lokalizacji czynności konserwacyjnych, z którymi są powiązane.

4. Należy wybrać wartość „tak” na przełączniku, który ma być uwzględniony w obliczeniach w sekcji **Uwzględnij**.

5. Kliknij przycisk **OK**, aby rozpocząć obliczanie.

6. Na karcie **Używająca pozycja** wybierz przyciski **Grupuj wg**, aby wyświetlić wymagany poziom szczegółowości obliczania. Wybrane przyciski grupy **Grupuj wg...** są wyróżnione. Aby uaktywnić lub dezaktywować przycisk, należy go kliknąć.

7. Aby wyświetlić wymiary powiązane z danym towarem, kliknij przycisk **Wyświetl wymiary** i wybierz wymiary, które mają zostać wyświetlone.

## <a name="example"></a>Przykład

Na poniższym zrzucie ekranu widać przykład obliczeń dla pozycji używającej towaru o kodzie „1000”.

![Przykład obliczenia dla używającej pozycji](media/12-controlling-and-reporting.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]