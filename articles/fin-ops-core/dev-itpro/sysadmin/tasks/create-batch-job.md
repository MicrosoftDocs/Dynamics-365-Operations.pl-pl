---
title: Tworzenie zadania wsadowego
description: Zadanie wsadowe to grupa podzadań, które są przesyłane do wystąpienia serwera obiektów aplikacji (AOS) w celu automatycznego przetworzenia.
author: maertenm
manager: AnnBe
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BatchJob, SysRecurrence, BatchAlerts
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 27541c84a40fe9b7e7705162e06167ad4f7e4ed9
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2191392"
---
# <a name="create-a-batch-job"></a>Tworzenie zadania wsadowego

[!include [task guide banner](../../includes/task-guide-banner.md)]

Zadanie wsadowe to grupa podzadań, które są przesyłane do wystąpienia serwera obiektów aplikacji (AOS) w celu automatycznego przetworzenia. Zadania wsadowe są uruchamiane przy użyciu poświadczeń zabezpieczeń użytkownika, który je utworzył. Aby utworzyć zadanie wsadowe, należy wykonać następującą procedurę. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="create-the-batch-job"></a>Tworzenie zadania wsadowego
1. Otwórz **Okienko nawigacji > Moduły > Administracja systemu > Zapytania > Zadania wsadowe**.
2. Kliknij przycisk **Nowy**.
3. W polu **Opis stanowiska** wpisz wartość.
4. W polu **Zaplanowana data/godzina rozpoczęcia** wpisz datę i godzinę.
5. Kliknij przycisk **Zapisz**.

## <a name="create-a-recurrence"></a>Tworzenie cyklu
1. W Panelu akcji kliknij **Zadanie wsadowe**.
2. Kliknij **Cykl**. Te opcje służą do wprowadzania zakresu i wzorca cyklu.  
3. Kliknij przycisk **OK**.

## <a name="add-alerts"></a>Dodawanie alertów
1. W Panelu akcji kliknij **Zadanie wsadowe**.
2. Kliknij **Ostrzeżenia**. Wskaż, czy komunikaty alarmowe mają być wysłane, po zakończeniu zadania wsadowego, wystąpieniu w nim błędu lub anulowaniu. Następnie określ, czy alerty mają być wyświetlane w postaci komunikatów podręcznych.   
3. Kliknij przycisk **OK**.

## <a name="adjust-batch-job-status"></a>Dostosuj status zadania wsadowego
1. Otwórz **Administracja systemu > Zapytania > Zadania wsadowe**.
2. Wybierz właściwe zadanie wsadowe.
3. W Panelu akcji kliknij **Zadanie wsadowe > Funkcje > Zmień status**.
4. Wybierz właściwy status:
    - **Wstrzymane**: Ustaw status zadania wsadowego jako **wstrzymane**, żeby zostało usunięte z planu zadań wsadowych. Jest to odpowiednik *stop*.
    - **Oczekujące**: Ustaw status zadania wsadowego jako **oczekujące**, żeby zostało wpisane na listę zadań oczekujących na dodanie do planu zadań wsadowych. Jest to odpowiednik *iść*.
5. Kliknij przycisk **OK**.
