---
title: Formant kosztów usterki składnika majątku
description: W tym temacie wyjaśniono kontrolę kosztów usterek składników majątku w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetCostControlFault
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3c36fc791fac6cce0433935adb88eb8cdc23003368204a87efc12cf5a419ec9d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6752040"
---
# <a name="asset-fault-cost-control"></a>Formant kosztów usterki składnika majątku

[!include [banner](../../includes/banner.md)]

 

W module Zarządzanie składnikami majątku można obliczać koszty rejestracji usterek składników majątku, aby uzyskać przegląd kosztów rzeczywistych w porównaniu z kosztami budżetowymi. Koszty rzeczywiste są oparte na zaksięgowanych transakcjach. Data jest datą usterki, w której objaw został zarejestrowany.

1. Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Usterka składnika majątku** > **Formant kosztów usterki składnika majątku**.

2. W oknie dialogowym **Formant kosztów usterki składnika majątku** wybierz wymiar finansowy, który ma zostać uwzględniony w obliczeniach.

4. Wybierz wartość „tak” w przycisku **Pomiń zero**, jeśli nie chcesz wyświetlać wyników z kosztem zerowym.

5. Pola **Poziom** można użyć, aby wskazać, jak szczegółowe mają być wiersze kontroli kosztów dotyczące lokalizacji czynności konserwacyjnych. 

    Jeśli na przykład w polu wstawiono liczbę „1” i istnieje wielopoziomowa struktura lokalizacji czynności konserwacyjnych, wszystkie wiersze kontroli kosztów usterek składniku majątku w lokalizacji czynności konserwacyjnych będą wyświetlane na najwyższym poziomie, dlatego godziny w wierszu mogą być dodawane z lokalizacji czynności konserwacyjnych znajdujących się na niższym poziomie. 
    
    W przypadku wstawienia liczby „0” w polu **Poziom** zostanie wyświetlony szczegółowy wynik zawierający wszystkie wiersze kontroli kosztów usterek składnika majątku na każdym poziomie lokalizacji czynności konserwacyjnych, z którym jest powiązany.

6. Aby ograniczyć wyszukiwanie, można wybrać określone składniki majątku, daty usterek i przyczyny usterek w skróconej karcie **Rekordy do uwzględnienia**.

7. Kliknij przycisk **OK**, aby rozpocząć obliczanie.

8. Kliknij przyciski **Grupuj wg...**, aby wyświetlić wymagany poziom szczegółowości obliczania. Wybrane przyciski grupy **Grupuj wg...** są wyróżnione. Aby uaktywnić lub dezaktywować przycisk, należy go kliknąć.

## <a name="example"></a>Przykład

W tym przykładzie przedstawiono obliczenia dotyczące kontroli kosztów usterki składnika majątku.

- W polu **Budżet pierwotny** są wyświetlane koszty budżetowe z prognozy zlecenia pracy. 
- W polu **Koszt rzeczywisty** są wyświetlane zaksięgowane koszty w zleceniach pracy. 
- W polu **Ustalony koszt** są wyświetlane łączne koszty, na które firma jest zobowiązana w związku ze zleceniami pracy.

    ![Rysunek 1.](media/05-controlling-and-reporting.png)

Informacje na temat konfigurowania usterek można znaleźć w temacie [Zarządzanie usterkami](../setup-for-work-orders/fault-management.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]