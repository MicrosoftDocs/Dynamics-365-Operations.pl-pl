---
title: Dodawanie działania poprzedzającego do działania przepływu produkcji
description: W wersji przepływu produkcji wszystkie działania muszą być ustawione kolejno.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dc1aa742013faeeb545d746f9715c639a5b66b9b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7575082"
---
# <a name="add-a-predecessor-to-a-production-flow-activity"></a>Dodawanie działania poprzedzającego do działania przepływu produkcji

[!include [banner](../../includes/banner.md)]

W wersji przepływu produkcji wszystkie działania muszą być ustawione kolejno. Działanie może mieć jeden lub wiele zdarzeń poprzedzających lub następujących. 

Ta procedura pokazuje, jak skojarzyć zdarzenie poprzedzające z działaniem. 

Do wykonania zadania potrzebujesz przepływ produkcji, który ma wersję roboczą z co najmniej dwoma działaniami, które mogą być połączone. 

Aby uzyskać więcej informacji, zobacz oficjalny dokument „Przepływy produkcji i działania w produkcji oszczędnej”.


## <a name="find-the-production-flow-and-version"></a>Znajdowanie przepływu produkcji i wersji
1. Wybierz kolejno opcje Kontrola produkcji > Ustawienia > Przepływ produkcji oszczędnej > Przepływy produkcji.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Na liście kliknij łącze w wybranym wierszu.
4. Na liście znajdź i zaznacz odpowiedni rekord.
5. Kliknij opcję Działania.

## <a name="select-an-activity-and-add-a-predecessor"></a>Wybór działania i dodawanie zdarzenia poprzedzającego
1. Na liście znajdź i zaznacz odpowiedni rekord.
2. Kliknij opcję Dodaj zdarzenie poprzedzające.
3. Wprowadź lub wybierz wartość w polu Działanie.
4. W polu Wskaźnik czasu cyklu wpisz liczbę.
    * Domyślny współczynnik czasu cyklu dla relacji działań wynosi 1. Zakłada on, że oba działania są wykonywane w tym samym tempie lub czasie taktu. Jeżeli zdarzenie poprzedzające jest wykonywane w szybszym tempie (niższym czasie taktu), współczynnik powinien być niższe niż 1. Jeżeli zdarzenie poprzedzające odbywa się w wolniejszym tempie (wyższy czas taktu), współczynnik czasu cyklu jest większy niż 1.  
5. Kliknij przycisk OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]