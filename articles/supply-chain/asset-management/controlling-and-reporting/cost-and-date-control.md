---
title: Kontrola kosztu i daty
description: W tym temacie wyjaśniono kontrolę kosztów i dat w module Zarządzanie składnikami majątku.
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
ms.openlocfilehash: 2bcd1584f6a858f7589387fbfe96267b7c16176a
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918402"
---
# <a name="cost-and-date-control"></a>Kontrola kosztu i daty

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

W module Zarządzanie składnikami majątku można obliczać koszty rejestracji usterek składników majątku, aby uzyskać przegląd kosztów rzeczywistych w porównaniu z kosztami budżetowymi składników majątku, loklizacjami czynności konserwacyjnych i zleceniami pracy. Koszty rzeczywiste są oparte na zaksięgowanych transakcjach. Można także wprowadzić obliczenie daty, aby porównać planowane daty rozpoczęcia i zakończenia według rzeczywistych dat rozpoczęcia i zakończenia w zleceniach pracy.

## <a name="cost-control-for-assets-functional-locations-and-work-orders"></a>Kontrola kosztów składników majątku, lokalizacji czynności konserwacyjnych i zleceń pracy

Obliczenia wykonane dla składników majątku, lokalizacji czynności konserwacyjnych i zleceń pracy są prawie identyczne. Tylko różnica polega na tym, że dla składników i lokalizacji czynności konserwacyjnych można uwzględnić w obliczeniach także podpozycje i podlokalizacje. Data jest datą transakcji, w której rejestracja została zarejestrowana.

1. Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Składniki majątku** > **Formant kosztów składników majątku** or **Formant kosztów lokalizacji czynności konserwacyjnych**, or **Zarządzanie składnikami majątku** > **Zapytania** > **Zlecenia pracy** > **Formant kosztów zlecenia pracy**.

2. W oknie dialogowym **Formant kosztów składników majątku** / **Formant kosztów lokalizacji czynności konserwacyjnych** / **Formant kosztów zlecenia pracy** wybierz okres, który ma zostać obliczony.

3. W razie potrzeby wybierz zbiór wymiarów finansowych, który ma być uwzględniany w obliczeniach.

4. Wybierz wartość „tak” w przycisku **Pomiń zero**, jeśli nie chcesz wyświetlać wyników z kosztem zerowym.

5. Pola **Poziom** można użyć, aby wskazać, jak szczegółowe mają być wiersze kontroli kosztów dotyczące lokalizacji czynności konserwacyjnych. Jeśli na przykład w polu wstawiono liczbę „1” i istnieje wielopoziomowa hierarchia lokalizacji czynności konserwacyjnych, wszystkie wiersze kontroli kosztów usterek składniku majątku w lokalizacji czynności konserwacyjnych będą wyświetlane na najwyższym poziomie, dlatego godziny w wierszu mogą być dodawane z lokalizacji czynności konserwacyjnych znajdujących się na niższym poziomie. W przypadku wstawienia liczby „0” w polu **Poziom** zostanie wyświetlony szczegółowy wynik zawierający wszystkie wiersze kontroli kosztów na każdym poziomie lokalizacji czynności konserwacyjnych, z którym jest powiązany.

6. Należy wybrać wartość „tak” na przełączniku **Pokaż otwarty koszt ustalony**, jeśli ta kolumna ma zostać uwzględniona w obliczeniach.

7. Wybierz wartość „tak” na przycisku przełącznika **Uwzględnij środki trwałe**, aby wyświetlić koszty związane z środkami podrzędnymi w postaci oddzielnych wierszy.

8. Aby ograniczyć wyszukiwanie, można wybrać określone składniki majątku / lokalizacje czynności konserwacyjnych / zlecenia pracy w skróconej karcie **Rekordy do uwzględnienia**.

9. Kliknij przycisk **OK**, aby rozpocząć obliczanie.

Na poniższym rysunku pokazano przykład okna dialogowego **Formant kosztów składników majątku**.

![Rysunek 1](media/01-controlling-and-reporting.png)

