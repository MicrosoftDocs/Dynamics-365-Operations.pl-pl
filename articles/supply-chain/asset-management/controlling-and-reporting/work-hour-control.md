---
title: Kontrola godzin pracy
description: W tym temacie opisano typy kontroli godzin pracy w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetHourControl
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0d2f4e86b5dec84d4a24db6a4f9f9f16f6a765bd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435117"
---
# <a name="work-hour-control"></a>Kontrola godzin pracy

[!include [banner](../../includes/banner.md)]

 

W module Zarządzanie składnikami majątku możesz obliczyć godziny, aby uzyskać przegląd rzeczywistych godzin w porównaniu z godzinami budżetowymi dotyczącymi zasobów, lokalizacji czynności konserwacyjnych lub zleceń pracy. Godziny rzeczywiste są oparte na zaksięgowanych transakcjach.

## <a name="work-hour-control-for-assets-functional-locations-and-work-orders"></a>Kontrola godzin dla składników majątku, lokalizacji czynności konserwacyjnych i zleceń pracy

Obliczenia wykonane dla składników majątku, lokalizacji czynności konserwacyjnych i zleceń pracy są prawie identyczne. Tylko różnica polega na tym, że dla składników i lokalizacji czynności konserwacyjnych można uwzględnić w obliczeniach także podpozycje i podlokalizacje. Data jest datą transakcji, w której rejestracja została zarejestrowana.

1. Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Składniki majątku** > **Formant godzin składnika majątku** lub **Formant godzin lokalizacji czynności konserwacyjnych** lub **Zarządzanie składnikami majątku** > **Zapytania** > **Zlecenia pracy** > **Formant godzin zlecenia pracy**.

2. W oknie **Formant godzin składnika majątku**.

3. W **Formant godzin składnika majątku** / **Formant godzin lokalizacji czynności konserwacyjnych** / **Formant godzin zlecenia pracy** oknie dialogowym wybierz okres, który ma zostać obliczony w polach **od dnia** i **do dnia**.

4. W razie potrzeby wybierz **zbiór wymiarów finansowych**, który ma być uwzględniany w obliczeniach.

5. Wybierz wartość „tak” w przełączniku **Pomiń zero**, jeśli nie chcesz wyświetlać wyników z zero godzin.

6. Pola **Poziom** można użyć, aby wskazać, jak szczegółowe mają być wiersze kontroli godzin dotyczące lokalizacji czynności konserwacyjnych. 

    Jeśli na przykład w polu wstawiono liczbę „1” i istnieje wielopoziomowa hierarchia lokalizacji czynności konserwacyjnych, wszystkie wiersze kontroli godzin usterek składniku majątku w lokalizacji czynności konserwacyjnych będą wyświetlane na najwyższym poziomie, dlatego godziny w wierszu mogą być dodawane z lokalizacji czynności konserwacyjnych znajdujących się na niższym poziomie. 
    
    W przypadku wstawienia liczby „0” w polu **Poziom** zostanie wyświetlony szczegółowy wynik zawierający wszystkie wiersze kontroli godzin na każdym poziomie lokalizacji czynności konserwacyjnych, z którym jest powiązany.

7. Wybierz wartość „tak” na przycisku przełącznika **Uwzględnij środki trwałe**, aby wyświetlić koszty związane z środkami podrzędnymi w postaci oddzielnych wierszy.

8. Aby ograniczyć wyszukiwanie, można wybrać określone składniki majątku / lokalizacje czynności konserwacyjnych / zlecenia pracy w skróconej karcie **Rekordy do uwzględnienia**.

9. Kliknij przycisk **OK**, aby rozpocząć obliczanie.

10. Na stronie **Formant godzin składnika majątku** kliknij przyciski **Grupuj wg**, aby wyświetlić wymagany poziom szczegółowości obliczania. Wybrane przyciski grupy **Grupuj wg...** są wyróżnione. Aby uaktywnić lub dezaktywować przycisk, należy go kliknąć.

## <a name="example"></a>Przykład

Na poniższym zrzucie ekranu pokazano przykład obliczania **Formant godzin składnika majątku**.

- W polu **Budżet pierwotny** są wyświetlane godziny budżetowe z prognozy zlecenia pracy. 
- W polu **Rzeczywiste godziny** są wyświetlane zaksięgowane godziny w zleceniach pracy. 
- W polu **Ustalone godziny** są wyświetlane łączne godziny, na które firma jest zobowiązana w związku ze zleceniami pracy.

![Przykład obliczania kontroli godzin składnika majątku](media/04-controlling-and-reporting.png)

Innym sposobem obliczenia godziny jest wielokrotne wybranie składników majątku w **Wszystkie składniki majątku** lub **Aktywne składniki majątku**. Następnie należy kliknąć przycisk **Formant godzin** na skróconej karcie **Ogólne**. Wybrane środki trwałe są automatycznie wstawiane do pola **Składnik majątku** na skróconej karcie **Rekordy do uwzględnienia**. Kliknij **OK** woknie dialogowym **Formant godzin składnika majątku**, a następnie zostanie wyświetlona wartość obliczona dla wybranych składników. Tę samą procedurę można wykonać w odniesieniu do lokalizacji czynności konserwacyjnych we **Wszystkie lokalizacje czynności konserwacyjnych** lub **Aktywne lokalizacje czynności konserwacyjnych** lub przypadku zleceń pracy **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.


