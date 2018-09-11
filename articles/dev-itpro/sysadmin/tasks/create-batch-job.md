--- 
title: Tworzenie zadania wsadowego
description: "Zadanie wsadowe to grupa podzadań, które są przesyłane do wystąpienia serwera obiektów aplikacji (AOS) w celu automatycznego przetworzenia."
author: maertenm
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BatchJob, SysRecurrence, BatchAlerts
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 31c8e2ba87ef8c17a3147e1159104585258d4164
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-batch-job"></a>Tworzenie zadania wsadowego

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


