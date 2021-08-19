---
title: Dezaktywowanie wersji przepływu produkcji
description: Gdy aktywna wersja przepływu produkcji nie jest już potrzebna, można ją dezaktywować.
author: cvocph
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 488f5d9e1137be2686f3f3056f4c4543766a16799a2f0484c3c4f0f9f3d456ad
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6726784"
---
# <a name="deactivate-a-production-flow-version"></a>Dezaktywowanie wersji przepływu produkcji

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]