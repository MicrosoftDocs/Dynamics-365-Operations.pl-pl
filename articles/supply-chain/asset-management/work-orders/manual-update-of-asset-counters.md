---
title: Ręczna aktualizacja liczników zasobów
description: W tym temacie opisano ręczną aktualizację liczników składników majątku w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetCounter
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5318bac961682f88e192ac70c4993c62b69b399c
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020892"
---
# <a name="manual-update-of-asset-counters"></a>Ręczna aktualizacja liczników zasobów

[!include [banner](../../includes/banner.md)]



Liczniki służą do tworzenia rejestracji na składnikach majątku, takich jak rejestracje dotyczące liczby godzin eksploatacji składnika majątku lub ilości, która została wyprodukowana.

Typ licznika wybrany dla licznika może być skonfigurowany do dziedziczenia wartości liczników. Innymi słowy, opcja **Dziedzicz wartości licznika** ustawiona na wartość **Tak** na skróconej karcie **Ogólne** na stronie **Liczniki** (**Zarządzanie składnikami majątku** > **Konfiguracja** > **Typy składników majątku** > **Liczniki**). W takim przypadku podczas tworzenia nowego wiersza licznika tego typu każdy podrzędny składnik, który używa tego samego typu licznika, jest automatycznie aktualizowany.

Na stronie **Wszystkie składniki majątku** można tworzyć godziny lub rejestracje liczników ilości dla składnika w oparciu o odczyty w składniku.

1. Wybierz **Zarządzanie składnikami majątku** > **Wspólne** > **Składniki majątku** > **Wszystkie składniki majątku**.

2. Wybierz środek trwały, a następnie w okienku akcji na karcie **Składnik majątku** w grupie **Zapobiegawcze** wybierz pozycję **Liczniki**. Na stronie **Liczniki składników majątku** zostanie wyświetlona lista wszystkich poprzednich rejestracji liczników, które zostały wykonane dla wybranego składnika.

3. Wybierz pozycję **Nowy**, aby utworzyć nową rejestrację. Identyfikator składnika majątku jest automatycznie wprowadzana w polu **Składnik majątku**.

4. W polu **Licznik** wybierz odpowiedni licznik. Do wyboru dostępne są tylko liczniki powiązane z typem składnika wybranego w obszarze zawartości. Jednostka powiązana jest automatycznie wstawiana w polu **Jednostka**.

5. W polu **Zarejestrowano** wybierz datę i godzinę rejestracji licznika.

6. W polu **Wartość** wprowadź liczbę od ostatniej rejestracji licznika. Można również w polu **Zagregowana wartość** wprowadzić łączną liczbę.

Należy uwzględnić następujące informacje:

- W przypadku fizycznego zainstalowania nowego licznika dla składnika majątku należy zarejestrować zmianę składnika majątku na stronie **Liczniki składników majątku**. Następnie należy utworzyć dwa wiersze rejestracji o identycznych sygnaturach czasowych. Pierwszy wiersz musi dotyczyć zastępowanego licznika. W wierszu, który jest powiązany z nowym licznikiem, zaznacz pole wyboru **Resetuj licznik**. W polu **Sumy całkowite** wartość sumy całkowitej jest sumą wszystkich zarejestrowanych wartości licznika z danego typu licznika.

- Jeśli zaznaczono pole wyboru **Resetuj licznik** na składniku majątku, należy użyć planu konserwacji z typem interwału „jeden raz od...” lub „po osiągnięciu...”, licznik jest nadal aktywny w nowym wierszu licznika, ponieważ tworzona jest oddzielna linia licznika i rozpoczyna się od nowego licznika.

Na poniższej ilustracji przedstawiono przykład strony **Liczniki składników majątku**.

![Rysunek 1](media/11-work-orders.png)

Na stronie **Liczniki składników majątku** (**Zarządzanie składnikami majątku** > **Zapytania** > **Składniki majątku** > **Liczniki składników majątku**) można w tym samym czasie przeprowadzać rejestracje liczników dla kilku składników majątku wedle potrzeby.

>[!NOTE]
>Istnieje możliwość skonfigurowania zakresu w celu zdefiniowania odchyleń dla ręcznej rejestracji licznika. Można również określić typ komunikatu, który będzie wyświetlany, jeśli rejestracje znajdują się poza zdefiniowanym zakresem. Aby uzyskać więcej informacji na temat sposobu konfigurowania liczników, zobacz [Liczniki](../setup-for-objects/counters.md).

