---
title: Ulepszenie wydajności aktywacji struktury konta
description: Ten artykuł zawiera objaśnienia dotyczące nowych usprawnień wydajności dla procesu aktywacji struktury konta.
author: RyanCCarlson2
ms.date: 10/31/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2022-10-08
ms.dyn365.ops.version: 10.0.31
ms.openlocfilehash: 42f8fcebba6465261489f74a9bb1dd46c2d5fa16
ms.sourcegitcommit: c6c2486be2359bd30106f7f52bda788239147d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2022
ms.locfileid: "9714008"
---
# <a name="account-structure-activation-performance-enhancement"></a>Ulepszenie wydajności aktywacji struktury konta

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Usprawnienie wydajności umożliwia szybsze aktywowanie struktur kont przez uruchamianie wielu aktualizacji transakcji jednocześnie. Ponadto sama struktura jest oznaczana jako aktywna po sprawdzaniu jej poprawności, a przetwarzanie transakcji może być kontynuowane, dopóki istniejące niezaksięgowane transakcje są aktualizowane do nowej struktury. Aktualizacje transakcji mogą nieco potrwać, więc można śledzić stan aktywacji, wybierając pozycję **Wyświetl stan aktywacji** powyżej siatki na stronie **Struktury kont**. Stan aktywacji można również wyświetlić, wybierając pozycję **Wyświetl** w okienku akcji, a następnie wybierając **Stan aktywacji** z menu rozwijanego.

[![Strona struktur kont.](./media/AccountStructure1.png)](./media/AccountStructure1.png)

Po wybraniu opcji **Wyświetl stan aktywacji** pojawi się okno dialogowe z poszczególnymi zadaniami uruchomionymi w ramach procesu aktywacji. Dla każdego zadania można wyświetlić stan oraz datę i czas ukończenia po jego zakończeniu.

[![Oś czasu aktywacji struktury konta.](./media/AccountStructureTimeline.png)](./media/AccountStructureTimeline.png)

## <a name="account-structure-activation-tips"></a>Aktywacja struktury konta — wskazówki

Okno dialogowe aktywacji struktury konta wyświetlane po wybraniu opcji **Aktywuj** dla struktury konta w wersji roboczej zawiera obszar karty o nazwie **Aktualizuj niezaksięgowane transakcje**. Ten obszar zawiera opcję o nazwie **Wymuszaj aktualizację**. Zaznaczenie tej opcji spowoduje zaktualizowanie wszystkich niezaksięgowanych transakcji do bieżącej struktury. Tej opcji należy jednak używać tylko w przypadku wystąpienia błędu lub po otrzymaniu takiego polecenia od pomocy technicznej firmy Microsoft.

Oto niektóre z czynników, które mogą wpływać na wydajność procesu aktywacji:

- Duża liczba niezaksięgowanych rekordów arkusza
- Duża liczba otwartych rekordów dokumentu źródłowego, takich jak faktury niezależne, faktury od dostawców i dokumenty pokrewne, które korzystają ze struktury dokumentów źródłowych i mają otwarte zasady podziału księgowań
- Ilość danych w TaxUncommitted
- Ilość danych otwartego budżetu
- Import danych arkusza przy wciąż uruchomionych zadaniach aktywacji

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
