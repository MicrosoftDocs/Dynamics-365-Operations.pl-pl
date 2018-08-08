--- 
title: "Definiowanie możliwości zasobu"
description: "Możliwości zasobu opisują, jakie operacje może wykonywać zasób."
author: sorenva
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 99c230c0e6a580f77d863b6f0be298615966c479
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="define-resource-capabilities"></a>Definiowanie możliwości zasobu

[!include [task guide banner](../../includes/task-guide-banner.md)]

Możliwości zasobu opisują, jakie operacje może wykonywać zasób. Podczas planowania wymagania poszczególnych zadań i operacji są dopasowywane do możliwości dostępnych zasobów. Ten przewodnik po zadaniach pomoże Ci utworzyć możliwość zasobu i przypisać ją do zasobu. Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.


## <a name="create-a-resource-capability"></a>Tworzenie możliwości zasobu
1. Przejdź do okna Możliwości zasobu.
2. Kliknij przycisk Nowy.
3. W polu Możliwość wpisz identyfikator możliwości zasobu.
    * Dla danej operacji można użyć identyfikatora możliwości w celu określenia, że zasoby muszą używać tej możliwości do wykonania operacji.  
4. W polu Opis wprowadź opis możliwości.

## <a name="assign-capability-to-a-resource"></a>Przypisywanie możliwości do zasobu
1. Kliknij przycisk Dodaj.
2. W polu Zasób wpisz identyfikator zasobu.
    * Możliwość zasobu można przypisać do jednego lub więcej zasobów.  
3. W polu Data wygaśnięcia wprowadź datę.
    * W tym polu można określić, że zasób posiada możliwość tylko przez określony czas.  
4. W polu Priorytet wprowadź liczbę.
    * Podczas planowania zadań i operacji można określić, czy zasoby będą wybierane według priorytetu. Jeśli wybierzesz tę opcję, a do wskazanego dnia zadanie lub operacja może być wykonywana przez więcej niż jeden zasób, zostanie wybrany zasób, który ma najniższy priorytet w odniesieniu do wymaganej możliwości.  
5. W polu Poziom wprowadź liczbę.
    * Po określeniu, że zadanie lub operacja wymaga określonej możliwości, można także określić minimalny wymagany poziom. Użyj poziomu możliwości w celu odróżnienia zasobów, które mogą wykonać to samo zadanie, ale z różną szybkością, siłą, rozmiarami itd.  


