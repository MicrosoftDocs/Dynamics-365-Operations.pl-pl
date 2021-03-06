---
title: Aktualizacja stanu w systemie Kanban
description: Gdy karta Kanban zostanie opróżniona przez pomyłkę lub otrzymana karta Kanban musi zostać opróżniona, należy zaktualizować stan karty Kanban.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Kanban, KanbanResetEmpty
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5a0e03da4671ffec4ecf4835b20a00ef87971c94
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831824"
---
# <a name="update-kanban-status"></a>Aktualizacja stanu w systemie Kanban

[!include [banner](../../includes/banner.md)]

Gdy karta Kanban zostanie opróżniona przez pomyłkę lub otrzymana karta Kanban musi zostać opróżniona, należy zaktualizować stan karty Kanban. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Ta procedura jest przeznaczona dla kierownika produkcji.


## <a name="find-the-kanban"></a>Znajdź kartę Kanban.
1. Wybierz kolejno opcje Kontrola produkcji > Kanban > Karty Kanban.
2. Otwórz filtr kolumny Stan magazynowej jednostki obsługi.
3. Kliknij przycisk Wyczyść.
    * Spowoduje to zresetowanie filtrów.  
4. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola Numer karty z wartością „000149”.

## <a name="change-emptied-status-to-received-status"></a>Zmiana stanu Opróżniono na Otrzymano
1. Kliknij opcję Wycofaj pustą magazynową jednostkę obsługi.
2. Kliknij przycisk OK.
    * Zwróć uwagę, że pole Stan magazynowej jednostki obsługi ma wartość Otrzymano.  

## <a name="change-received-status-to-emptied-status"></a>Zmiana stanu Otrzymano na Opróżniono
1. Kliknij opcję Pusta karta Kanban.
2. Na liście oznacz wybrany wiersz.
    * Zwróć uwagę, że pole Stan magazynowej jednostki obsługi ma wartość Opróżniono.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]