---
title: Używająca pozycja
description: W tym temacie opisano sposób uzyskiwania przeglądu miejsca użycia towaru w Zarządzaniu składnikami majątku.
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
ms.openlocfilehash: 84ab803aedf5b803b6c5f39ff1907726335cb45d
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918333"
---
# <a name="item-where-used"></a>Używająca pozycja

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Można dokonać obliczeń dla konkretnego towaru, aby uzyskać przegląd informacji o miejscu użycia towaru w module Zarządzanie składnikami majątku. Wyniki zawierają kontekst, w którym towar został użyty w czasie jego istnienia. Z menu Zarządzanie środkiem trwałym można otworzyć **Używająca pozycja**, a także uzyskać do niej dostęp z następujących stron:

[BOM składnika majątku](../objects/object-BOM.md)

[Części zamienne w domyślnym typie składnika majątku](../setup-for-objects/object-types.md)

[Prognoza pozycji dla prognozy domyślnego typu zadań konserwacji](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md)

[Prognoza konserwacji zlecenia pracy](../work-orders/maintenance-forecasts.md)

[Zapotrzebowanie na zakup zlecenia pracy](../work-orders/procurement.md)

[Zakup zlecenia pracy](../work-orders/procurement.md)

## <a name="make-an-item-where-used-calculation"></a>Umożliwia obliczanie użycia pozycji w miejscu

1. Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Używająca pozycja** lub wybierz **Używająca pozycja** na jednej ze stron wymienionych powyżej.

2. W oknie **Używająca pozycja** wybierz towar, dla którego chcesz dokonać obliczeń w polu **Kod towaru** .

3. Pola **Poziom** można użyć, aby wskazać, jak szczegółowe mają być wiersze dla pozycji dotyczące lokalizacji czynności konserwacyjnych. Jeśli na przykład w polu zostanie wstawiony numer „1”, a istnieje struktura lokalizacji funkcjonalnej z wieloma poziomami, wszystkie wiersze pozycji dla lokalizacji funkcjonalnej będą wyświetlane na najwyższym poziomie. Relacja/ilość w wierszu można więc dodać z lokalizacji funkcjonalnych znajdujących się na niższym poziomie. W przypadku wstawienia liczby „0” w polu **Poziom** zostanie wyświetlony szczegółowy wynik zawierający wszystkie wiersze pozycji na każdym poziomie lokalizacji czynności konserwacyjnych, z którymi są powiązane.

4. Należy wybrać wartość „tak” na przełączniku, który ma być uwzględniony w obliczeniach w sekcji **Uwzględnij**.

5. Kliknij przycisk **OK**, aby rozpocząć obliczanie.

6. Na karcie **Używająca pozycja** > w grupach okienka akcji **Grupuj wg...** kliknij odpowiednie przyciski, aby wyświetlić wymagany poziom szczegółowości obliczania. Wybrane przyciski okienka akcji są wyróżnione. Aby uaktywnić lub dezaktywować przycisk, należy go kliknąć.

7. Aby wyświetlić wymiary powiązane z danym towarem, kliknij przycisk **Wyświetl wymiary** i wybierz wymiary, które mają zostać wyświetlone.

Na poniższym rysunku widać przykład obliczeń dla pozycji użytej dla towaru o kodzie „1000”.

![Rysunek 1](media/12-controlling-and-reporting.png)

