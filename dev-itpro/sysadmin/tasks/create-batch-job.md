--- 
title: Tworzenie zadania wsadowego
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: ca2b755406fb7fce4b11457be86f6a8685004438
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-batch-job"></a>Tworzenie zadania wsadowego

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


