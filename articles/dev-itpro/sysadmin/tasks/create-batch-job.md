--- 
title: "Utwórz zadań wsadowych"
description: "Zadanie wsadowe to grupa podzadań, które są przesyłane do wystąpienia serwera obiektów aplikacji (AOS) w celu automatycznego przetworzenia."
author: maertenm
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: b32c16a0c0045e22128746f81c6e9fd03370ac1f
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---
# <a name="create-batch-jobs"></a>Utwórz zadań wsadowych

[!include [task guide banner](../../includes/task-guide-banner.md)]

Zadanie wsadowe to grupa podzadań, które są przesyłane do wystąpienia serwera obiektów aplikacji (AOS) w celu automatycznego przetworzenia. Zadania wsadowe są uruchamiane przy użyciu poświadczeń zabezpieczeń użytkownika, który je utworzył. Aby utworzyć zadanie wsadowe, należy wykonać następującą procedurę. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="create-the-batch-job"></a>Tworzenie zadania wsadowego
1. Wybierz kolejno opcje Administrowanie systemem > Zapytania > Zadania wsadowe.
2. Kliknij przycisk Nowy.
3. W polu Opis stanowiska wpisz wartość.
4. W polu Planowana data/godzina rozpoczęcia wprowadź datę i godzinę.
5. Kliknij przycisk Zapisz.

## <a name="create-a-recurrence"></a>Tworzenie cyklu
1. W okienku akcji kliknij opcję Zadanie wsadowe.
2. Kliknij przycisk Cykl.
    * Te opcje służą do wprowadzania zakresu i wzorca cyklu.  
3. Kliknij przycisk OK.

## <a name="add-alerts"></a>Dodawanie alertów
1. W okienku akcji kliknij opcję Zadanie wsadowe.
2. Kliknij opcję Alerty.
    * Wskaż, czy komunikaty alarmowe mają być wysłane, po zakończeniu zadania wsadowego, wystąpieniu w nim błędu lub anulowaniu. Następnie określ, czy alerty mają być wyświetlane w postaci komunikatów podręcznych.   
3. Kliknij przycisk OK.


