--- 
title: "Dezaktywowanie wersji przepływu produkcji"
description: "Gdy aktywna wersja przepływu produkcji nie jest już potrzebna, można ją dezaktywować."
author: cvocph
manager: AnnBe
ms.date: 10/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 4a7eee6617e12d59a3d06207f5f6b58c93e28240
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="deactivate-a-production-flow-version"></a>Dezaktywowanie wersji przepływu produkcji

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Gdy aktywna wersja przepływu produkcji nie jest już potrzebna, można ją dezaktywować. Tej opcji należy używać tylko wtedy, jeśli wszystkie reguły i działania Kanban zakończyły się i nie będą ponownie uaktywniane. Należy zauważyć, że data ważności wszystkich reguł Kanban odnoszących się do tej wersji przepływu produkcji będzie aktualizowana o bieżącą datę i godzinę. 

Aby zmodyfikować aktywną wersję przepływu produkcji, należy rozważyć ustawienie daty ważności dla aktywnej wersji i utworzenie nowej wersji. To pozwoli kontynuować operacje produkcyjne, jednocześnie przygotowując nową wersję i powiązane reguły Kanban. 

Aby aktywna wersja przepływu produkcji wygasała, należy ustawić datę ważności. W tym sensie dezaktywacja jest raczej wyjątkiem niż regułą. 

Do wykonania tej procedury jest potrzebny przepływ produkcji o wersji, która może być dezaktywowana. Nie próbuj tego w środowisku produkcyjnym, chyba że masz 100-procentową pewność, że wersja jest w pełni przestarzała.


## <a name="deactivate-a-production-flow-version"></a>Dezaktywowanie wersji przepływu produkcji
1. Wybierz kolejno opcje Kontrola produkcji > Ustawienia > Przepływ produkcji oszczędnej > Przepływy produkcji.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Na liście kliknij łącze w wybranym wierszu.
4. Na liście znajdź i zaznacz odpowiedni rekord.
5. Kliknij przycisk Dezaktywuj.
    * Nie kontynuuj, jeśli nie masz 100-procentowej pewności, że ta wersja przepływu produkcji jest przestarzała. Kliknięcie przycisku Ok spowoduje unieważnienie wszystkich aktywnych reguł Kanban oraz natychmiastowe zatrzymanie wszystkich działań produkcji i uzupełniania w tej wersji przepływu produkcji.  
6. Kliknij przycisk OK.


