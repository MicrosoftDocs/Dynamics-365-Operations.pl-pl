---
title: Tworzenie raportu zużycia
description: W tym artykule wyjaśniono, jak utworzyć raporty zużycia w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 08/21/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 136d6248db8012e5870e0627ddbd3703aa63703b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852908"
---
# <a name="create-consumption-reports"></a>Tworzenie raportu zużycia

[!include [banner](../../includes/banner.md)]

 

Po utworzeniu i zaksięgowaniu rejestracji zużycia w zleceniach pracy w module Zarządzanie składnikami majątku dostępne są dwa raporty umożliwiające wyświetlenie szczegółów zużycia.


## <a name="asset-consumption-report"></a>Raport zużycia składnika majątku

Po zaksięgowaniu zużycia w zleceniach pracy można wydrukować raport dotyczący zużycia składnika majątku. W raporcie są wyświetlane godziny, koszty godzinowe, koszty towarów i wydatki zaksięgowane dla składników majątku.

1. Kliknij **Zarządzanie składnikami majątku** > **Raporty** > **Składniki majątku** > **Zużycie składnika majątku**.

2. W oknie dialogowym **Zużycie składnika majątku** wybierz parametry i poziom szczegółów, które chcesz wyświetlić, wybierając w odpowiednich przyciskach opcję **Tak**, a następnie wstawiając poziom lokalizacji czynności konserwacyjnych w sekcji **Pokaż**.
    - Pola **Poziom** można użyć, aby wskazać, jak szczegółowe mają być wiersze składnika majątku dotyczące lokalizacji czynności konserwacyjnych. 
    
        Jeśli na przykład w polu wprowadzono liczbę „1” i istnieje wielopoziomowa struktura lokalizacji czynności konserwacyjnych, wszystkie składniki majątku w lokalizacji czynności konserwacyjnych będą wyświetlane na najwyższym poziomie, dlatego wartości w wierszu mogą być dodawane z lokalizacji czynności konserwacyjnych znajdujących się na niższym poziomie. 
        
        W przypadku wprowadzenia liczby „0” w polu **Poziomy** zostanie wyświetlony szczegółowy wynik zawierający wszystkie składniki majątku na każdym poziomie lokalizacji czynności konserwacyjnych, z którym są one powiązane. 
        
    - Wybierz wartość **Tak** na przycisku **Suma wszystkich podrzędnych składników majątku**, aby wyświetlić sumy dla poszczególnych podrzędnych składników majątku w raporcie.

3. Wybierz interwał dat w sekcji **Daty**.

4. Na skróconej karcie **Miejsce docelowe** wybierz opcję, czy raport ma być wyświetlany na ekranie, wydrukowany lub zapisany jako plik lub wiadomość e-mail.

5. W razie potrzeby można wybrać określone składniki majątku, które mają być wyświetlane w raporcie. Na skróconej karcie **Rekordy do uwzględnienia** kliknij **Filtruj**, a następnie dodaj składniki majątku, które mają zostać uwzględnione w raporcie.

6. Kliknij przycisk **OK**. Raport zostanie wygenerowany.


## <a name="work-order-consumption-report"></a>Raport zużycia zlecenia pracy

Po zaksięgowaniu zużycia w zleceniach pracy można wydrukować raport dotyczący zużycia zlecenia pracy. W raporcie są wyświetlane godziny, koszty godzinowe, koszty towarów i wydatki zaksięgowane dla zlecenia pracy.

1. Kliknij kolejno **Zarządzanie składnikami majątku** > **Reporty** > **Zlecenia pracy** > **Zużycie zlecenia pracy**.

2. W oknie dialogowym **Zużycie zlecenia pracy** wybierz parametry, które mają zostać uwzględnione w raporcie, klikając opcję **Tak** w odpowiednich przyciskach w sekcji **Pokaż**.

3. Wybierz interwał dat w sekcji **Daty**.

4. Na skróconej karcie **Miejsce docelowe** wybierz opcję, czy raport ma być wyświetlany na ekranie, wydrukowany lub zapisany jako plik lub wiadomość e-mail.

5. W razie potrzeby można wybrać określone zlecenia pracy, które mają być wyświetlane w raporcie. Na skróconej karcie **Rekordy do uwzględnienia** kliknij **Filtruj**, a następnie dodaj zlecenia pracy, które mają zostać uwzględnione w raporcie.

6. Kliknij przycisk **OK**. Raport zostanie wygenerowany.


>[!NOTE]
>Można również wygenerować [raport zlecenia pracy](../work-orders/work-order-report.md) zawierający więcej szczegółów zlecenia.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]