---
title: Tworzenie raportu zużycia
description: W tym temacie wyjaśniono, jak utworzyć raporty zużycia w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/21/2019
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
ms.openlocfilehash: 3d978f8b991211e477dd8f766fe67432d9d493d0
ms.sourcegitcommit: c0b581e4c647b6c47bc14d1d7bfe267832afecba
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/21/2019
ms.locfileid: "1913104"
---
# <a name="create-consumption-reports"></a>Tworzenie raportu zużycia

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Po utworzeniu i zaksięgowaniu rejestracji zużycia w zleceniach pracy w module Zarządzanie składnikami majątku dostępne są dwa raporty umożliwiające wyświetlenie szczegółów zużycia.


## <a name="asset-consumption-report"></a>Raport zużycia składnika majątku

Po zaksięgowaniu zużycia w zleceniach pracy można wydrukować raport dotyczący zużycia składnika majątku. W raporcie są wyświetlane godziny, koszty godzinowe, koszty towarów i wydatki zaksięgowane dla składników majątku.

1. Kliknij **Zarządzanie składnikami majątku** > **Raporty** > **Składniki majątku** > **Zużycie składnika majątku**.

2. W oknie dialogowym **Zużycie składnika majątku** wybierz parametry i poziom szczegółów, które chcesz wyświetlić, wybierając w odpowiednich przyciskach opcję „tak”, a następnie wstawiając poziom lokalizacji funkcjonalnej w sekcji **Pokaż**.
    - Pola **Poziom** można użyć, aby wskazać, jak szczegółowe mają być wiersze składnika majątku dotyczące lokalizacji czynności konserwacyjnych. Jeśli na przykład w polu wstawiono liczbę „1” i istnieje struktura lokalizacji czynności konserwacyjnych wielopoziomowa, wszystkie wiersze usterek składniku majątku w lokalizacji czynności konserwacyjnych będą wyświetlane na najwyższym poziomie, dlatego godziny w wierszu mogą być dodawane z lokalizacji czynności konserwacyjnych znajdujących się na niższym poziomie. W przypadku wstawienia liczby „0” w polu **Poziom** zostanie wyświetlony szczegółowy wynik zawierający wszystkie składniki majątku na każdym poziomie lokalizacji czynności konserwacyjnych, z którymi są powiązane. 
    - Wybierz wartość „tak” na przycisku **Suma wszystkich podrzędnych składników majątku**, aby wyświetlić sumy dla poszczególnych podrzędnych składików majątku w raporcie.

3. Wybierz interwał dat w sekcji **Daty**.

4. Na skróconej karcie **Miejsce docelowe** wybierz opcję, czy raport ma być wyświetlany na ekranie, wydrukowany lub zapisany jako plik lub wiadomość e-mail.

5. W razie potrzeby można wybrać określone składniki majątku, które mają być wyświetlane w raporcie. Na skróconej karcie **Rekordy do uwzględnienia** kliknij **Filtruj**, a następnie dodaj składniki majątku, które mają zostać uwzględnione w raporcie.

6. Kliknij przycisk **OK**. Raport zostanie wygenerowany.


## <a name="work-order-consumption-report"></a>Raport zużycia zlecenia pracy

Po zaksięgowaniu zużycia w zleceniach pracy można wydrukować raport dotyczący zużycia zlecenia pracy. W raporcie są wyświetlane godziny, koszty godzinowe, koszty towarów i wydatki zaksięgowane dla zlecenia pracy.

1. Kliknij kolejno **Zarządzanie składnikami majątku** > **Reporty** > **Zlecenia pracy** > **Zużycie zlecenia pracy**.

2. W oknie dialogowym **Zużycie zlecenia pracy** wybierz parametry, które mają zostać uwzględnione w raporcie, klikając opcję tak w odpowiednich przyciskach w sekcji **Pokaż**.

3. Wybierz interwał dat w sekcji **Daty**.

4. Na skróconej karcie **Miejsce docelowe** wybierz opcję, czy raport ma być wyświetlany na ekranie, wydrukowany lub zapisany jako plik lub wiadomość e-mail.

5. W razie potrzeby można wybrać określone zlecenia pracy, które mają być wyświetlane w raporcie. Na skróconej karcie **Rekordy do uwzględnienia** kliknij **Filtruj**, a następnie dodaj zlecenia pracy, które mają zostać uwzględnione w raporcie.

6. Kliknij przycisk **OK**. Raport zostanie wygenerowany.


>[!NOTE]
>Można również wygenerować [raport zlecenia pracy](../work-orders/work-order-report.md) zawierający więcej szczegółów zlecenia.