10. W **Grupuj wg...** grupach okienka akcji na stronie **Formant kosztów składników majątku** kliknij odpowiednie przyciski, aby wyświetlić wymagany poziom szczegółowości obliczania. Wybrane przyciski okienka akcji są wyróżnione. Aby uaktywnić lub dezaktywować przycisk, należy go kliknąć.

Na poniższym rysunku pokazano przykład wyniku obliczania w **Formant kosztów składników majątku**.

![Rysunek 2](media/02-controlling-and-reporting.png)

Innym sposobem obliczenia kosztów jest wielokrotne wybranie składników majątku w **Wszystkie składniki majątku** lub **Aktywne składniki majątku**. Następnie kliknij przycisk **Kontrola kosztów** na karcie **Ogólne**. W oknie dialogowym **Formant kosztów składników majątku** wybrane składniki majątku są automatycznie umieszczane w polu **Składnik majątku** na karcie skróconej **Rekordy do uwzględnienia**. Kliknij **OK** i wyświetlona zostanie kalkulacja kosztów dla wybranych składników majątku. Tę samą procedurę można wykonać w odniesieniu do lokalizacji czynności konserwacyjnych we **Wszystkie lokalizacje czynności konserwacyjnych** lub **Aktywne lokalizacje czynności konserwacyjnych** lub przypadku zleceń pracy **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.

>[!NOTE]
>W polu **Budżet pierwotny** są wyświetlane koszty budżetowe z prognozy zlecenia pracy. Pole **Ustalony koszt** pokazuje całkowitą kwota wydatków, które firma zobowiązała się zapłacić. W polu **Otwarty koszt ustalony** są wyświetlane zobowiązania do zapłaty za towary, godziny i usługi, które zostały zamówione lub przyjęte, ale jeszcze nie zapłacone. Po zaksięgowaniu wszystkich rejestracji zużycia odpowiednie koszty są uwzględniane w polu **Koszt rzeczywisty**.

## <a name="work-order-date-control"></a>Kontrola dat zlecenia pracy

Ta strona umożliwia uzyskanie przeglądu oczekiwanych dat rozpoczęcia i zakończenia w porównaniu z rzeczywistymi datami rozpoczęcia i zakończenia w zleceniach pracy.

1. Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Zlecenia pracy** > **Kontrola dat zlecenia pracy**.

2. Kliknij przycisk **Oblicz**.

3. Wybierz lokalizację czynności koserwacyjnych w polu **Lokalizacja czynności konserwacyjnych**.

4. Wstaw okres, dla którego chcesz dokonać obliczeń w polach **Od dnia** i **Do dnia**. Wszystkie zlecenia pracy z oczekiwanym rozpoczęciem w okresie zostaną uwzględnione.

5. Kliknij przycisk **OK**.

6. W **Grupuj wg...** grupach okienka akcji, kliknij odpowiednie przyciski, aby wyświetlić wymagany poziom szczegółowości obliczania. Wybrane przyciski okienka akcji są wyróżnione. Aby uaktywnić lub dezaktywować przycisk, należy go kliknąć.

Na poniższym rysunku pokazano przykład wyniku obliczania w **Kontrola dat zlecenia pracy**.

![Rysunek 3](media/03-controlling-and-reporting.png)

- Pole **Średnie opóźnienie rozpoczęcia** zawiera różnicę w dniach między planowaną datą rozpoczęcia zlecenia pracy w porównaniu z rzeczywistą datą rozpoczęcia. Jeśli na przykład rzeczywista data rozpoczęcia wypada na dwa dni przed zaplanowaną datą rozpoczęcia, w tym polu zostanie wyświetlona wartość „-2”.  
- Pole **Średnie opóźnienie zakończenia** zawiera różnicę w dniach między planowaną datą końca zlecenia pracy w porównaniu z rzeczywistą datą zakończenia. Jeśli na przykład rzeczywista data zakończenia wypada na dwa dni przed zaplanowaną datą zakończenia, w tym polu zostanie wyświetlona wartość „3”.  
- W polach **Wystąpienia** jest wyświetlana liczba odchyleń w odniesieniu do daty planowanej i rzeczywistej oraz planowana i rzeczywista data zakończenia zlecenia pracy.

