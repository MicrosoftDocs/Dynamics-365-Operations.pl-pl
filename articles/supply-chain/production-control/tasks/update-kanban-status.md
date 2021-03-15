---
title: Aktualizacja stanu w systemie Kanban
description: Gdy karta Kanban zostanie opróżniona przez pomyłkę lub otrzymana karta Kanban musi zostać opróżniona, należy zaktualizować stan karty Kanban.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Kanban, KanbanResetEmpty
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1161e642f8b3b1cd0a2568e0745caa6db5fe5afb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4981010"
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